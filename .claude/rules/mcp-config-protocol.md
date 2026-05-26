# MCP 配置协议（硬约束 — 违反即事故）

> 来源：多次真实配置事故（写错路径 / import 不存在的函数 / 多余 cmd 包装）

---

## 铁律 1：配置路径

**MCP 配置文件路径取决于你的平台。请查阅平台文档确认正确路径。**

| 环境 | 配置路径 | 备注 |
|------|---------|------|
| **Newmax（牛马AI）** | `~/.newmax/.mcp.json` | 唯一正确路径 |
| Claude Code 原版 | `~/.mcp.json` | Newmax 不读这个 |

- ❌ **禁止**往错误路径写 MCP 配置（写了也白写）
- ✅ **必须**确认平台实际读取的配置路径
- 写入前必须 Read 该文件当前内容（No Blind Overwrite）

---

## 铁律 2：命令格式

**直接调用可执行文件，不需要 `cmd /c` 包装。**

```json
// ✅ 正确
{ "command": "npx", "args": ["-y", "some-package"] }
{ "command": "python", "args": ["some_script.py"] }

// ❌ 错误（多余的 cmd 包装）
{ "command": "cmd", "args": ["/c", "npx", "-y", "some-package"] }
{ "command": "cmd", "args": ["/c", "python", "some_script.py"] }
```

**例外**：只有当命令本身是 Windows 内置命令（如 `dir`、`type`）时才需要 `cmd /c`。
npm/npx/pip/python/node 等一律直接调用。

---

## 铁律 3：markitdown MCP 启动方式

**`markitdown_mcp` 包没有顶层 `main` 函数，禁止用 `from markitdown_mcp import main`。**

正确启动方式（写在 wrapper 脚本中）：
```python
import runpy
runpy.run_module("markitdown_mcp", run_name="__main__")
```

---

## 铁律 4：写入后必须验证

**每次修改 MCP 配置后，必须执行以下验证：**

1. **JSON 语法检查**：用 python 解析确认无语法错误
   ```bash
   python -c "import json; json.load(open('path/to/.mcp.json'))"
   ```
2. **文件存在确认**：Read 文件确认内容正确
3. **启动测试**（新增 MCP 时必须）：用 stdin initialize 握手测试能否正常启动
4. **告知用户重启**：新 MCP 在下次会话才会加载

---

## 铁律 5：不要残留旧配置

**修改 MCP 配置后，检查是否有旧位置的残留文件。**

- 修改新路径后，检查旧路径是否有冲突配置
- 如果有 → 清理或同步（避免两份配置不一致导致混乱）

---

## MCP 新增清单（每次新增 MCP 前逐项检查）

- [ ] 配置写入正确的平台路径
- [ ] 命令格式无 `cmd /c` 包装（除非是 Windows 内置命令）
- [ ] 依赖包已安装（`pip install` / `npm install`）
- [ ] 启动测试通过（stdin initialize 握手）
- [ ] JSON 语法验证通过
- [ ] 已告知用户需要重启会话
- [ ] 旧配置位置无冲突残留

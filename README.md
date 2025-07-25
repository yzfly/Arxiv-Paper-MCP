# ArXiv Paper MCP

一个基于 arXiv 的论文检索与内容解析工具。支持 Model Context Protocol (MCP) 标准，提供论文搜索、PDF链接获取和内容解析功能。

<a href="https://glama.ai/mcp/servers/@yzfly/Arxiv-Paper-MCP">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@yzfly/Arxiv-Paper-MCP/badge" alt="ArXiv Paper MCP server" />
</a>

## 功能特性

* 🔍 **arXiv 论文智能搜索**：关键词检索，快速定位你关心的论文
* 🔗 **获取 PDF 下载链接**：获取 arXiv 论文的直接 PDF 下载链接
* 📄 **论文内容解析**：智能解析论文内容，优先使用 HTML 版本，回退到 PDF
* 🆕 **AI领域最新论文**：获取 arXiv AI 领域今日最新更新论文列表

## 安装使用

### NPX 方式（推荐）

```bash
npx @langgpt/arxiv-paper-mcp
```

### 全局安装

```bash
npm install -g @langgpt/arxiv-paper-mcp
arxiv-paper-mcp
```

## MCP 客户端配置

### Claude Desktop 配置

在 Claude Desktop 的配置文件中添加：

```json
{
  "mcpServers": {
    "arxiv-paper-mcp": {
      "command": "npx",
      "args": ["-y", "@langgpt/arxiv-paper-mcp@latest"]
    }
  }
}
```

配置文件位置：
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

### 其他 MCP 客户端

对于其他支持 MCP 的客户端，请参考其文档配置 stdio 传输方式。

## 可用工具与参数

### 1. 搜索论文

* **工具名**: `search_arxiv`
* **参数**:
  * `query`：搜索关键词
  * `maxResults`：返回论文数（可选，默认 5）

### 2. 获取PDF下载链接

* **工具名**: `get_arxiv_pdf_url`
* **参数**:
  * `input`：arXiv 论文 URL 或 arXiv ID（如：2403.15137v1）

### 3. 解析论文内容

* **工具名**: `parse_paper_content`
* **参数**:
  * `input`：arXiv 论文 URL 或 arXiv ID
  * `paperInfo`：论文元信息（可选，用于添加论文元数据）

### 4. 获取AI领域最新论文

* **工具名**: `get_recent_ai_papers`
* **参数**: 无

## 使用流程示例

1. **搜索论文**
   使用 `search_arxiv` 工具搜索相关论文
2. **获取最新AI论文**
   用 `get_recent_ai_papers` 工具获取今日最新AI领域论文
3. **获取PDF链接**
   用 `get_arxiv_pdf_url` 工具获取PDF下载链接
4. **解析论文内容**
   用 `parse_paper_content` 工具获取论文的文本内容（优先 HTML，回退 PDF）

## 开发指南

### 本地开发

```bash
# 克隆项目
git clone https://github.com/yzfly/arxiv-paper-mcp.git
cd arxiv-paper-mcp

# 安装依赖
npm install

# 开发模式运行
npm run dev

# 构建
npm run build

# 运行构建版本
npm start
```

### 项目结构

```
arxiv-paper-mcp/
├── src/
│   └── index.ts          # 主服务器文件
├── build/                # 编译输出目录
├── package.json          # 项目配置
├── tsconfig.json         # TypeScript 配置
├── README.md             # 项目说明
└── LICENSE               # 许可证
```

## 技术栈

- **Node.js** >= 18.0.0
- **TypeScript** - 类型安全的JavaScript
- **Model Context Protocol** - 标准化的AI上下文协议
- **arXiv API** - 学术论文数据源

## 故障排除

### 常见问题

1. **论文搜索失败**
   ```
   错误：搜索失败
   解决：检查网络连接，确保搜索关键词正确
   ```

2. **PDF解析失败**
   ```
   错误：PDF 解析失败
   解决：检查 arXiv ID 是否正确，确保论文存在
   ```

### 日志调试

启用详细日志：
```bash
DEBUG=arxiv-paper-mcp npx @langgpt/arxiv-paper-mcp
```

## 贡献指南

欢迎贡献代码！请遵循以下步骤：

1. Fork 本项目
2. 创建特性分支：`git checkout -b feature/amazing-feature`
3. 提交更改：`git commit -m 'Add amazing feature'`
4. 推送分支：`git push origin feature/amazing-feature`
5. 创建 Pull Request

## 许可证

本项目采用 MIT 许可证。详情请见 [LICENSE](LICENSE) 文件。

## 作者信息

- **作者**: yzfly
- **邮箱**: yz.liu.me@gmail.com
- **GitHub**: [https://github.com/yzfly](https://github.com/yzfly)

## 相关链接

- [Model Context Protocol](https://modelcontextprotocol.io/)
- [arXiv.org](https://arxiv.org/)
- [Claude Desktop](https://claude.ai/download)

## 支持

如果您觉得这个项目有用，请给它一个 ⭐！

如有问题或建议，请通过以下方式联系：

- 📧 邮箱：yz.liu.me@gmail.com
- 🐛 GitHub Issues：[项目问题追踪](https://github.com/yzfly/arxiv-paper-mcp/issues)
- 💬 GitHub Discussions：[项目讨论区](https://github.com/yzfly/arxiv-paper-mcp/discussions)
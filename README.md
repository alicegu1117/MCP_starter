# MCP Coursework - Model Context Protocol Learning Project

This repository contains my coursework and learning materials for the Model Context Protocol (MCP), including server implementations, client applications, and practical examples.

## 📁 Project Structure

```
mcp_coursework/
├── mcp_project/                 # Main project directory
│   ├── research_server.py       # MCP server for arXiv paper research
│   ├── mcp_chatbot.py          # MCP client chatbot implementation
│   ├── server_config.json      # Multi-server configuration
│   ├── pyproject.toml          # Python project configuration
│   └── papers/                 # Research papers data (gitignored)
├── mcp_client.ipynb            # Single server client notebook
├── mcp_client_multi_server.ipynb # Multi-server client notebook
├── research_server.ipynb       # Server creation tutorial notebook
└── .gitignore                  # Git ignore rules
```

## 🚀 Features

### MCP Research Server
- **arXiv Paper Search**: Search and retrieve academic papers from arXiv
- **Paper Information Storage**: Save paper metadata locally
- **Information Extraction**: Retrieve stored paper information by ID

### MCP Client Applications
- **Single Server Chatbot**: Connect to one MCP server
- **Multi-Server Chatbot**: Connect to multiple MCP servers simultaneously
- **Tool Discovery**: Automatic tool schema discovery and registration

### Supported MCP Servers
- **Research Server**: Custom arXiv paper research tools
- **Filesystem Server**: File and directory operations
- **Fetch Server**: Web content retrieval

## 🛠️ Setup Instructions

### Prerequisites
- Python 3.13+
- `uv` package manager
- Anthropic API key (for Claude models)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/alicegu1117/MCP_starter.git
   cd MCP_starter
   ```

2. **Set up the Python environment**
   ```bash
   cd mcp_project
   uv venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   uv sync
   ```

3. **Configure API keys**
   Create a `.env` file in the `mcp_project` directory:
   ```bash
   ANTHROPIC_API_KEY=your_anthropic_api_key_here
   ```

## 📖 Usage Examples

### Running the Research Server
```bash
cd mcp_project
uv run research_server.py
```

### Running the Multi-Server Chatbot
```bash
cd mcp_project
python mcp_chatbot.py
```

### Using Jupyter Notebooks
```bash
cd mcp_project
jupyter notebook
# Open mcp_client.ipynb or mcp_client_multi_server.ipynb
```

## 🔧 Key Components

### Research Server (`research_server.py`)
- **`search_papers(topic, max_results)`**: Search arXiv for papers on a topic
- **`extract_info(paper_id)`**: Retrieve stored paper information

### MCP Chatbot (`mcp_chatbot.py`)
- Connects to multiple MCP servers
- Automatic tool discovery and registration
- LLM-powered conversation with tool usage

### Server Configuration (`server_config.json`)
```json
{
    "mcpServers": {
        "research": {
            "command": "uv",
            "args": ["run", "research_server.py"]
        },
        "filesystem": {
            "command": "npx",
            "args": ["-y", "@modelcontextprotocol/server-filesystem", "."]
        }
    }
}
```

## 📚 Learning Materials

This project includes several Jupyter notebooks that demonstrate:
- **Lesson 3**: Basic MCP client implementation
- **Lesson 4**: Creating an MCP server with FastMCP
- **Lesson 6**: Multi-server MCP client implementation

## 🤝 Contributing

This is a learning project, but suggestions and improvements are welcome!

## 📄 License

This project is for educational purposes as part of MCP coursework.

## 🔗 Resources

- [Model Context Protocol Documentation](https://modelcontextprotocol.io/)
- [FastMCP Library](https://github.com/jlowin/fastmcp)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [MCP Inspector](https://github.com/modelcontextprotocol/inspector)

---

**Note**: The `papers/` directory contains generated research data and is excluded from version control via `.gitignore`. 
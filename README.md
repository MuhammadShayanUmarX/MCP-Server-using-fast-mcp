# mcp server using fast mcp

A modern todo list application built with FastAPI and integrated with an MCP (Model Context Protocol) server using FastMCP for Gemini CLI interaction.
Watch the demo video: [MCP Server Demo](https://drive.google.com/file/d/1vBwzGs_mDDPut9jPG1dQz8nDb7F9PPEz/view?usp=sharing)

## 🚀 Features

- ✅ **Complete CRUD operations** for todos
- 📊 **Statistics endpoint** for task tracking
- 🔌 **MCP server** using FastMCP (2025)
- 📝 **Pre-loaded dummy data** (5 tasks)
- 🤖 **Gemini CLI integration** ready
- 🎯 **Simple setup** with just 2 files

## 📁 Project Structure

```
fast-apimcp/
├── main.py              # FastAPI application + MCP server
├── mcp_server.py        # Modern MCP server using FastMCP
├── requirements.txt     # Dependencies
├── .gemini/
│   └── settings.json   # Gemini CLI configuration
└── README.md           # This file
```

## 🛠️ Installation

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Start FastAPI Server
```bash
python main.py
```

The API will be available at:
- **API Base**: http://localhost:8000
- **Documentation**: http://localhost:8000/docs
- **Stats Endpoint**: http://localhost:8000/todos/stats

### 3. Start MCP Server (Terminal 2)
```bash
python mcp_server.py
```

## 📊 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | API information and available endpoints |
| GET | `/todos` | Get all todos |
| GET | `/todos/stats` | Get todo statistics |
| GET | `/todos/{id}` | Get specific todo by ID |
| POST | `/todos` | Create new todo |
| PUT | `/todos/{id}` | Update existing todo |
| DELETE | `/todos/{id}` | Delete todo |

## 🔌 MCP Server Tools

The MCP server provides these tools for Gemini CLI:

- `get_todos` - Retrieve all todos
- `get_todo_stats` - Get statistics (total, completed, pending)
- `create_todo` - Create new todo
- `update_todo` - Update existing todo
- `delete_todo` - Delete todo
- `get_todo_by_id` - Get specific todo details

## 🤖 Gemini CLI Integration

### Configuration
The `.gemini/settings.json` file configures Gemini CLI to connect to your MCP server:

```json
{
  "mcpServers": {
    "todo-mcp-server": {
      "command": "python3",
      "args": ["mcp_server.py"],
      "cwd": "/home/okki/Desktop/projects/fast-apimcp"
    }
  }
}
```

### Example Commands
Once both servers are running, you can ask Gemini CLI:

- **"How many tasks are left?"** → Gets pending task count
- **"Show me all my todos"** → Lists all tasks
- **"Create a new task called Review code"** → Adds new task
- **"Mark task 1 as completed"** → Updates task status
- **"Delete task 3"** → Removes task

## 🧪 Testing

### Test FastAPI Directly
```bash
# Get all todos
curl http://localhost:8000/todos

# Get statistics
curl http://localhost:8000/todos/stats

# Create a new todo
curl -X POST "http://localhost:8000/todos" \
     -H "Content-Type: application/json" \
     -d '{"title": "Test Todo", "description": "Created via curl"}'
```

### Test MCP Server
```bash
python mcp_server.py
```
This will test the connection and show current todos.

## 📝 Dummy Data

The application comes pre-loaded with 5 dummy todos:
1. **Learn FastAPI** (pending) - Complete FastAPI tutorial
2. **Build MCP Server** (pending) - Create MCP server for Gemini CLI
3. **Test Integration** (pending) - Test FastAPI with MCP server
4. **Deploy Application** (completed) - Deploy to production
5. **Write Documentation** (pending) - Create API documentation

## 🔧 Technology Stack

- **FastAPI** - Modern Python web framework
- **FastMCP** - Modern MCP server library (2025)
- **Pydantic** - Data validation and serialization
- **Uvicorn** - ASGI server
- **httpx** - Async HTTP client

## 🎯 Quick Start Commands

```bash
# Install dependencies
pip install -r requirements.txt

# Start FastAPI (Terminal 1)
python main.py

# Start MCP Server (Terminal 2)
python mcp_server.py

# Test API
curl http://localhost:8000/todos/stats
```

## 🐛 Troubleshooting

### Common Issues

1. **"Cannot connect to FastAPI"**
   - Make sure FastAPI is running first: `python main.py`

2. **"Module not found: fastmcp"**
   - Install fastmcp: `pip install fastmcp`

3. **"Port 8000 already in use"**
   - Stop other services or change port in `main.py`

4. **MCP server not connecting**
   - Check `.gemini/settings.json` configuration
   - Ensure both servers are running

## 📈 Statistics Example

```json
{
  "total_todos": 5,
  "completed_todos": 1,
  "pending_todos": 4,
  "completion_percentage": 20.0
}
```

## 🎉 Success!

## 📹 Demo Video




Once everything is running, you'll have:
- ✅ FastAPI serving your todo API
- ✅ MCP server connected to FastAPI
- ✅ Gemini CLI able to manage your todos
- ✅ Real-time todo statistics
- ✅ Natural language todo management

Perfect for productivity and task tracking! 🚀

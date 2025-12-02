
Here’s an outline of steps to run **Context7** in Docker and sync its context directory using a GitHub repo across multiple computers:

### Steps to Set Up Context7 (Docker + Git Sync)

1. **Clone down this repo** and cd into it

```bash
git clone https://github.com/ajoslin103/context-7-data.git

cd context7-data
```

2. **Build the Docker Image**

```bash
docker build -t context7-mcp .
```

3. **Add the context7 server description to your Editor MCPConfig**

Update for the absolute path to your context7-data directory

```json
{
  "mcpServers": {
    "context7": {
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "-v",
        "<your-context7-data-path-goes-here>:/root/.context7",
        "context7-mcp"
      ]
    }
  }
}
```

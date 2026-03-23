# Mplify MCP Quickstart

This guide runs `mplify-mcp-server` against the OpenAPI specs generated in this repository under `generated/mcp`.

## Prerequisites

- Docker
- Optional: Node.js (for MCP Inspector)

Run all commands from `generated/mcp`.

```bash
cd generated/mcp
```

```powershell
Set-Location .\generated\mcp
```

## Build image

```bash
docker build -t mplify-mcp-server mplify-mcp-runner
```

```powershell
docker build -t mplify-mcp-server mplify-mcp-runner
```

## Generated API mapping

The current generated MCP folder structure and API names are:

| Domain | OpenAPI file | Env file | Port |
|---|---|---|---|
| Alarm Management | `alarm/alarmManagement.api.yaml` | `ALARM_MANAGEMENT.env` | `8000` |
| Fault Management | `fm/faultManagement.api.yaml` | `FAULT_MANAGEMENT.env` | `8001` |
| Service Inventory Management | `inventory/serviceInventoryManagement.api.yaml` | `SERVICE_INVENTORY_MANAGEMENT.env` | `8002` |
| Service Ordering Management | `order/serviceOrderingManagement.api.yaml` | `SERVICE_ORDERING_MANAGEMENT.env` | `8003` |
| Performance Monitoring | `pm/performanceMonitoring.api.yaml` | `PERFORMANCE_MONITORING.env` | `8004` |
| Streaming Management | `pm/streamingManagement.api.all-in-one.yaml` | `STREAMING_MANAGEMENT.env` | `8005` |
| Service Function Test | `sft/serviceFunctionTest.api.yaml` | `SERVICE_FUNCTION_TEST.env` | `8006` |

Before running each container, update the corresponding `.env` file values.

## Run MCP servers

### Alarm Management

```bash
docker run --rm -p 8000:8000 \
  -v "${PWD}:/data" \
  --env-file ./ALARM_MANAGEMENT.env \
  mplify-mcp-server
```

```powershell
docker run --rm -p 8000:8000 `
  -v "${PWD}:/data" `
  --env-file .\ALARM_MANAGEMENT.env `
  mplify-mcp-server
```

### Fault Management

```bash
docker run --rm -p 8001:8000 \
  -v "${PWD}:/data" \
  --env-file ./FAULT_MANAGEMENT.env \
  mplify-mcp-server
```

```powershell
docker run --rm -p 8001:8000 `
  -v "${PWD}:/data" `
  --env-file .\FAULT_MANAGEMENT.env `
  mplify-mcp-server
```

### Service Inventory Management

```bash
docker run --rm -p 8002:8000 \
  -v "${PWD}:/data" \
  --env-file ./SERVICE_INVENTORY_MANAGEMENT.env \
  mplify-mcp-server
```

```powershell
docker run --rm -p 8002:8000 `
  -v "${PWD}:/data" `
  --env-file .\SERVICE_INVENTORY_MANAGEMENT.env `
  mplify-mcp-server
```

### Service Ordering Management

```bash
docker run --rm -p 8003:8000 \
  -v "${PWD}:/data" \
  --env-file ./SERVICE_ORDERING_MANAGEMENT.env \
  mplify-mcp-server
```

```powershell
docker run --rm -p 8003:8000 `
  -v "${PWD}:/data" `
  --env-file .\SERVICE_ORDERING_MANAGEMENT.env `
  mplify-mcp-server
```

### Performance Monitoring

```bash
docker run --rm -p 8004:8000 \
  -v "${PWD}:/data" \
  --env-file ./PERFORMANCE_MONITORING.env \
  mplify-mcp-server
```

```powershell
docker run --rm -p 8004:8000 `
  -v "${PWD}:/data" `
  --env-file .\PERFORMANCE_MONITORING.env `
  mplify-mcp-server
```

### Streaming Management

```bash
docker run --rm -p 8005:8000 \
  -v "${PWD}:/data" \
  --env-file ./STREAMING_MANAGEMENT.env \
  mplify-mcp-server
```

```powershell
docker run --rm -p 8005:8000 `
  -v "${PWD}:/data" `
  --env-file .\STREAMING_MANAGEMENT.env `
  mplify-mcp-server
```

### Service Function Test

```bash
docker run --rm -p 8006:8000 \
  -v "${PWD}:/data" \
  --env-file ./SERVICE_FUNCTION_TEST.env \
  mplify-mcp-server
```

```powershell
docker run --rm -p 8006:8000 `
  -v "${PWD}:/data" `
  --env-file .\SERVICE_FUNCTION_TEST.env `
  mplify-mcp-server
```

## Run MCP Inspector

Use MCP Inspector to interact with a running server:

```bash
npx @modelcontextprotocol/inspector http://localhost:<port>/mcp
```

```powershell
npx @modelcontextprotocol/inspector http://localhost:<port>/mcp
```

Examples:

- `http://localhost:8000/mcp` Alarm Management
- `http://localhost:8001/mcp` Fault Management
- `http://localhost:8002/mcp` Service Inventory Management
- `http://localhost:8003/mcp` Service Ordering Management
- `http://localhost:8004/mcp` Performance Monitoring
- `http://localhost:8005/mcp` Streaming Management
- `http://localhost:8006/mcp` Service Function Test

## VS Code MCP setup

1. Start one or more MCP containers and verify each URL is reachable.
2. Add server entries in your user `mcp.json`.
3. Point each entry to the matching server URL (for example `http://localhost:8004/mcp`).
5. If the server does not appear immediately, run `Developer: Reload Window`.
6. Open Copilot Chat and use agent mode or the tools picker. The configured MCP server should now be available there.
7. If you are using an older VS Code MCP implementation, use the legacy `mcp.servers` setting in **User Settings JSON**.
8. If `mcp.servers` appears grayed out, it is in the wrong scope or unsupported by that settings scope.

Legacy fallback example (`mcp.servers` in User Settings JSON):

```json
{
  "mcp.servers": {
    "Alarm Management": {
      "url": "http://localhost:8000/mcp"
    },
    "Fault Management": {
      "url": "http://localhost:8001/mcp"
    },
    "Service Inventory Management": {
      "url": "http://localhost:8002/mcp"
    },
    "Service Ordering Management": {
      "url": "http://localhost:8003/mcp"
    },
    "Performance Monitoring": {
      "url": "http://localhost:8004/mcp"
    },
    "Streaming Management": {
      "url": "http://localhost:8005/mcp"
    },
    "Service Function Test": {
      "url": "http://localhost:8006/mcp"
    }
  }
}
```

## Claude Desktop setup

Add an MCP server entry for each API that points at the running container.

```json
{
  "mcpServers": {
    "Alarm Management": {
      "url": "http://localhost:8000/mcp"
    },
    "Fault Management": {
      "url": "http://localhost:8001/mcp"
    },
    "Service Inventory Management": {
      "url": "http://localhost:8002/mcp"
    },
    "Service Ordering Management": {
      "url": "http://localhost:8003/mcp"
    },
    "Performance Monitoring": {
      "url": "http://localhost:8004/mcp"
    },
    "Streaming Management": {
      "url": "http://localhost:8005/mcp"
    },
    "Service Function Test": {
      "url": "http://localhost:8006/mcp"
    }
  }
}
```



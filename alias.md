# Codex aliases

### Für schnelle Änderungen
alias codexf="codex --profile fast --search -a on-failure -s workspace-write"

### Default zum Entwickeln
alias codexd="codex --profile default --search -a on-failure -s workspace-write"

### Default mit Chrome DevTools MCP
alias codexc="codexd -c mcp_servers.chrome-devtools.enabled=true"

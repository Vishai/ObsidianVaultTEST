# n8n Automation Cheatsheet

## Overview
n8n is a powerful workflow automation tool that connects apps and services. This cheatsheet covers essential concepts and common patterns.

## Core Concepts

### Nodes
- **Trigger Nodes**: Start workflows (Webhook, Schedule, Manual)
- **Action Nodes**: Perform operations (HTTP Request, Database, etc.)
- **Logic Nodes**: Control flow (IF, Switch, Merge)

### Connections
- Drag from output to input
- Multiple connections allowed
- Data flows between nodes

### Executions
- Manual: Test button
- Automatic: Based on triggers
- View history in executions panel

## Common Trigger Patterns

### Webhook Trigger
```
Webhook → Process Data → Send Response
```
- Use for API endpoints
- Returns data to caller
- GET or POST methods

### Schedule Trigger
```
Cron Schedule → Fetch Data → Process → Store
```
- Use for periodic tasks
- Cron syntax: `0 9 * * 1-5` (9 AM weekdays)
- Timezone considerations

### Manual Trigger
```
Manual → Test Workflow → Debug
```
- Use for development
- Great for testing
- Click "Execute Workflow"

## Essential Nodes

### HTTP Request
```json
{
  "method": "GET",
  "url": "https://api.example.com/data",
  "authentication": "Header Auth",
  "headers": {
    "Authorization": "Bearer {{$credentials.apiKey}}"
  }
}
```

### Code Node (JavaScript)
```javascript
// Access input data
const items = $input.all();

// Process each item
return items.map(item => {
  return {
    json: {
      processed: item.json.value * 2,
      timestamp: new Date().toISOString()
    }
  };
});
```

### IF Node
```
Condition: {{$json.status}} equals "active"
- True → Continue workflow
- False → Different path or stop
```

## Data Transformation

### Accessing Data
- `{{$json.fieldName}}` - Current item
- `{{$node["NodeName"].json.field}}` - From specific node
- `{{$input.first().json.data}}` - First input item

### Expressions
- `{{new Date().toISOString()}}` - Current timestamp
- `{{$json.amount * 1.1}}` - Math operations
- `{{$json.name.toLowerCase()}}` - String methods

## Common Workflows

### 1. API to Database
```
Webhook → Transform Data → Database Insert → Return Success
```

### 2. Scheduled Scraping
```
Schedule → HTTP Request → Parse HTML → Store → Notify
```

### 3. Email Automation
```
Email Trigger → Parse Content → IF Logic → Send Email → Log
```

### 4. Multi-Service Sync
```
Service A → Transform → Service B
                     ↓
                 Service C
```

## Best Practices

### Error Handling
1. Use IF nodes to check conditions
2. Add error workflows
3. Log errors to database or file
4. Set up notifications for failures

### Performance
- Minimize HTTP requests
- Batch operations when possible
- Use pagination for large datasets
- Consider rate limits

### Organization
- Name nodes descriptively
- Group related workflows
- Use sticky notes for documentation
- Version control with git

### Security
- Use credentials, not hardcoded keys
- Validate webhook inputs
- Sanitize user data
- Enable webhook authentication

## Debugging Tips

### Inspect Node Output
- Click node to see output
- Check JSON tab
- Review executions panel
- Use pinned data for testing

### Common Issues
- **"No items"**: Previous node returned empty
- **Expression errors**: Check syntax with `{{}}`
- **Credential issues**: Verify authentication
- **Timeout**: Increase timeout or optimize

## Integration Examples

### Notion
```javascript
// Create page in Notion
{
  "parent": { "database_id": "xxx" },
  "properties": {
    "Title": {
      "title": [{"text": {"content": "{{$json.title}}"}}]
    }
  }
}
```

### Obsidian (via Webhook)
```
Create note → Format Markdown → POST to Obsidian Local REST API
```

### GitHub
```
Webhook (Push) → Parse Commit → Notify Team → Update Dashboard
```

## Resources
- [n8n Documentation](https://docs.n8n.io)
- [Community Forum](https://community.n8n.io)
- [Workflow Templates](https://n8n.io/workflows)

## Quick Reference

### Keyboard Shortcuts
- `Ctrl/Cmd + S` - Save workflow
- `Ctrl/Cmd + E` - Execute node
- `Ctrl/Cmd + A` - Select all
- `Delete` - Delete selected

### Data Types
- String: Text data
- Number: Numeric values
- Boolean: true/false
- Object: Nested JSON
- Array: Lists of items

---
*Tags: #automation #n8n #workflow #integration #productivity*

# MCP Registry

## Essential MCPs

### Playwright MCP
**Purpose**: Browser automation and UI verification
**Use Cases**:
- Screenshot current development state
- Verify UI changes match requirements
- Automated browser testing
- Network and console log monitoring

**Installation**:
```json
{
  "name": "playwright-mcp",
  "command": "npx",
  "args": ["playwright-mcp"],
  "type": "stdio"
}
```

### GitHub MCP
**Purpose**: Repository operations without leaving context
**Use Cases**:
- Create pull requests
- Review code changes
- Manage issues
- Check CI/CD status

### FireCrawl MCP
**Purpose**: Convert websites to markdown
**Use Cases**:
- Research competitor features
- Import documentation
- Analyze UI patterns
- Extract structured data

### Context7 MCP
**Purpose**: Enhanced context management
**Use Cases**:
- Load project-specific context
- Switch between contexts
- Maintain context history

### Notion MCP
**Purpose**: Access team documentation
**Use Cases**:
- Read project requirements
- Update status documents
- Access team knowledge base
- Sync decisions and outcomes

## Custom MCPs

### Internal API MCP
Create wrapper for your internal APIs with:
- Authentication handling
- Error standardization
- Rate limiting awareness
- Response transformation

### Validation MCP
Encapsulate validation logic:
- Business rule verification
- Data integrity checks
- Cross-service validation
- Compliance checking

## MCP Development Template
```javascript
// mcp-template.js
export const server = {
  name: 'custom-mcp',
  version: '1.0.0',
  tools: [
    {
      name: 'tool-name',
      description: 'What this tool does',
      inputSchema: {
        type: 'object',
        properties: {
          // Define inputs
        }
      },
      handler: async (input) => {
        // Implementation
        return { success: true, data: result };
      }
    }
  ]
};
```
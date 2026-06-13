# Nuclino

Nuclino is a unified team workspace that combines wikis, docs, and project management into a single collaborative platform. Teams use Nuclino to build internal knowledge bases, write documentation, manage projects, and share information across the organization using a graph-based content model that links items visually.

## API

The Nuclino REST API (public preview launched January 2022) allows developers to build integrations and automate content workflows. All API interactions use JSON over HTTPS, and content is authored and returned in Markdown.

- **Base URL:** `https://api.nuclino.com/v0`
- **Auth:** Bearer token API key in the `Authorization` header
- **Docs:** https://help.nuclino.com/d3a29686-api

### Resources

| Resource | Description |
|---|---|
| Items | Wiki pages with Markdown content — create, read, update, delete, search |
| Collections | Groups of items (page lists) — full CRUD |
| Workspaces | Top-level organizational units |
| Teams | Groups of workspace members (paid plans) |
| Users | User identity and membership information |
| Fields | Metadata schema for workspace items |
| Files | File attachments associated with items |

### Key Endpoints

```
GET    /v0/items                    List items in a workspace or team
POST   /v0/items                    Create an item or collection
GET    /v0/items/:id                Get a single item or collection
PUT    /v0/items/:id                Update title or content
DELETE /v0/items/:id                Delete (move to trash)
GET    /v0/items?search=...         Full-text search
GET    /v0/workspaces/:id           Get workspace details
GET    /v0/workspaces/:id/users     List workspace members
GET    /v0/users/:id                Get user details
```

## Rate Limits

- 150 requests per minute per API key
- HTTP 429 returned when exceeded
- Response headers: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset`, `Retry-After`

## Pricing

| Plan | Price | Key Limits |
|---|---|---|
| Free | $0 | 50 items, 2 GB storage |
| Starter | $6/user/month | Unlimited items, 10 GB/user, 30-day history |
| Business | $10/user/month | Starter + AI, audit log, team insights |

25% discount on annual billing. API access is included on all plans.

## Links

- Website: https://www.nuclino.com
- API Docs: https://help.nuclino.com/d3a29686-api
- Blog: https://blog.nuclino.com
- Pricing: https://www.nuclino.com/pricing
- API Keys: https://help.nuclino.com/04598850-manage-api-keys
- MCP Integration: https://help.nuclino.com/70af7f4f-connect-nuclino-to-ai-assistants-with-mcp

# Nuclino

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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

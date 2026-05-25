# CoreModels Connector for Claude

The CoreModels connector lets Claude read and edit your CoreModels knowledge-graph schemas
directly from a conversation — searching nodes, creating and updating nodes, mixins and
relations, and importing/exporting JSON Schema.

- **Connector type:** Remote MCP server (streamable HTTP)
- **Server URL:** `https://go.coremodels.io/mcp-admin`
- **Authentication:** OAuth 2.0 — you sign in with your CoreModels account; Claude never sees
  your password.
- **Website:** https://www.aramai.net/products/coremodels

## Prerequisites

- A CoreModels account at https://www.aramai.net/products/coremodels (a free account works).
- At least one CoreModels project. Your role on each project (Viewer / Editor / Admin)
  determines which tools you can use against it.

## Setup

1. In Claude, open **Settings → Connectors → Add custom connector** (or pick **CoreModels**
   from the directory once approved).
2. Enter the server URL: `https://go.coremodels.io/mcp-admin`
3. Click **Connect**. You'll be redirected to the CoreModels sign-in page.
4. Sign in and approve access. Claude receives a scoped OAuth token and the connector becomes
   active.

## Using it

Just describe what you want in plain language — Claude maps it to the right tool and the project
you're working in. Example prompts:

- "Summarize my CoreModels project — how many types, elements, and spaces does it have?"
- "Find every Type node whose label contains 'invoice', and show their relations."
- "Create a Type called 'Customer' and link it to 'Order' with the 'places' relation."
- "Export my project as JSON Schema."

## Available tools

### Read-only
| Tool | What it does |
|---|---|
| `search_nodes` | Search nodes by id, type, label, or space; optional relations/mixins. |
| `get_project_summary` | High-level summary of a project. |
| `get_mixins_and_relation_groups` | List a project's mixins and relation templates. |
| `export_jsonschema` | Export a project (or space) as a JSON Schema string. |

### Editing (require Editor; some require Admin)
| Tool | What it does |
|---|---|
| `create_node` / `update_node` / `remove_node` | Create, edit, or suspend a node. |
| `create_relation` / `remove_relation` | Add or remove a directed relation between nodes. |
| `create_mixin_type` | Create a mixin type. |
| `create_mixin_value` / `remove_mixin_value` | Set or clear mixin values on a node. |
| `bulk_create` | Create multiple nodes/relations in one call. |
| `import_jsonschema` | Import a JSON Schema into a space (Admin only). |

Every editing tool is annotated as a destructive operation, so Claude will ask you to confirm
before running it.

## Permissions & scope

The connector can only act on projects your signed-in account already has access to, and only
within the role you hold on each project. It cannot reach projects you aren't a member of.

## Troubleshooting

- **Sign-in loop / "not authorized":** make sure you're signed into the CoreModels account that
  belongs to the project you're trying to use.
- **"Tool is not available on this endpoint" or permission denied:** the action needs a higher role
  (Editor/Admin) than you hold on that project.
- **Connection fails:** confirm the server URL is exactly `https://go.coremodels.io/mcp-admin`.

## Support

- Email: ops@aramai.net
- Documentation: https://github.com/aramai-schematica/coremodels-connector-docs/blob/main/documentation.md
- Security issues: ops@aramai.net

## Privacy

See the [Privacy Policy](./privacy-policy.md).

# CoreModels Connector — Privacy Policy

_Last updated: 2026-05-25 · Provided by ARAMAI ("we")._

This policy describes how the CoreModels MCP connector (`https://go.coremodels.io/mcp-admin`)
handles data when used from Claude or any other MCP client.

## 1. Data we access

When you connect and authorize the connector, it accesses **only** the CoreModels data your
signed-in account is already permitted to see, in order to fulfil the request you make:

- **Project graph data** — nodes, relations, mixins, spaces, and JSON Schema content of the
  CoreModels projects you operate on.
- **Account identity** — the user identifier from your OAuth token, used to resolve your
  CoreModels account and check your project role.
- **Request content** — the tool name and arguments Claude sends on your behalf (for example a
  search expression or the node you want to create).

We do **not** access projects you are not a member of, and the connector enforces your existing
per-project role (Viewer / Editor / Admin).

## 2. How we use it

- To execute the operation you requested (search, create, update, export, etc.).
- To authenticate and authorize you against the correct CoreModels project.
- To produce operational logs (see §4) for reliability and security.

We do **not** use your project data to train AI models.

## 3. Sharing

- We do not sell your data.
- Your project data is not shared with third parties except infrastructure providers strictly
  required to run the service: Microsoft Azure (including Azure Cosmos DB) hosting.
- Requests originate from the MCP client you choose (e.g. Claude). Their handling of your prompts
  and the connector's responses is governed by that client's own privacy policy.

## 4. Storage & retention

- **Project data** is stored as part of your CoreModels account for as long as your account or
  project exists.
- **Operational logs** record metadata such as the tool invoked, duration, your user id, and the
  project id — used for debugging, abuse prevention, and security. Retention: 90 days.
- OAuth tokens are validated per request; revoking access in your account or in the MCP client
  immediately stops further access.

## 5. Your rights

You can disconnect the connector at any time from your MCP client, and revoke its access from your
CoreModels account. For access, correction, or deletion requests covering your data, contact us
(§7).

## 6. Security

Connections use HTTPS. Access requires OAuth 2.0 sign-in with user consent; the connector never
receives your password. Data is hosted on Microsoft Azure with encryption in transit and at rest.

## 7. Contact

ARAMAI — ops@aramai.net

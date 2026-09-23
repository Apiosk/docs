# Apiosk buyer documentation

The public site at https://docs.apiosk.com covers self-service signup,
organisation API keys, the buyer HTTP API, the hosted MCP server and App
spending. Publishing and payment-rail material is outside this public
integration guide while provider onboarding is not the product focus.

## Sources of truth

- Buyer API routes and response shapes: gateway/src/server.rs and
  gateway/src/public_api.rs in the sibling Gateway repository.
- Source directory and executable status: gateway/src/sources.rs and the
  public GET /v1/source-readiness snapshot.
- Hosted MCP tools: mcp/src/gateway-v2.mjs in the sibling MCP repository.
- Team signup and API-key controls: app/src/routes/signup.tsx and
  app/src/components/workspaces/organisation-api-keys.tsx.
- Generated API reference: openapi/apiosk-api.json.

Counts, operation availability and prices change. Do not copy a catalogue
count or a price from an example into a promise. Use the live source detail.

## Validate

~~~bash
npm run validate
npm run check:openapi
~~~

The Mintlify CLI is fetched by npx if it is not installed locally. A
local JSON, navigation and link check can run without network access.

## Hosting

Mintlify builds the docs content. The Netlify wrapper in this repository
proxies docs.apiosk.com to the configured Mintlify origin. It requires
APIO_DOCS_PROXY_TARGET. The wrapper is not a substitute for publishing
the Mintlify content. After a docs release, verify the live homepage,
OpenAPI reference and a representative API, MCP and App page.

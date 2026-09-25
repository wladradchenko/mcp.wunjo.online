# mcp.wunjo.online
Control Wunjo from local and cloud LLM by MCP. Use prompt, chat context, images, objects on the canvas to design vector graphics and refine in the editor.

This repository holds the **plugin manifests** for that server — nothing else. The server itself is
hosted at `https://mcp.wunjo.online/design` and needs no installation.

## Install

**Cursor** — install **Wunjo Design** from the Cursor Marketplace. To try this repository directly,
copy it to `~/.cursor/plugins/local/wunjo-design` and reload the window.

**Grok Build** — open `/plugin`, search for **Wunjo Design**, install.

**Grok Bot** — Settings → Plugins, install the Wunjo Design plugin from the Cursor Marketplace.

**ChatGPT** (web, paid plan) — Settings → Security and login → switch on **Developer mode**. Then
Plugins → plus → name it Wunjo, paste `https://mcp.wunjo.online/design`, pick OAuth.

**Claude** — Customize → Connectors → Add custom connector → paste the same address.

**Any other MCP client** — point it at `https://mcp.wunjo.online/design` (streamable HTTP).

On first connect the client opens a browser window to sign in to a Wunjo account; creating one is free.

## What the tools do

Forty-eight tools over your own documents in [Wunjo Design](https://wunjo.online/product/design), a
browser-based vector editor:

- documents, pages and layers — list, read, create, delete;
- elements — shapes, paths, gradients, effects, and text laid out from real font metrics;
- images — place your own or fetched ones, import SVG;
- brand — components, shared palette and fonts from your other documents;
- looking at the work — render the current page, check the print area of a product mock-up;
- output — export slices and templates;
- account — plan and credit balance;
- the editor's own image models — generation, upscale, background removal, splitting a picture into
  layers. These spend credits: the tool quotes the price first and runs only after you agree.

Everything an agent makes stays an ordinary editable file — vector objects on a canvas, not a flat
picture. Open the document at `wunjo.online` and keep working by hand.

## Authentication and network

The plugin talks to exactly one host:

- `https://mcp.wunjo.online/design` — the MCP server (streamable HTTP);
- `https://mcp.wunjo.online/.well-known/oauth-authorization-server` and
  `/.well-known/oauth-protected-resource/design` — OAuth discovery;
- `https://auth.wunjo.online` — where the person signs in, in their own browser.

Authorisation is OAuth 2.1 with PKCE and Dynamic Client Registration, so the client registers
itself. No API key or token is stored in this repository or pasted into a chat, and the tools only
ever reach the documents of the account that signed in.

## Support

`support@wunjo.online` — questions, access problems, anything about the server.

## License

MIT for these manifests (see `LICENSE`). Use of the hosted service is governed by the
[terms](https://wunjo.online/terms-of-service) and [privacy policy](https://wunjo.online/privacy-policy)
of wunjo.online.

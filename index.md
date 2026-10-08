---
title: Aisle MCP Server
---

# Aisle MCP Server

**[Aisle](https://aisle.wedding)** is a wedding marketplace for couples planning weddings worldwide — with deep coverage of destination weddings in Italy, Mexico, Greece, Spain, and Hawaii. Venues, vetted vendors, guest websites, RSVP, and AI-assisted planning in one place.

Aisle runs a public **Model Context Protocol (MCP)** server so AI assistants like **ChatGPT** and **Claude** can search real wedding data and help couples plan inside a conversation.

## Consumer directory connector

For the Aisle listing in MCP marketplaces and Claude's connector directory, use:

```text
https://aisle.wedding/api/claude/mcp
```

This hosted Streamable HTTP connector exposes public venue and supplier search,
budget estimates, timelines and planning tools without an account. Private wedding
details, guests, RSVP totals, events, accommodations and registry progress require
OAuth sign-in; changes require an existing Aisle membership.

Individual guest tools include only guests confirmed as 13 or older. Guest notes
and dietary details are excluded. This connector does not book venues, collect
payments or publish custom HTML. Estimates are planning guidance, not supplier
quotes or live availability.

For clients that accept remote MCP configuration:

```json
{
  "mcpServers": {
    "aisle": {
      "url": "https://aisle.wedding/api/claude/mcp"
    }
  }
}
```

The full endpoint below remains available with additional tools. See the
[current tool and connection documentation](https://aisle.wedding/mcp) for the
differences between endpoints.

## Full MCP endpoint

`https://aisle.wedding/api/mcp` — Streamable HTTP, OAuth.

## Connect

- **ChatGPT** — Settings → Connectors → Add → paste the URL.
- **Claude** — Settings → Connectors → Add custom connector → paste the URL.

Then ask: *"Find all-inclusive wedding venues on the Amalfi Coast for 60 guests"* or *"What does a destination wedding in Tulum cost?"*

## Learn more

- Website: [aisle.wedding](https://aisle.wedding)
- Browse venues: [aisle.wedding/venues](https://aisle.wedding/venues)
- Planning guides: [aisle.wedding/guides](https://aisle.wedding/guides)
- MCP details: [aisle.wedding/mcp](https://aisle.wedding/mcp)

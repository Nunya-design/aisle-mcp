# Aisle MCP Server

**[Aisle](https://aisle.wedding)** is a wedding marketplace for couples planning weddings anywhere in the world — with deep coverage of destination weddings across Italy, Mexico, Greece, Spain, and Hawaii. It brings venues, vetted vendors, guest websites, RSVP, and AI-assisted planning into one place.

This repository documents Aisle's **Model Context Protocol (MCP) server** — a public endpoint that lets AI assistants like **ChatGPT** and **Claude** search Aisle's wedding data and help couples plan directly inside a conversation.

> Aisle is one of the only wedding platforms with a live MCP server. Ask ChatGPT or Claude to "find Tuscany wedding venues for 80 guests" and it can answer from Aisle's real inventory.

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

```
https://aisle.wedding/api/mcp
```

Transport: **Streamable HTTP**. Authentication: OAuth (public discovery tools are available; personal wedding-planning tools require sign-in).

## What it can do

The server exposes wedding-specific tools, including:

- **Venues** — search wedding venues by country, region, budget, capacity, and style; get full venue details.
- **Vendors** — search wedding planners, photographers, florists, caterers, and more by category and location.
- **Guides** — search Aisle's editorial planning guides (budgets, timelines, legal requirements, etiquette).
- **Budget & travel** — estimate a wedding budget and estimate guest travel costs for a destination.
- **Planning** — generate a planning timeline, wedding checklist, and packing list.
- **Your wedding** (signed in) — manage guests, events, accommodations, and registry for your own wedding.

## Connect it

**ChatGPT** — Settings → Connectors → *Add* → paste the URL above (add as a Streamable HTTP server).

**Claude** — Settings → Connectors → *Add custom connector* → paste the URL above.

**Any MCP client** — point your client at `https://aisle.wedding/api/mcp` using the Streamable HTTP transport.

Once connected, you can ask things like:

- *"Find all-inclusive wedding venues on the Amalfi Coast for 60 guests."*
- *"What does a destination wedding in Tulum typically cost?"*
- *"Give me a 12-month planning timeline for a wedding in Greece."*
- *"Search for wedding photographers in Lake Como."*

## About Aisle

Aisle is building the modern wedding marketplace — starting with venues worldwide and expanding across vendors, guest sites, and planning tools. Learn more at **[aisle.wedding](https://aisle.wedding)**.

- Browse venues: <https://aisle.wedding/venues>
- Planning guides: <https://aisle.wedding/guides>
- MCP details: <https://aisle.wedding/mcp>

## License

Documentation in this repository is released under the MIT License. Aisle's data and services are subject to the terms at [aisle.wedding](https://aisle.wedding).

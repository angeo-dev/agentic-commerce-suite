# Angeo Agentic Commerce Suite for Magento 2

[![Packagist Version](https://img.shields.io/packagist/v/angeo/agentic-commerce-suite)](https://packagist.org/packages/angeo/agentic-commerce-suite)
[![Downloads](https://img.shields.io/packagist/dt/angeo/agentic-commerce-suite)](https://packagist.org/packages/angeo/agentic-commerce-suite)
[![Magento](https://img.shields.io/badge/Magento-2.4.6%20%E2%80%93%202.4.9-f26322)](composer.json)
[![Hyvä](https://img.shields.io/badge/Hyv%C3%A4-compatible-0a7)](https://angeo.dev/modules/)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)

**One `composer require` to make your store ready for AI agents.**

This is a Composer *metapackage*. It has no code of its own. It installs the
Angeo modules that work together, at versions tested together.

## What you get

| Layer | Module | What it does |
|---|---|---|
| Discover | `angeo/module-llms-txt` | `llms.txt`, `llms-full.txt` (llms.txt spec v2) |
| Discover | `angeo/module-robots-txt-aeo` | AI-bot rules in `robots.txt`, Content-Usage signals, bot IP check |
| Understand | `angeo/module-rich-data` | Product, Offer, Breadcrumb, ItemList, return policy JSON-LD |
| Understand | `angeo/module-openai-product-feed` + `-api` | Product feed for ChatGPT shopping |
| Act | `angeo/module-ucp` + `angeo/module-ucp-catalog` | `/.well-known/ucp` profile and UCP catalog (Google AI Mode, Gemini) |
| Act | `angeo/module-ucp-checkout` | UCP checkout with live shipping rates, orders and webhooks; the buyer pays on your own checkout |
| Act | `angeo/module-ucp-checkout-mcp` | The same UCP checkout as MCP tools |
| Act | `angeo/module-mcp-server` | MCP server for Claude, ChatGPT, Gemini and custom agents |
| Act | `angeo/module-mcp-checkout` | Guest cart and pay-by-link checkout over MCP |
| Act | `angeo/module-webmcp` | WebMCP tools in the shopper's browser (Chrome) |
| Check | `angeo/module-aeo-audit` | `bin/magento angeo:aeo:audit` — score your store |
| Measure | `angeo/module-agent-activity` | Which AI agents come, what they do, and which orders they bring |

Optional, not installed by default:
`angeo/module-aeo-brand-visibility` (needs your own AI provider keys).

## Install

```bash
composer require angeo/agentic-commerce-suite
bin/magento setup:upgrade
bin/magento cache:flush
```

Then check the result:

```bash
bin/magento angeo:aeo:audit
```

All settings live under **Stores → Configuration → Angeo**.

## Want only some modules?

Install the modules you need one by one. For example:

```bash
composer require angeo/module-llms-txt angeo/module-rich-data
```

## Requirements

* Magento Open Source, Mage-OS or Adobe Commerce 2.4.6 – 2.4.9
* PHP 8.2 – 8.5 (some modules still support 8.1; the suite as a whole needs 8.2)
* Luma or Hyvä

## Versioning

The suite has its own version. A new suite version is released when a module
gets a new major version, or when we add or remove a module.
Minor and patch updates of modules come in automatically through `^` ranges.

## License

MIT. Made by [angeo.dev](https://angeo.dev).

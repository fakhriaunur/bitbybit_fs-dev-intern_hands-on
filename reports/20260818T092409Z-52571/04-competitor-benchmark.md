# Competitor Benchmark

## Report status

- Status: `PASS`
- Evidence completeness: `PARTIAL` — competitor values are dated public-source estimates, not runtime tests

## Method

Retrieved official public pages on `2026-08-18`. No competitor accounts were created. Values are labeled:

- `Observed`: directly observed in bitbybit product or docs.
- `Public-source estimate`: stated by an official public source, not independently tested.
- `Not comparable`: scope, plan, audience, or measurement differs.

Layer 1 uses WhatsApp-first AI commerce/support products: WATI, respond.io, SleekFlow, and Gorgias as an adjacent ecommerce-support reference.

Layer 2 is retained as an integration-operating-model appendix: SAAS Integrator, API2Cart, Make, and n8n solve broader connectivity/workflow problems and are not direct WhatsApp product substitutes.

## Layer 1 — WhatsApp-first AI commerce/support

| Capability | Product | Evidence class | Finding/value | Source URL | Retrieved UTC | Confidence | Comparable? |
|---|---|---|---|---|---|---|---|
| Commerce/catalog | bitbybit | Observed | Commerce product surface includes Shopify and Shopee Beta CSV/XLSX auto-detection/mapping; no import executed | `/tmp/.../COM-01-S02` | 2026-08-18 | High | Yes |
| Commerce/catalog | WATI | Public-source estimate | Official positioning describes AI-powered customer engagement and ecommerce/Shopify usage; catalog depth not independently confirmed | https://www.wati.io/ | 2026-08-18 | Medium | Partial |
| Commerce/catalog | respond.io | Public-source estimate | WhatsApp automation and integrations are public; catalog/checkout depth not confirmed in reviewed source | https://respond.io/whatsapp-business-api | 2026-08-18 | Medium | Partial |
| Commerce/catalog | SleekFlow | Public-source estimate | WhatsApp AI agents positioned for sales, with Shopify, Salesforce, and HubSpot integrations | https://sleekflow.io/en-us/channels-integrations/whatsapp | 2026-08-18 | Medium | Partial |
| Commerce/catalog | Gorgias | Public-source estimate | Ecommerce helpdesk and AI platform; catalog/order action details not tested | https://www.gorgias.com/ | 2026-08-18 | Medium | Partial |
| Customer support | bitbybit | Observed | Livechat, ticket, chatbot, forms, widget, filters, assignment buckets, and channel connection surfaces present; no seeded conversation | `/tmp/.../CHAT-01-S01`–`CHAT-01-S06` | 2026-08-18 | High | Yes |
| Customer support | WATI | Public-source estimate | WhatsApp Business API page highlights multiple logins, increased limits, and team inbox | https://www.wati.io/whatsapp-business-api/ | 2026-08-18 | Medium | Partial |
| Customer support | respond.io | Public-source estimate | Public home page positions unified team inbox across WhatsApp, TikTok, Instagram, and Facebook with AI Agents | https://respond.io/ | 2026-08-18 | Medium | Partial |
| Customer support | SleekFlow | Public-source estimate | Omnichannel messaging and AI agents positioned for sales and support | https://sleekflow.io/ | 2026-08-18 | Medium | Partial |
| Customer support | Gorgias | Public-source estimate | Helpdesk, chat, FAQ, and AI Agent positioned for ecommerce support | https://www.gorgias.com/ | 2026-08-18 | Medium | Partial |
| WhatsApp/omnichannel | bitbybit | Observed | Authenticated catalog lists WhatsApp Business App, Cloud API, Sandbox, Instagram, Facebook, TikTok Beta, and other channels | `/tmp/.../INT-01-S01` | 2026-08-18 | High | Yes |
| WhatsApp/omnichannel | WATI | Public-source estimate | WhatsApp-centric engagement platform also positions Instagram and Messenger support | https://www.wati.io/ | 2026-08-18 | Medium | Partial |
| WhatsApp/omnichannel | respond.io | Public-source estimate | Public integration page lists WhatsApp plus multiple chat channels and tools | https://respond.io/integrations | 2026-08-18 | Medium | Partial |
| WhatsApp/omnichannel | SleekFlow | Public-source estimate | WhatsApp, Instagram, SMS, and other channels positioned in AI suite | https://sleekflow.io/ | 2026-08-18 | Medium | Partial |
| WhatsApp/omnichannel | Gorgias | Public-source estimate | Omnichannel ecommerce support is public, but WhatsApp parity was not confirmed from reviewed official pages | https://www.gorgias.com/apps | 2026-08-18 | Low | No |
| AI/automation | bitbybit | Observed | AI Studio agent, knowledge, tagging, chatbot templates/flows, and AI Playground are present; publishing not tested | `AI-01-S01`–`AI-01-S03`, `CHAT-01-S03` | 2026-08-18 | High | Yes |
| AI/automation | WATI | Public-source estimate | Official site calls platform AI-powered and highlights no-code/AI chatbots | https://www.wati.io/pricing/ | 2026-08-18 | Medium | Partial |
| AI/automation | respond.io | Public-source estimate | Home page positions AI Agents with chat, calls, campaigns, and automation | https://respond.io/ | 2026-08-18 | Medium | Partial |
| AI/automation | SleekFlow | Public-source estimate | Official site positions AI suite and AI agents for revenue-driving conversations | https://sleekflow.io/ | 2026-08-18 | Medium | Partial |
| AI/automation | Gorgias | Public-source estimate | AI Agent and automation positioned for ecommerce support and sales | https://www.gorgias.com/ | 2026-08-18 | Medium | Partial |
| CRM/customer record | bitbybit | Observed | Customer search/source/tag filters, segments, import history, and CRM product surface present | `CRM-01-S01`–`CRM-01-S05` | 2026-08-18 | High | Yes |
| CRM/customer record | WATI/respond.io/SleekFlow/Gorgias | Not comparable | CRM depth differs by product and was not tested; marketing pages do not establish record-model parity | Official pages above | 2026-08-18 | Low | No |
| Native integrations | bitbybit | Observed | Shopify product-level connectors plus messaging, reviews, payment, Meta, and Indonesian shipping cards | `INT-01-S01` | 2026-08-18 | High | Yes |
| Native integrations | respond.io | Public-source estimate | Official integrations page lists broad channel/tool coverage | https://respond.io/integrations | 2026-08-18 | Medium | Partial |
| Native integrations | SleekFlow | Public-source estimate | Official WhatsApp page names Salesforce, HubSpot, Shopify | https://sleekflow.io/en-us/channels-integrations/whatsapp | 2026-08-18 | Medium | Partial |
| Native integrations | Gorgias | Public-source estimate | Official apps directory positions ecommerce platform/app integrations | https://www.gorgias.com/apps | 2026-08-18 | Medium | Partial |
| Plan limits/pricing | bitbybit | Observed/Public-source estimate | Public product-level Free/Starter/Growth/Pro Bundle; bitLink observed $0/$6/$19/$299 tiers; Developer gate requires Standard+ | `PUB-01-S09`, `PLAN-01-S01`, `LINK-01-S03`, `INT-01-S02` | 2026-08-18 | High | Yes |
| Plan limits/pricing | WATI | Public-source estimate | Official pricing page offers plan comparison and free trial; exact runtime limits not tested | https://www.wati.io/pricing/ | 2026-08-18 | Medium | Partial |
| Plan limits/pricing | respond.io | Public-source estimate | Official pricing search result lists Starter $79/mo, Growth $159/mo, Advanced $279/mo, Enterprise, and 7-day trial | https://respond.io/pricing | 2026-08-18 | Medium | Partial |
| Plan limits/pricing | SleekFlow | Public-source estimate | Official pricing page provides plan comparison; WhatsApp message costs are documented separately | https://sleekflow.io/en-us/pricing | 2026-08-18 | Medium | Partial |
| Plan limits/pricing | Gorgias | Not comparable | Reviewed official pages establish product scope, not a comparable plan snapshot | https://www.gorgias.com/ | 2026-08-18 | Low | No |

## Layer 2 — Integration operating model appendix

| Product | Public-source estimate | What it contributes to benchmark | Source URL | Comparable to bitbybit? |
|---|---|---|---|---|
| Make | Visual no-code workflow automation; webhook and HTTP integrations; official page claims 3,000+ apps | Reference for breadth and self-serve connector composition, not WhatsApp product parity | https://www.make.com/en/integrations/gateway | Partial |
| n8n | Source-available AI workflow automation with webhook integrations and broad app connectivity | Reference for technical extensibility, custom workflow depth, and webhook ergonomics | https://n8n.io/integrations/webhook/ | Partial |
| API2Cart | Unified ecommerce API covering 70+ shopping platforms and marketplaces | Reference for marketplace coverage and normalized commerce data model | https://api2cart.com/ | No |
| SAAS Integrator | Custom API/integration provider across ERP, ecommerce, POS, CRM, WMS, PIM, marketplaces, and marketing systems | Reference for managed integration services, not self-serve WhatsApp workflow UX | https://www.saasintegrator.com/ | No |

## Layer decision

- Secondary layer retained as comparable: `NO` for direct product scoring; retained as integration-operating-model appendix.
- WhatsApp-first fallback used: `YES`; WATI, respond.io, and SleekFlow are primary direct references, with Gorgias as adjacent ecommerce-support context.
- Reason: Layer 2 products optimize generalized connectivity or managed integration, while bitbybit competes first on AI commerce/support workflows. Treating connector count as equivalent would overstate parity and hide setup/ownership differences.

## Sources

| Source ID | Publisher | URL | Retrieved UTC | Scope | Notes |
|---|---|---|---|---|---|
| `SRC-01` | bitbybit | https://bitbybit.studio/pricing/ | 2026-08-18 | Pricing | Public product-level packaging. |
| `SRC-02` | bitbybit | https://bitbybit.studio/integrations/ | 2026-08-18 | Integrations | Public native/integration operating model. |
| `SRC-03` | bitbybit | https://knowledge.bitbybit.studio/ | 2026-08-18 | Docs | Product guides, setup, API, AI-readable docs. |
| `SRC-04` | WATI | https://www.wati.io/ | 2026-08-18 | Product positioning | WhatsApp/AI/customer engagement claims. |
| `SRC-05` | WATI | https://www.wati.io/pricing/ | 2026-08-18 | Pricing | Official plan page. |
| `SRC-06` | respond.io | https://respond.io/ | 2026-08-18 | Product positioning | Unified inbox, channels, AI Agents. |
| `SRC-07` | respond.io | https://respond.io/integrations | 2026-08-18 | Integrations | Public channel/tool list. |
| `SRC-08` | respond.io | https://respond.io/pricing | 2026-08-18 | Pricing | Public plan snapshot. |
| `SRC-09` | SleekFlow | https://sleekflow.io/en-us/channels-integrations/whatsapp | 2026-08-18 | WhatsApp/integrations | AI agents and named CRM/ecommerce integrations. |
| `SRC-10` | SleekFlow | https://sleekflow.io/en-us/pricing | 2026-08-18 | Pricing | Official pricing page. |
| `SRC-11` | Gorgias | https://www.gorgias.com/ | 2026-08-18 | Ecommerce support | AI/helpdesk/chat positioning. |
| `SRC-12` | Gorgias | https://www.gorgias.com/apps | 2026-08-18 | Integrations | Official app directory. |
| `SRC-13` | Make | https://www.make.com/en/integrations/gateway | 2026-08-18 | Webhooks/workflows | 3,000+ app claim and webhook workflow reference. |
| `SRC-14` | n8n | https://n8n.io/integrations/webhook/ | 2026-08-18 | Webhooks/workflows | Webhook/app connectivity reference. |
| `SRC-15` | API2Cart | https://api2cart.com/ | 2026-08-18 | Commerce integration | 70+ platform/marketplace claim. |
| `SRC-16` | SAAS Integrator | https://www.saasintegrator.com/ | 2026-08-18 | Managed integration | Broad integration-service scope. |

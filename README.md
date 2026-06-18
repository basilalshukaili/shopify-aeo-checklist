# Shopify AEO Checklist

> **AI Engine Optimization (AEO)** is the practice of structuring your Shopify store so AI assistants — ChatGPT Shopping, Perplexity, Google AI Overviews, Claude, and Bing Copilot — confidently cite and recommend your products.

Traditional SEO gets you ranked on page 1. AEO gets you *spoken aloud* as the answer.

This checklist is free, community-maintained, and opinionated. PRs welcome.

---

## ⚡ Check your store's AEO in 10 seconds (free)

Don't guess — measure. We built free tools that score your store against everything in this checklist:

- **[Run the free AI-Visibility Check →](https://hatchloop.dev/ai-visibility-check/)** — your AI Search Visibility + Agent-Commerce score + competitor comparison
- One command in your terminal: `npx github:basilalshukaili/ai-visibility-checker yourstore.com`
- [Product Schema Generator](https://hatchloop.dev/product-schema-generator/) · [llms.txt Generator](https://hatchloop.dev/llms-txt-generator/) · [AI Crawler Check](https://hatchloop.dev/ai-crawler-check/)
- The data: [we audited 22 DTC brands](https://hatchloop.dev/state-of-ai-visibility-dtc/) — median AI-visibility was just **52/100**, and a third had zero product schema.

Want it done for you? The [**$99 AEO Audit + Fix List**](https://hatchloop.dev/ai-visibility-check/) ranks every gap with the exact fixes.

---

## Why AEO matters for Shopify merchants in 2025-26

- A growing share of product-discovery queries now resolve in an AI answer box rather than ten blue links — and the trend is accelerating.
- ChatGPT's shopping integrations (Bing index + partner feeds) actively pull product data from structured pages.
- Perplexity's "Shop" mode cites specific product pages with price, reviews, and stock status.
- Google's AI Overviews increasingly answer "best [product] for [use case]" queries directly — your page either gets cited or doesn't.

The window to establish AEO authority is *right now*, before the field is saturated.

---

## The Checklist

### 1. Structured Data (Schema.org)

Shopify auto-generates some schema, but it's rarely complete. Audit yours.

- [ ] **Product schema** — `name`, `description`, `brand`, `offers` (price, currency, availability), `sku`, `gtin`
- [ ] **AggregateRating** — AI models weight stores with verified review counts heavily; don't skip this
- [ ] **BreadcrumbList** — helps models understand your site hierarchy
- [ ] **FAQPage** — add an FAQ section to product/collection pages and mark it up; AI systems love Q&A formatted content
- [ ] **Organization** schema on your homepage — `name`, `url`, `logo`, `contactPoint`, `sameAs` (link to social profiles)
- [ ] Validate at [schema.org](https://schema.org/docs/gs.html) and [Google's Rich Results Test](https://search.google.com/test/rich-results)

**Shopify apps that help:** Ilana's JSON-LD for SEO, Schema Plus for SEO.

---

### 2. Product Page Content

AI models synthesize answers from page text. Thin pages get skipped.

- [ ] **Product description 300+ words** with natural language answering "Who is this for?", "What problem does it solve?", "How is it used?"
- [ ] **Explicit use-case framing** — "Best for X type of customer" phrasing gets cited in "best for [use case]" queries
- [ ] **Comparative language** — mention what category of problem you solve (not competitors by name); e.g., "unlike clip-on alternatives, this mounts permanently"
- [ ] **Specs in prose, not just a table** — AI scrapers often miss HTML tables; restate key specs in a sentence
- [ ] **In-stock language** — "Available now, ships in 2-3 days" scores better than just setting inventory levels
- [ ] **Return/guarantee info on the product page** — AI shopping answers include trust signals; buried policies don't count

---

### 3. Brand Authority Signals

AI models score brand trustworthiness before deciding whether to cite you.

- [ ] **Consistent NAP** — Name, Address, Phone identical across Google Business, Bing Places, Yelp, and your Shopify contact page
- [ ] **Wikipedia or Wikidata presence** — if your brand is notable enough, a Wikidata entry dramatically increases citation frequency
- [ ] **Press mentions with dofollow links** — AI training corpora weight press coverage; even niche trade press counts
- [ ] **Google Merchant Center feed** — required for ChatGPT's shopping integration via Bing Shopping index
- [ ] **Verified reviews on third-party platforms** — Trustpilot, G2, Google Reviews; AI systems cross-reference these

---

### 4. Technical Foundations

- [ ] **Page speed under 2.5s LCP** — slow pages get dropped from AI Shopping surface crawls
- [ ] **Mobile-first layout** — AI crawlers use mobile user-agent strings
- [ ] **Canonical URLs** — prevent duplicate-content dilution across product variants (size, color)
- [ ] **`hreflang` tags** if you sell internationally — helps AI models serve the right-locale answer
- [ ] **`robots.txt`** — confirm AI crawlers (GPTBot, PerplexityBot, ClaudeBot, anthropic-ai) are NOT blocked

Shopify's default robots.txt allows all bots. Only worry about this if you've customized it.

Verify bot access:

```bash
curl -A "GPTBot" https://yourstore.myshopify.com/robots.txt | head -30
```

---

### 5. Content Hub / Blog

A content hub lifts your whole store's AEO authority.

- [ ] **Answer cluster strategy** — for each product category, publish 3-5 "What is the best X for Y?" posts with honest, cited answers (even if competitors win some categories)
- [ ] **Long-tail FAQ posts** — "How do I clean a [product]?", "What's the difference between [A] and [B]?" — AI systems frequently surface these
- [ ] **Regular cadence** — at least 2 posts/month; freshness matters for AI Overviews
- [ ] **Internal links** from blog posts to product pages with descriptive anchor text
- [ ] **Author bio with credentials** — E-E-A-T signals matter for AI content scoring

---

### 6. Feeds and Integrations

- [ ] **Google Merchant Center** — synced product feed, no disapprovals
- [ ] **Bing Merchant Center** — separate submission; powers ChatGPT Shopping
- [ ] **Meta Commerce Manager** — indirectly improves authority signals
- [ ] **Open Graph + Twitter Card tags** — Shopify sets these but check they're populated with product-specific values, not store defaults

---

### 7. Monitoring Your AEO Performance

AEO is not (yet) tracked in Google Analytics by default. Proxy metrics:

| Signal | How to track |
|---|---|
| AI referral traffic | Filter GA4 referrers for `perplexity.ai`, `chatgpt.com`, `bing.com/chat`, `claude.ai` |
| "Cited in AI answer" | Manual spot-checks weekly: ask ChatGPT / Perplexity for your target queries |
| Structured data health | Google Search Console -> Enhancements |
| Rich result impressions | GSC -> Search results, filter by RICH_SNIPPET appearance |

---

## Free Tools

| Tool | What it does |
|---|---|
| [Google Rich Results Test](https://search.google.com/test/rich-results) | Validates structured data on any URL |
| [Schema Markup Validator](https://validator.schema.org/) | Checks schema.org compliance |
| [PageSpeed Insights](https://pagespeed.web.dev/) | LCP / CWV check |
| [Screaming Frog (free tier)](https://www.screamingfrog.co.uk/seo-spider/) | Crawl for missing schema, thin content |
| [hatchloop.dev/tools/aeo-check/](https://hatchloop.dev/tools/aeo-check/) | Free AEO audit for Shopify stores — scans schema completeness, bot access, content signals, and feed status in one pass |

---

## Contributing

This checklist is intentionally opinionated and Shopify-specific. To contribute:

1. Fork the repo, create a branch, open a PR
2. Cite a source for any new claim (AI behavior changes fast; undated opinions age poorly)
3. Keep items actionable — "think about SEO" is not a checklist item

Issues and discussions welcome.

---

## License

[CC0 1.0 Universal](LICENSE) — public domain. Use freely, no attribution required.

---

*Maintained by the community. Not affiliated with Shopify Inc.*

# 🔮 Precogs

Archive of predictions about the future. Mini-essays about what might happen — and whether it did.

Named after the precognitive beings in *Minority Report* who could see the future before it happened.

## How it works

Each prediction is a free-form essay that ends with a concrete, verifiable claim. Every prediction has:

- **Status**: pending → confirmed / debunked / partially
- **Check date**: when to verify the prediction
- **Confidence**: how sure the author is (%)
- **Two languages**: Russian and English

## Local development

```bash
bundle install
bundle exec jekyll serve
```

## Adding a prediction

Create a markdown file in `_posts/ru/` and `_posts/en/` with this front matter:

```yaml
---
layout: prediction
title: "Your prediction title"
date: 2026-03-14
author: luvor
lang: ru  # or en
categories: [tech, ai]
status: pending
check_date: 2030-01-01
confidence: 75
tags: [ai, future]
---
```

## License

Content © luvor. Code: MIT.

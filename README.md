# ebay — eBay Selling / Commerce API skill

Skill mandiri (standalone) untuk
eBay RESTful APIs (Selling, Commerce, Buy, Post-Order). Struktur identik dengan skill
toolkit:

```
ebay/
├── SKILL.md          # name + description, workflow, output shape, references
├── agents/
│   └── openai.yaml   # interface config (display_name, short_description, default_prompt)
└── references/
    └── api/          # 35 kategori, 385 API doc (clean Markdown)
        ├── Inventory_API/
        ├── Fulfillment_API/
        ├── Account_v1_API/
        ├── Browse_API/
        ├── Post_Order_Return_API/
        └── ...
```

## Cara pakai (untuk agent/LLM)

Salin ke direktori skills coding-agent (mis. `.codex/skills/` atau
`.claude/skills/`), atau set langsung sebagai skill. Saat ada pertanyaan API eBay,
skill `ebay-selling-api-guide` memandu inspect `references/api/**` lalu cross-check ke
dok resmi bila perlu.

## Update / regenerasi

Konten `references/api/` adalah **snapshot statis** dari eBay OpenAPI 3 contracts
(mirror `hendt/ebay-api`, sumber resmi di `https://edp.ebay.com/api-docs/master/`).
Untuk memperbarui, tarik spec terbaru lalu jalankan toolchain di repo `updskills`:

```
python tools/spec_to_markdown.py \
  --spec ebay-specs/specs \
  --outdir ebay/references/api
```

Tidak perlu mengedit manual satu-satu.

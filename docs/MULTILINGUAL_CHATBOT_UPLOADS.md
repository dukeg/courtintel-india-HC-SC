# Multilingual Chatbot + Upload/Download Modules

## Scope
This upgrade adds a multilingual product layer for CourtIntel India:

- Language switcher for Indian-language UX.
- Special chatbot agent available anytime.
- Upload module for orders, judgments, notes, draft pleadings, and research documents.
- Download module for AI-generated reports.
- Backend APIs for chat, file upload, document analysis, and report download.

## Supported language codes
Starter support includes:

- `en` English
- `hi` Hindi
- `kn` Kannada
- `ta` Tamil
- `te` Telugu
- `ml` Malayalam
- `mr` Marathi
- `bn` Bengali
- `gu` Gujarati
- `pa` Punjabi
- `ur` Urdu

Only English, Hindi, and Kannada have starter response templates. Other languages are wired into the UI and backend normalization layer for future model integration.

## API endpoints

### Chatbot agent
`POST /chat`

Payload:

```json
{
  "query": "Find case status by CNR and summarize next hearing",
  "language": "en",
  "history": []
}
```

Response includes:

- answer
- detected intent
- safety notice
- suggested actions
- citation placeholders

### Upload document
`POST /documents/upload`

Form data:

- `file`: uploaded document
- `language`: language code

The starter decodes text-like files. For production, add PDF parsing, OCR, scanned-document pipelines, and court-document layout extraction.

### Download report
`GET /documents/download/{file_id}`

Returns a generated AI report as text. Production can upgrade this to PDF/DOCX/XLSX exports.

## Production AI roadmap

### Chatbot agent
The current chatbot is deterministic and safe by default. For production:

1. Detect user language.
2. Classify intent.
3. Retrieve court/case/judgment records from official-indexed sources.
4. Generate answer using retrieval-grounded LLM.
5. Add citation spans.
6. Run legal-safety guardrails.
7. Translate or generate directly in selected language.

### Upload analysis
Production upload analysis should include:

- PDF text extraction.
- OCR for scanned documents.
- Layout-aware extraction for cause lists and orders.
- Statute/entity/citation extraction.
- Timeline extraction.
- Similar case retrieval.
- Report generation with citations.

### Download tools
Recommended exports:

- AI case summary PDF.
- Court timeline report.
- Citation table CSV.
- Watchlist activity export.
- Research memo DOCX.

## Legal-safety principle
The chatbot and document AI should never claim to replace legal counsel. All outputs must be treated as research assistance and verified with official court records.

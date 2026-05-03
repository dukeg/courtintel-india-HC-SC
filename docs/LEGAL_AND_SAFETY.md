# Legal, compliance, and AI safety notes

## Product positioning

CourtIntel India should be positioned as a legal research and court-monitoring platform, not as a substitute for lawyers, judges, registry officials, or official court records.

## AI safety rules

- Always show source references for summaries.
- Never present AI output as official court status.
- Never claim guaranteed case outcomes.
- Flag uncertainty clearly.
- Preserve original source links and timestamps.
- Store model version and analysis timestamp.

## Data access rules

- Prefer official APIs, public datasets, licensed feeds, or formal partnerships.
- Do not bypass captchas, access restrictions, or anti-automation controls.
- Respect robots.txt and terms of use when crawling public websites.
- Maintain source-specific rate limits.

## Sensitive information

Court data may include personal information. Add privacy review before production:

- data minimization
- access controls
- retention policies
- redaction support
- audit logs

---
name: sol-cv-design
description: Create or revise a concise, single-column Word and PDF CV using Sol's red and violet editorial format, consistent entry hierarchy, separate publications and conferences, and verified career facts.
---

# Sol CV Design

Use this format for a professional CV, especially for applied AI, policy, and computational social science. Let the candidate's actual experience determine the positioning; using Power BI does not itself justify a Business Intelligence headline.

## Layout and hierarchy

- One column; two pages maximum by default. Education comes first, then Work Experience, Consulting Experience, Teaching Experience, and Research Experience. Add Publications and Policy Reports, Conferences and Seminars, and Honors when relevant. Technical Skills is the final section; languages may be its last line.
- Keep every publication and every conference as an individual entry inside the CV, unless the user explicitly requests a separate document. Do not compress several works or events into a semicolon-filled paragraph.
- Use a white page, black text, deep violet `#5B20D6` for links and the main identity accent, and red `#C52842` for dates. Both red and violet are intentional in this CV format.
- Use Arial consistently. Name: 25 pt bold. Section headings: 11 pt bold. Body: 9.5–10 pt. Date metadata: 8.5 pt. Footer: 7 pt. Never shrink body text below 9.5 pt to meet the page limit.
- Use 0.45-inch top/bottom and 0.5-inch side margins on US Letter by default. Align entries to a shared left edge, with dates at the right. Use restrained neutral section rules and one violet rule above the name, not below it.
- Standardize every entry: bold title and institution, right-aligned red date, then concise descriptions. Keep the title with its description. Use the same font, date treatment, punctuation, indents, and spacing across sections.
- Identify supervisors explicitly with `Supervisor: Name`. For multiple course supervisors, use `Supervisors: Name (course); Name (course)`. Do not leave personal names unlabeled next to institutions.
- Contact details belong under the headline and in the footer of every page. Include only the phone numbers and links the user supplies. Do not infer current residence from the university location. Preserve a user's request to omit a city when applying elsewhere.

## Content decisions

- Treat explicit category and ordering choices from the user as authoritative. Sort newest first within each section unless the user requests an exception. Do not automatically reclassify a consulting firm as consulting if the user places a staff role in Work Experience.
- Keep the institution's location distinct from where the candidate worked; for example, `Geneva-based organization | Remote`.
- Represent career progression rather than applying a final title retroactively: fact-checking, a chapter-author contract, and a subsequent promotion are distinct stages. Preserve verified dates without inventing a promotion date.
- Explain invitations and policy audiences with concrete institutional context and audience size. Do not inflate a working-group presentation into a UN General Assembly speech or label an official session as a side event.
- Use the formal verified names of people, courses, institutions, and publications. Preserve the difference between an authored article, a chapter, an edited issue, and a discussion paper.
- Never invent missing employers, metrics, findings, funding amounts, dates, or responsibilities. Distinguish scholarship support from educational credit. Ask a focused question when the missing information changes a factual claim.
- For a two-page edit, remove repetition and shorten supporting descriptions first. Preserve the candidate's core contribution, tools, scope, and measurable achievements. Obtain direction before deleting substantive experience merely to make it fit.
- Apply all annotations to the latest canonical Word and PDF. Inspect the current file before repeating an edit that may already be present. Do not revert accepted corrections while responding to screenshots of older versions.

## Editable template

Use `scripts/build_cv.py` with the schema illustrated in `assets/example.json`:

```bash
python scripts/build_cv.py --input assets/example.json --output /absolute/path/cv.docx
```

The example is fictional. Replace its content with verified candidate data; never treat sample text as evidence. The generated DOCX uses native paragraphs and hyperlinks rather than screenshots or columns. The builder does not publish, contact anyone, or fetch external data.

Resolve Python and document dependencies through the host's workspace dependency tools when available. The script needs `python-docx`.

## Delivery gate

Render the final DOCX to PDF and page images using the document tools available in the host. Inspect every page and verify:

- At most two pages and one reading column.
- No clipping, footer overlap, orphan headings, broken links, or split entry titles.
- Education first; requested experience categories correct; skills last.
- Each publication and conference remains separate.
- Consistent supervisor labels, dates, contact details, and current facts in both formats.

If the CV is too long, revise the text and distribution instead of silently cutting factual content or producing a third page. Deliver the editable Word and matching PDF only after the final inspection.

Publishing this skill does not authorize publishing a candidate's CV or personal information. Repository examples and assets must be synthetic unless the user explicitly authorizes their public release.

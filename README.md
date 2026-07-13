# Electrical Estimating Review Skill

A reusable ChatGPT Skill for reviewing electrical, fire alarm, security, IT, communications, AV, BAS-interface, and low-voltage contract documents from a senior estimator and field-construction perspective.

The Skill is designed to help estimators identify scope, materials, document gaps, coordination requirements, constructability concerns, estimating risks, RFIs, assumptions, exclusions, and drawing conflicts before pricing or rough-in begins.

## What this Skill does

The Skill can:

- summarize the defined scope of work;
- prepare a categorized material list;
- identify scope gaps, vague notes, and unassigned responsibilities;
- cross-reference drawings, schedules, details, and specifications;
- identify coordination requirements with other trades and vendors;
- review constructability, access, clearances, sequencing, shutdowns, and existing conditions;
- identify technical, commercial, schedule, procurement, and labour risks;
- prepare RFIs only after checking the available contract documents;
- prepare assumptions, qualifications, and exclusions;
- create a scope-responsibility matrix;
- determine whether the information is sufficient to begin rough-in.

## Review philosophy

The Skill does not provide definitive conclusions from vague, cropped, isolated, or insufficient information.

Before completing a review, it will:

1. confirm the estimator's scope of work;
2. identify the project stage and requested deliverable;
3. inventory the documents provided;
4. determine whether enough information is available;
5. request only the missing documents that could materially affect the result.

Where applicable, users may be asked to provide specifications, addenda, bid Q&A, CCNs, SIs, CDs, RFIs, sketches, revised drawings, emails, vendor quotations, shop drawings, schedules, site photos, and related architectural, structural, mechanical, civil, controls, security, AV, or life-safety documents.

The Skill checks those documents before recommending an RFI. Information such as manufacturer, model, dimensions, accessories, cable category, finish, and environmental rating may already be defined in specifications or schedules.

## Commands

Use one command or combine several commands in one request.

| Command | Purpose |
|---|---|
| `/scope-summary` | Summarize confirmed scope, boundaries, responsibilities, interfaces, and unresolved questions. |
| `/material-list` | Produce a categorized material list and separate exact quantities, calculated quantities, allowances, and unknowns. |
| `/scope-gaps` | Identify omitted, ambiguous, conflicting, open-ended, or unassigned scope. |
| `/coordination` | List coordination requirements with other disciplines, trades, vendors, utilities, and the owner. |
| `/constructability` | Review access, working clearances, routing, congestion, supports, finishes, phasing, shutdowns, and installation sequence. |
| `/estimating-risks` | Identify technical, commercial, labour, procurement, schedule, quantity, coordination, and contractual risks. |
| `/rfi` | Prepare only RFIs that remain unresolved after the available documents are reviewed. |
| `/assumptions` | Prepare measurable estimating assumptions for unresolved items. |
| `/exclusions` | Prepare exclusions for work outside the defined scope or unsupported by the documents. |
| `/assumptions-exclusions` | Produce assumptions and exclusions in separate sections. |
| `/scope-matrix` | Create a responsibility matrix for supply, installation, rough-in, cabling, testing, programming, commissioning, and related interfaces. |
| `/drawing-conflicts` | Cross-reference documents and produce a drawing conflict matrix. |
| `/document-check` | Determine whether sufficient information has been provided for the requested review. |
| `/rough-in-review` | Determine whether coordinated information is sufficient to begin rough-in. |
| `/full-review` | Run all applicable review modules. |

Natural-language requests are also supported. For example, “prepare a bill of materials,” “find missing scope,” or “review for rough-in readiness” will trigger the corresponding review module.

## Example prompts

### Full estimating review

```text
Guild's scope is electrical and communications rough-in and cabling.
Review the attached drawings and specifications.
/full-review
```

### Material and scope-gap review

```text
Review the attached IT room drawings.
/material-list /scope-gaps /coordination
Separate confirmed quantities from allowances and unknown quantities.
```

### Drawing cross-reference

```text
Cross-reference the electrical, communications, architectural, and mechanical drawings.
/drawing-conflicts /constructability /rfi
Do not prepare an RFI until the specifications and related schedules have been checked.
```

### Rough-in readiness

```text
Guild is responsible for conduit rough-in for BAS and security data outlets.
Review the attached documents and confirm whether enough information exists to start rough-in.
/rough-in-review
```

### Scope matrix

```text
Create a scope matrix for the communications cabinet, BAS data outlet, security panels, fibre backbone, copper cabling, grounding, power, plywood, sleeves, testing, and commissioning.
/scope-matrix
```

### Preliminary review with incomplete documents

```text
I only have this drawing at the moment.
Provide a preliminary /scope-gaps review and identify the specific documents still required before final pricing.
```

## Recommended input

For the strongest review, provide:

- the estimator's defined scope of work;
- the relevant drawings and revisions;
- specifications;
- addenda and bid Q&A;
- CCNs, SIs, CDs, RFIs, sketches, and bulletins;
- architectural, structural, mechanical, controls, security, AV, and life-safety documents;
- vendor quotations, shop drawings, product data, and control diagrams;
- relevant emails, site photos, schedules, phasing plans, and shutdown requirements.

Not every document is required for every review. The Skill should request only the information that could materially resolve the issue being reviewed.

## Installation

1. Download or clone this repository.
2. Zip the `electrical-estimating-review` folder so that `SKILL.md` remains at the root of the folder inside the archive.
3. Open ChatGPT Skills at `/skills`.
4. Upload the ZIP file.

The packaged upload file must be 25 MB or smaller.

## Repository structure

```text
electrical-estimating-review/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── output-templates.md
    └── review-checklist.md
```

## Important limitations

- The Skill supports estimating and constructability review; it does not replace consultant design, engineering approval, code interpretation by the authority having jurisdiction, or site verification.
- Material quantities depend on the completeness and scale of the documents provided.
- A preliminary review should not be treated as a final estimate when critical information is missing.
- Silence in a document is not automatically converted into contractor responsibility.

## Updating the Skill

Edit `SKILL.md` for workflow or behavior changes. Use the files under `references/` for detailed checklists and output templates. Repackage the complete folder after each update.

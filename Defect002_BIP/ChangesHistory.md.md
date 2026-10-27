<!--
HOW TO USE
1. Copy to docs/bip/<ReportName>/CHANGELOG.md (one per BIP report and its data model).
   If several reports share one data model, keep one file and list them all in section 2.
2. Fill sections 1 and 2 once (the baseline). Edit them again only when a report, layout or data model is added or removed.
3. Every PR adds ONE short entry at the top of section 3.
4. Delete these comments and the example entry when you start.
Why: BIP has no native Git integration. The report (.xdoz) and data model (.xdmz) are archives, and layout templates
are hard to read in a diff, so this file records what changed in plain words.
Author, reviewer, commit, dates and deployment runs already live in the PR and the deployment tool; do not copy them here.
-->
--Testing Changes for merging.
# PO_MILESTONE_DETAILS_DM : Change History

## 1. Summary (baseline, fill once)

| Field | Value |
|---|---|
| Purpose | One sentence, and who uses the output |
| Technical owner | |
| Catalog path | /Custom/OIC Reports/PO_MILESTONE_DETAILS_REP.xdoz |
| Data model path | /Custom/OIC Reports/Data Model/PO_MILESTONE_DETAILS_DM.xdmz |
| Environments | Dev / Test / Prod instance names |
| Deployment method | Deployment tool pipeline, or manual catalog upload |
| Tag format | `bip-<report>-vMAJOR.MINOR.PATCH` (MAJOR = output or parameters change for consumers, MINOR = new layout or field, PATCH = fix) |
| Baseline tag / date | `bip-<report>-v0.1.0` / YYYY-MM-DD |

## 2. Inventory (baseline, edit only when something is added or removed)

| Component | Name | Notes |
|---|---|---|
| Report | PO_MILESTONE_DETAILS_REP | |
| Data model | PO_MILESTONE_DETAILS_DM | |
| Layouts | | Template type (RTF, XPT, Excel), output formats offered |



## 3. Release Log (newest first)

Copy this block to the top for each change:

```markdown
### bip-<report>-vX.Y.Z : YYYY-MM-DD : <short title>
- Tracker / PR: DEF-0000 / #00
- Changed: <component> (<layout, data set, parameter, bursting, etc.>): was <before>, now <after>
- Why: <reason>
- Tested: Dev preview with parameters <values>, output format <PDF/Excel/...> (evidence in PR)
- Rollback to: bip-<report>-vX.Y.(Z-1)
- Manual action after deploy: none (or: map data source, re-create schedule, re-upload translation)
```

Add one `Changed:` line per component touched. Add `Breaking for consumers: yes, <what>` only when true (changed parameters, columns, file name or output structure).

Be specific: name the layout section, data set, SQL clause, parameter or burst rule. "Updated report" is not acceptable.


<!-- ### Example (delete when you start)

### bip-customerstatement-v3.1.1 : 2026-10-20 : Statement date format
- Tracker / PR: DEF-1003 / #64
- Changed: Layout `Statement.rtf` (header table): date was MM/DD/YYYY, now DD/MM/YYYY
- Why: Finance statements must follow the DD/MM/YYYY convention
- Tested: Dev preview, customer CUST-100, PDF (evidence in PR)
- Rollback to: bip-customerstatement-v3.1.0
- Manual action after deploy: none

### bip-customerstatement-v0.1.0 : YYYY-MM-DD : Baseline
- Initial Git import. Contents: see section 2. -->

## 4. History Before Git (optional, limit to about 1 to 2 hours)

Major events only. Do not invent history. Mark how sure you are.

| Approx. date | What changed | Source | Confidence |
|---|---|---|---|
| | | Deployment history / tracker / earlier downloaded archives / person | High / Medium / Low |

## 5. Rollback

Redeploy the previous tag through your deployment tool, or re-upload the previous archives to the catalog folder. Check the data source mapping and schedules afterwards, because they can differ per environment.

## PR checklist (add to the PR template)

```markdown
- [ ] Tracker ID is in the branch name and PR title
- [ ] CHANGELOG.md has a new entry naming the component and the before and after
- [ ] Both the report (.xdoz) and data model (.xdmz) are re-downloaded and committed if either changed
- [ ] Rollback tag is filled in
- [ ] Before and after output evidence is attached
- [ ] No passwords, tokens or keys in this PR
```
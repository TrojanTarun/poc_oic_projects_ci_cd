<!--
HOW TO USE
1. Copy to docs/<ProjectName>/CHANGELOG.md (one per OIC Project). Keep it outside the projects/ folder
   OIC writes to, until a dry run confirms an export does not delete or overwrite other files there.
2. Fill sections 1 and 2 once (the baseline). Edit them again only when an integration is added or removed.
3. Every PR adds ONE short entry at the top of section 3. Nothing else needs updating.
4. Delete these comments and the example entry when you start.
Why: OIC exports a Project as a binary .CAR file, so GitHub cannot show what changed inside it.
Author, reviewer, commit, dates and deployment runs already live in the PR and FlexDeploy; do not copy them here.
-->

# TEN_OIC_POS_PRJ : Change History

## 1. Project Summary

| Field | Value |
|---|---|
| Project name | `TEN_OIC_POS_PRJ`|
| Business domain | `Direct Procurement` |
| Purpose | `Purpose`  |
| Business owner | `OwnerName`|
| Technical owner / CODEOWNER | `LeadName` |
| Created in OIC | `YYYY-MM-DD` |
| Added to Git | `YYYY-MM-DD` (baseline tag `TEN_OIC_POS_PRJ-v1.0.0`) |
| Current released version | `TEN_OIC_POS_PRJ-v1.0.0` |
| Git artifact path | `projects/TEN_OIC_POS_PRJ.car` (branch `main`) |
| Environments | Dev / Test / Prod instance names | `Dev` |
| Deployment  | FlexDeploy pipeline name or link | `FlexDeploy` |

## 2. Inventory (baseline, edit only when something is added or removed)

| Integration | Version | Trigger / endpoint | Connections | Lookups / libraries |
|---|---|---|---|---|
| | | | | |
TEN POS-26B Receive Tasks Scheduler | 1.0.0 | Scheduled  |||
TEN POS-26B Process | 1.1.1 | App Driven | TEN POS-30 SMat DB<br>TEN POS-26B PeopleConnect REPORT<br>TEN POS-26B OIC REST Trigger | TEN_POS26B_Mapping_Lookup<br>TEN_Common_Email_Lookups|
Notes: names only, never secrets. Anything that differs per environment (host, user name): list the names here.

## 3. Release Log (newest first)

Copy this block to the top for each change:

```markdown
### <project>-vX.Y.Z : YYYY-MM-DD : <short title>
- Tracker / PR: DEF0000 / #00
- Changed: <INTEGRATION> (01.00.000A -> 01.00.000B), <element>: was <before>, now <after>
- Why: <reason>
- Tested: Dev, Test (evidence in PR)
- Rollback to: <project>-vX.Y.(Z-1)
- Manual action after deploy: none
```

Add one `Changed:` line per integration or artifact touched. Add `Breaking for callers: yes, <what>` only when true.

Be specific about the element (mapper field, switch condition, lookup row, schedule, connection setting). "Updated mapping" is not acceptable.

### Example 

### TEN_OIC_POS_PRJ_v1.0.1 : 2026-10-20 : new changes
- Tracker / PR: DEF0000 / 
- Changed: TEN_OIC_POS_PRJ (01.00.0001 -> 01.00.0002),  `what changes has been made`
- Why: `Failure reason`
- Tested: Dev, Test (evidence in PR)
- Rollback to: `previous version`
- Manual action after deploy: `action`

### TEN_OIC_POS_PRJ_v1.0.0 : YYYY-MM-DD : Baseline
- Initial Git import. Contents: see section 2.

## 4. History Before Git (optional, limit to about 1 to 2 hours)

Major events only. Do not invent history. Mark how sure you are.

| Approx. date | What changed | Source | Confidence |
|---|---|---|---|
| | | FlexDeploy history / OIC version list / tracker / person | High / Medium / Low |

## 5. Rollback

Redeploy the previous tag through FlexDeploy. If OIC must import it directly, create a branch from the tag, set the Repository branch to it, then import. Note anything learned from the first real rollback here.

## PR checklist (add to the PR template)

```markdown
- [ ] Tracker ID is in the branch name and PR title
- [ ] CHANGELOG.md has a new entry naming the integration, element, before and after
- [ ] Rollback tag is filled in
- [ ] Before and after test evidence is attached
- [ ] No passwords, tokens or keys in this PR
```

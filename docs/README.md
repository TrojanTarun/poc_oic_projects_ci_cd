## Layout

```
projects/        written by OIC Export to Repository (.CAR files)
deployments/     written by OIC for project deployments
docs/
  README.md      this index
  <ProjectName>/CHANGELOG.md
.github/
  CODEOWNERS
  pull_request_template.md
```

## Projects

| Project | Domain | Technical owner | Wave | History |
|---|---|---|---|---|
| InvoiceSync | Finance | @invoice-lead | 0 | [CHANGELOG](InvoiceSync/CHANGELOG.md) |
| | | | | |

## Standalone integrations not yet in a Project

Track here until moved. They cannot use OIC Export to Repository.

| Integration | Owner | Planned Project | Planned wave | IAR path in Git (if committed manually) |
|---|---|---|---|---|
| | | | | `integrations/<name>.iar` |

## BI Publisher objects

| Report | Catalog path | Owner | Archive path in Git |
|---|---|---|---|
| | | | `bip/<path>/` |

## Rules

1. Every change goes through a Pull Request with a CHANGELOG entry.
2. The entry names the artifact, the element, and the before and after values.
3. Tags: `<project>-vMAJOR.MINOR.PATCH`; BIP reports use `bip-<report>-vMAJOR.MINOR.PATCH`.
4. No secrets in any file in this repository.

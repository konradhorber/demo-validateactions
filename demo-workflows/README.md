# validate-actions Demo Workflows

Quick demos of the main features added in the last 2 weeks.

## 1a. Job Needs Validation (`01a-needs-validation.yml`)
Shows correct and incorrect `needs` references:
- ✅ Valid job dependencies  
- ❌ References to non-existent jobs

## 1b. Circular Dependencies (`01b-circular-dependencies.yml`)
Demonstrates circular dependency detection:
- ❌ Simple 3-job circular dependency cycle

## 2. Outdated Actions (`02-outdated-actions.yml`) 
Demonstrates version checking:
- ❌ Outdated action versions (v3 actions)
- ❌ SHA commit references instead of tags
- ✅ Current action versions (v4 actions)

## Quick Test

```bash
# Install and run
poetry install --with dev
poetry run validate-actions demo-workflows/

# Should show:
# - Error for "missing-job" reference in 01a
# - Error for circular dependency in 01b  
# - Warnings for outdated actions in 02
```
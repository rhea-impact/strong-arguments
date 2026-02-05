---
name: cleanup
description: Clean up and validate this repo after changes. Checks JSON schemas, missing files, markdown formatting, and TODOs.
disable-model-invocation: true
allowed-tools: Read, Grep, Glob, Bash, Write, Edit
---

# Repo Cleanup

Run a comprehensive cleanup and validation check on this repository.

## Checklist

### 1. Validate JSON Files Against Schemas

Check that all JSON data files validate against their schemas:
- `fallacies.json` should validate against `fallacy-schema.json`
- `engagement.json` should validate against `engagement-schema.json`
- `examples/argument-domains.json` should be valid JSON

Use a JSON schema validator if available, or manually check required fields.

### 2. Check for Required Files

Verify these standard files exist:
- [ ] `LICENSE` — Should be MIT as stated in README
- [ ] `.gitignore` — Should exclude common patterns
- [ ] `CONTRIBUTING.md` — Guidelines for contributors (optional but recommended)

If missing, offer to create them.

### 3. Markdown Consistency

Check all `.md` files for:
- Consistent heading styles (ATX style: `#`, `##`, etc.)
- No trailing whitespace
- Proper link formatting
- Tables render correctly

### 4. Find TODOs and FIXMEs

Search for any incomplete items:
```
grep -r "TODO\|FIXME\|XXX\|HACK" --include="*.md" --include="*.json"
```

Report any found.

### 5. Check Internal Links

Verify that all internal markdown links point to files that exist:
- Links in README.md to other docs
- Links in PHILOSOPHY.md, REFERENCES.md, etc.
- Links in examples/README.md

### 6. JSON Formatting

Ensure all JSON files are properly formatted (2-space indent, consistent style).

## Output

After running checks, provide:
1. **Summary** — What was checked
2. **Issues Found** — Any problems discovered
3. **Fixes Applied** — What was automatically fixed
4. **Manual Action Needed** — What requires human decision

## Auto-fix Policy

- **Auto-fix:** Formatting issues, missing LICENSE (MIT), missing .gitignore
- **Ask first:** Missing CONTRIBUTING.md, content changes, structural changes

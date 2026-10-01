# Documentation Generation

## Source of Truth

- Read the relevant file under `canon/` and `styles.yml` before generating or revising documentation.
- Treat the selected canon as authoritative for technical facts and required procedure order. Do not invent setup facts, commands, values, requirements, or mutation variants.
- Use only complete, explicitly defined mutation and omission entries from that canon. If an entry is incomplete or ambiguous, do not infer its intended field or variants.
- Keep technical facts and procedure steps accurate unless a specific documented mutation applies. Reordering sections is allowed; changing the order of procedure steps is not.

## Styles

- Produce one page for each style defined in `styles.yml`: `terse`, `sufficient`, `thorough`, and `legacy`.
- Follow the detail, tone, and formatting guidance in `styles.yml`. Vary structure and phrasing naturally so pages can read as if written by different engineers.
- Apply style-level omission rules only when supported by the canon. Include thorough-only context in thorough pages when the canon defines it.
- Legacy pages may use more canon-defined conflicts or omissions, but must not call themselves old, outdated, or legacy, or explicitly claim to have been written earlier. Keep them practical, slightly dated, and informal.

## Outputs

- Keep each canon's outputs in its own folder under `generated/`, named for the canon file (for example, `generated/dev-env-setup/`). Do not overwrite outputs for another canon.
- Write documentation as HTML fragments only. Do not add `<html>`, `<head>`, or `<body>` wrappers.
- Maintain a `manifest.json` in the same output folder. Each page entry records `id`, `title`, `style`, `mutations`, and `omissions`; the page filename must be `<id>.html`, and declared deviations must match the page content exactly.
- Normally create one page per style. If an additional variation is requested, create a distinct page and manifest entry rather than replacing a style page.
- Before editing generated files, inspect their current contents and preserve user or formatter changes that are unrelated to the request. Do not modify canon or style files unless explicitly asked.

## Validation

- Confirm the expected output files exist and every manifest `id` maps to a page.
- Parse `manifest.json` as JSON and check style coverage and deviation records.
- Check that HTML is fragment-only, facts agree with the canon except for declared deviations, and each procedure follows the canon's step order.
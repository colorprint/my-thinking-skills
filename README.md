# my-thinking-skills — personal Claude marketplace (full bundle)

Self-contained marketplace that ships **ngmeyer-skills** (all 10 of Neal Meyer's
thinking/engineering skills, including council-review / DMAD) as one plugin via a
relative path. Self-contained layout = most compatible with Cowork's
"Add marketplace" flow (no cross-repo source to resolve).

## Install in Cowork

1. Push this repo to a **public** GitHub repository.
2. Cowork -> Customize -> Plugins -> "+" -> Add marketplace -> `<you>/my-thinking-skills`.
3. Install the `ngmeyer-skills` plugin. All 10 skills load; toggle off any you don't want.

## Auto-update from upstream

`.github/workflows/sync-upstream.yml` runs daily (and on demand via Actions ->
Run workflow). It mirrors `skills/` and the plugin manifest from
`ngmeyer/skills@main` into this repo and commits if anything changed. Because the
plugin source is a relative path with no pinned version, each such commit is a new
plugin version Cowork can update to.

Chain: author pushes -> Action mirrors here -> new commit -> Cowork sees new version.

To stop tracking upstream, delete the workflow. To pin, add a `version` to
`plugins/ngmeyer-skills/.claude-plugin/plugin.json`.

Credit: skills by Neal Meyer (github.com/ngmeyer/skills), MIT.

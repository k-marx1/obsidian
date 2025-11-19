# Repository Guidelines

## Project Structure & Module Organization
The vault root groups one folder per course (`Концепции современного естествознания`, `Теоретическая механика`, `Химия`, etc.), each holding the canonical `Лекции.md`, `Практика.md`, and optional dated notes such as `19.11.md`. Shared diagrams live in `Excalidraw/` as `.excalidraw.md` canvases, while export-ready assets go under `images/` (create subject subfolders when needed). Obsidian workspace metadata sits in `.obsidian/`; leave it untouched so personal settings do not leak into version control.

## Build, Test, and Development Commands
- `obsidian .` — opens the vault in Obsidian to preview backlinks, canvases, and callouts before committing.
- `rg -n "энтропия" "Техническая термодинамика в химической технологии/Лекции.md"` — search for terminology so cross-course references stay consistent.
- `git status && git diff` — review staged and unstaged changes; these notes are lengthy and easy to modify accidentally.

## Coding Style & Naming Conventions
Write Markdown with a single `#` title per file, `##` subsections for topics, numbered lists for derivations, and bold emphasis for key terms. Keep paragraphs short so both Obsidian and GitHub render cleanly. Use double-square-bracket wiki links (`[[Экология/Практика]]`) with exact folder names. File names stay in Russian (`Лекции.md`, `Практика.md`, `19.11.md`), and canvases follow `Drawing YYYY-MM-DD HH.MM.SS.excalidraw.md`.

## Testing Guidelines
There is no automated suite; manual validation is the release checklist. Preview edits in Obsidian to confirm headings, LaTeX blocks, and embeds render correctly. Run `rg -n "\[\[" <folder>` to ensure every new wiki link points to an existing note. For assets, verify that image paths resolve in both Obsidian (`![[…]]`) and GitHub (`![]()`), adjusting relative paths before committing.

## Commit & Pull Request Guidelines
Match the current history style: `vault backup: YYYY-MM-DD HH:MM:SS`. Group updates by course so future bisects stay meaningful and mention major additions (e.g., “конспект по энтропии”). Pull requests should summarize the scope, list affected folders, link related tasks, and note how you validated the Markdown (Obsidian preview, `rg` link check, etc.). Attach screenshots whenever Excalidraw canvases or complex figures change.

## Asset & Linking Tips
Keep raw `.excalidraw` canvases in `Excalidraw/` and export PNG/SVG derivatives into `images/<course>/`. Reference them via relative paths so GitHub previews work alongside Obsidian embeds. Reuse asset paths when the same image appears in multiple notes to avoid divergence. Leave `.obsidian/` plugin lists untouched unless coordinating a shared workspace change, and document the rationale whenever they are updated.

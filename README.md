# SQL Path — Interactive course (`index.html`)

A single-file, browser-based SQL course. Lessons run **real [SQLite](https://www.sqlite.org/)** in the page via **[sql.js](https://sql.js.org/)** (WebAssembly). There is no backend server and nothing to install.

**Main file:** [`index.html`](index.html)

## How to open it

1. Double-click `index.html`, or open it from your editor’s “Open in browser” action.
2. The first load needs **internet access** so the page can fetch sql.js from [jsDelivr](https://www.jsdelivr.com/) (`sql-wasm.js` + `sql-wasm.wasm`).
3. Use a current **Chrome**, **Edge**, or **Firefox**.

### Offline use

Download `sql-wasm.js` and `sql-wasm.wasm` from the [sql.js releases](https://github.com/sql-js/sql.js/releases) (match version **1.11.0** with the URLs in the file), place them next to `index.html`, and change the `<script src="…">` and `locateFile` URL in the HTML to relative paths.

## What you get

- **Learn** steps: read in the left panel, then **Continue**.
- **Practice** steps: write SQL in the editor, **Run** to try it, **Check** to validate against the assignment (you may get specific feedback).
- **Mini-lab** steps (end of most units): checklist only; the checker gives **pass/fail** style messages without teaching the solution.
- **Capstone** (final step): larger solo project with automated checks.

Progress is **linear**: the next lesson stays locked until the previous one is completed.

## Curriculum (16 units + capstone)

| Unit | Topics |
|------|--------|
| 1 · Foundations & DDL | Relational basics, types, `CREATE TABLE`, inserts, early `SELECT` |
| 2 · Filtering rows | `WHERE`, `AND`/`OR`, `IN`, `BETWEEN`, `LIKE` |
| 3 · Sorting & NULL | `ORDER BY`, `LIMIT`/`OFFSET`, `DISTINCT`, `NULL` |
| 4 · Changing data | `INSERT`, `UPDATE`, `DELETE`, `INSERT…SELECT` |
| 5 · Keys & relations | Primary/foreign keys, composite keys |
| 6 · JOINs | Inner/left joins, joins with aggregates |
| 7 · Aggregates | `GROUP BY`, `HAVING`, `SUM` / counts |
| 8 · Subqueries & CTEs | `IN`, `EXISTS`, `WITH` (CTEs) |
| 9 · UNION & cleanup | `UNION`, `COALESCE` / `NULLIF` |
| 10 · Constraints & indexes | `CHECK`, `UNIQUE`, `CREATE INDEX`, `EXPLAIN` concepts |
| 11 · Transactions | `BEGIN`, `COMMIT`, `ROLLBACK`, batch safety |
| 12 · CASE & dates | `CASE` expressions, `strftime` / date handling |
| 13 · Window functions | `ROW_NUMBER`, `SUM() OVER`, partitions |
| 14 · Upsert | `ON CONFLICT DO UPDATE` / idempotent writes |
| 15 · Self-joins | Same-table joins, org-style data |
| 16 · Capstone | End-to-end schema + views (school enrollment) |

Units **1–9** and **10–15** each end with a **mini-lab**; **16** is only the capstone.

There are **67** steps total (including learn, practice, mini-labs, and the final capstone).

## Editor shortcuts

| Action | Shortcut |
|--------|----------|
| Run SQL | **Ctrl+Enter** (Cmd+Enter on macOS) |
| Check answer | **Shift+Ctrl+Enter** |
| Indent | **Tab** (two spaces); **Shift+Tab** outdents |

## Progress and XP

- Completion and **XP** are stored in the browser under the key **`sql-path-progress-v4`** (`localStorage`).
- Clearing site data for the file’s origin resets progress.
- If the course structure changes in a future version, the progress key may be bumped; older keys will not apply to a new layout.

## Maintainer note: splicing curriculum

[`splice_curriculum.py`](splice_curriculum.py) is a small helper that can replace the `/* ——— Curriculum ——— */` block in `index.html` with the contents of a separate text file. The authoritative curriculum in this repo is **inside** `index.html`; the script is optional for bulk edits.

## License / credits

- Course content and HTML: your project.
- **sql.js** / SQLite: see the [sql.js](https://github.com/sql-js/sql.js) and [SQLite](https://www.sqlite.org/copyright.html) projects.

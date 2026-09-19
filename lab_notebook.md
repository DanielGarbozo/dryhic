# lab_notebook.md, dryhic

Session log. Entry format (what `/checkpoint` fills in when closing a session):

```
## YYYY-MM-DD
**Summary**: what got done today (EDA/modeling/infra).
**New skill**: one concrete thing learned (e.g. "pandas groupby", "why git doesn't track
empty directories").
**Biological question resolved**: if applicable. If the session was pure infrastructure,
"N/A (infra session)".
**LinkedIn post idea?**: yes/no plus about what, if there's a real biological insight worth
it.
**Where we left off**: so the next session doesn't waste time rebuilding context.
```

---

## 2026-09-19
**Summary**: Phase 0 complete. `dryhic` repo created on GitHub (private), folder scaffold
(`notebooks/`, `src/`, `data/`, `figures/`, `results/`), `.gitignore`, `environment.yml`
(conda, Python 3.11 plus pandas/sklearn/xgboost), `CLAUDE.md` with the experimental design
migrated from `ml-portfolio/README_NEXT_SESSION.md`. Also generalized
`checkpoint.md`/`feynman.md`/`session-start.md` in `ml-portfolio` (were hardcoded to the old
TCGA-BRCA project) and built `/new-ml-project` and `/progress`.

**New skill**: why a git repo plus a conda env shouldn't live inside a Google Drive/OneDrive/
Dropbox sync folder (broken symlinks, `index.lock` conflicts); the difference between a
`drvfs` mount (Windows drive mounted in WSL) and a native Linux filesystem; git doesn't
track empty directories (hence `.gitkeep`); the `gh repo create --source=. --remote=origin
--push` flag combo; heredocs (`cat > file << 'EOF'`) pasted from a Windows clipboard into
WSL bash can break on CRLF line endings, so the closing `EOF` doesn't match and ends up as
literal file content (happened with `.gitignore`, fixed).

**Biological question resolved**: N/A (infra session).

**LinkedIn post idea?**: not yet. Wait for a real result (Phase 1 onward).

**Where we left off**: the repo was first created by mistake in
`/mnt/u/My Drive/github/dryhic` (Google Drive mounted as drive U:) and migrated to
`/mnt/c/Users/soyda/Documents/github/fcc/dryhic` with no data loss. Data architecture
decided: raw BAM/FASTQ stay on the lab's server/HPC (Daniel confirmed it exists and he has
access), never copied to either laptop; only small derived outputs travel between his two
computers. `CLAUDE.md` is gitignored (holds unpublished strain-level detail) and kept as a
local-only file, backed up separately to Drive by Daniel. Still open: set up SSH access to
the lab server from both machines (next session or when Phase 1 starts).

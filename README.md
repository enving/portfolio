# enving / portfolio

This **meta‑repository** aggregates all of my demo repositories as **Git submodules**.  Each submodule lives in its own subdirectory, so the full source code of every project is available in one place while the individual repositories keep their own history and issue tracking.

## Submodules

| Submodule | Description |
|-----------|-------------|
| `open-webui` | User‑friendly AI Interface (Svelte) |
| `docs`       | Documentation site |
| `mcpo`       | MCP‑to‑OpenAPI proxy server |
| `pipelines`  | UI‑agnostic OpenAI plugin framework |
| `desktop`    | Desktop client (Alpha) |
| `.github`    | GitHub configuration (templates, workflows) |

> When cloning this repo, use `git clone --recurse-submodules …` so that all submodule contents are fetched automatically.

---

### How to work with the submodules

* **Update a submodule** (e.g. after a new commit in `open-webui`):
  ```bash
  cd open-webui
  git pull origin main   # fetch latest
  cd ..
  git add open-webui
  git commit -m "Update open-webui submodule"
  git push
  ```
* **Add a new submodule** – see the script below.

---

#### Adding the submodules (run once)

```bash
# from the repository root (portfolio)
git submodule add https://github.com/enving/open-webui.git open-webui
git submodule add https://github.com/enving/docs.git docs
git submodule add https://github.com/enving/mcpo.git mcpo
git submodule add https://github.com/enving/pipelines.git pipelines
git submodule add https://github.com/enving/desktop.git desktop
git submodule add https://github.com/enving/.github.git .github

git add .gitmodules
git commit -m "Add all demo repos as submodules"
git push origin main
```

---

Now you have a single entry point (`enving/portfolio`) that shows all your projects together, while each project remains a first‑class GitHub repository.

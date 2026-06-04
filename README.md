# copier-python-uv

A minimal [Copier](https://copier.readthedocs.io) template for my uv-based Python
projects — both reusable **packages** (published to PyPI, Sphinx docs on Read the
Docs, carthorse releases) and standalone **apps** (CLI entry point, no publishing).

It encodes the conventions shared across my libraries (chide, sybil) and apps
(chimera): `src/` layout, hatchling, `[dependency-groups]`, ruff, pytest + 100%
coverage, a `happy.sh` quality gate, Sybil-tested `.rst` docs, and CI that defers to
the `cjw296/python-workflow` reusable workflows.

## Create a project

```bash
uvx copier copy gh:cjw296/copier-python-uv ./my-thing --trust
```

`--trust` lets the template, after generation, run `git init` + `uv sync` and make
an initial commit of the generated layout. `copier update` skips the init/commit.

## Update an existing project

From inside a generated project, pull in later template improvements:

```bash
uvx copier update --trust
```

This works because each generated project records its answers in
`.copier-answers.yml`.

## Questions

| Question | Notes |
|---|---|
| `project_type` | `package` (PyPI + docs + release) or `app` (CLI, no publishing) |
| `project_name` | Human-readable; the kebab `project_slug` and snake `package_slug` derive from it |
| `python_version` | Minimum for packages, target for apps |
| `type_checker` | `mypy` (default for packages) or `ty` (default for apps) |

# AI Setup Template Repo

This repository packages a reusable AI collaboration setup that can be copied into another software project and adapted there.

The root of this repository explains the template package itself. The reusable files that consumers should copy live in [`template/`](./template).

## What This Repo Contains

- [`template/AGENTS.md`](./template/AGENTS.md): baseline agent operating rules for a target project.
- [`template/README.md`](./template/README.md): source-of-truth and context-loading guide intended for the target project.
- [`template/.codex/config.toml`](./template/.codex/config.toml): optional project-level Codex config with a small starter set of MCP servers. Remove entries you do not want in the target project.
- [`template/docs/`](./template/docs): workflow and documentation conventions for spec-driven delivery.
- [`template/skills/`](./template/skills): reusable review and quality-check skills.
- [`template/ui-templates/`](./template/ui-templates): reserved space for reusable UI starter assets.

## How To Use It

1. Copy the contents of [`template/`](./template) into the root of your project.
2. Review `AGENTS.md` and `README.md` first, then adjust them to match your stack, workflows, and constraints.
3. Review `.codex/config.toml` and remove any MCP servers or Codex settings you do not want before using the template in a target project.
4. Update the docs in `docs/` so they describe your actual project rather than this starter baseline.
5. Remove parts you will not maintain. A smaller, accurate setup is better than a larger stale one.

## What To Customize First

- Project goal and scope in `README.md`
- Stack- or framework-specific rules in `AGENTS.md`
- Optional MCP servers and Codex settings in `.codex/config.toml`
- Delivery workflow in `docs/spec-driven-delivery.md`
- UI/style guidance in `docs/frontend-style.md`
- Any skills that reference tools, directories, or workflows your project does not use

## Repo Layout

```text
.
├── README.md
└── template/
    ├── .codex/
    ├── AGENTS.md
    ├── README.md
    ├── docs/
    ├── skills/
    └── ui-templates/
```

## Maintainer Notes

This repository is template-focused. There is currently no root-level application to build, run, or test.

When changing template behavior or guidance, treat these files as the primary source of truth:

1. [`template/AGENTS.md`](./template/AGENTS.md)
2. [`template/README.md`](./template/README.md)
3. Task-relevant normative docs referenced from `template/README.md`

Keep the root README repo-specific, and keep reusable consumer-facing assets under `template/`.

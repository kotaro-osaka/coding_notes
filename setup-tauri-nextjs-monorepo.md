# Setup Tauri-Next.js Monrepos
___
## npm config file `.npmrc`
> `/.npmrc`
- `registry=https://registry.npmjs.org/` Default registry to pull packages from
- `package-manager=pnpm@10.12.1` Default package manager
- `auto-install-peers=true` Ensure host project provides certain packages
- `public-hoist-pattern[]=*eslint*` Hoist eslint-related packages to root

## pnpm workspaces
> `/pnpm-workspace.yaml`

```yaml
packages:
	- 'apps/*'
	- 'packages/*'
```

## turbo.json
> `/turbo.json`
```json

```

## package.json
> `/package.json`
```json

```

> [!info]
> Extend and add onto `package.json` in subfolders by specifying `"extends": "/path/to/base.json"`



> [!info]
> Avoid sharing whole monorepo with webhost by setting up a filtered deployment branch
> 1. 
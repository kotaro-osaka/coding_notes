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
> Extend and add onto `package.json` in subfolders by specifying `"extends": "/"`

## To do
1. `.npmrc`: look through all options or conventions from google etc.
2. `package.json`: look through all options or conventions from google etc. (incl `packageManager`)
3. ![[99 - misc/Pasted image 20250608190203.png]]
	- (extends pattern)
4. 
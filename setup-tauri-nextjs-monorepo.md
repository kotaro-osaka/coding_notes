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
{
    "$schema": "https://turborepo.com/schema.json",
    "ui": "tui",
    "tasks": {
        "build": {
            "dependsOn": ["^build"],
            "inputs": ["$TURBO_DEFAULT$", ".env*"],
            "outputs": [".next/**", "!.next/cache/**"]
        },
        "lint": {
            "dependsOn": ["^lint"]
        },
        "check-types": {
            "dependsOn": ["^check-types"]
        },
        "dev": {
            "cache": false,
            "persistent": true
        },
        "clean": {
            "cache": false
        }
    }
}
```

## package.json
> `/package.json`
```json

```

> [!info]
> Extend and add onto `package.json` in subfolders by specifying `"extends": "/path/to/base.json"`







# Protocol
___
> [!info]
> Avoid sharing whole monorepo with webhost by setting up a **filtered deployment branch**
» `turbo prune --scope=web` to create a folder including the bare minimum of `apps/web` and deploy that using CI


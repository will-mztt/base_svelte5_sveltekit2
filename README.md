# Svelte & SvelteKit

This is a sample base project using Svelte 5.0 and SvelteKit 2.0 **without TypeScript support** and using `pnpm` as package manager.

## Debugging on VS Code and Chrome

Debugging "_non-transpiled_" code on both VS Code and Chrome is functional on this version of the project.

### `.vscode/launch.json`

These configurations were copied from [an issue on SvelteKit official GitHub from 2023](https://github.com/sveltejs/kit/issues/7781#issuecomment-1634140560).

```
{
	"version": "0.2.0",
	"configurations": [
		{
			"name": "Launch server",
			"request": "launch",
			"runtimeArgs": ["dev"],
			"runtimeExecutable": "pnpm",
			"skipFiles": ["<node_internals>/**"],
			"type": "node",
			"console": "integratedTerminal"
		},

		{
			"type": "chrome",
			"request": "launch",
			"name": "Launch browser",
			"url": "http://127.0.0.1:5173",
			"webRoot": "${workspaceFolder}"
		}
	],
	"compounds": [
		{
			"name": "Both",
			"configurations": ["Launch server", "Launch browser"]
		}
	]
}
```

Aside from these configurations, changes were made to the files `vite.config.js` and `svelte.config.js` to ensure sourcemap generation is explicitly set to `true`.

## Debugging on Firefox

When using Firefox, debugging is only working on the browser's DevTools.

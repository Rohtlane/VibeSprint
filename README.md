# Connected — The Life Game

The complete editable app is in [connected-life-source.zip](connected-life-source.zip). Download that file and extract it first; the source files are inside the archive, not at this repository root.

## Continue with Claude

1. Download and extract connected-life-source.zip.
2. Open the extracted folder in Claude Code or your editor.
3. Read HANDOFF.md for project context and README.md for setup.
4. With Node.js 24 and npm installed, run `npm run install:ci`, then `npm run dev`.
5. Open http://localhost:5173.

The archive includes the game source, assets, lockfile, tests, database migration and developer handoff. No paid AI API or original Codex chat is required. It excludes credentials, node_modules, saved games and local databases.

This repository currently stores a source snapshot as a ZIP. Extract the files into a working checkout before editing; a normal Git clone alone does not unpack the app. The included README explains building and local classroom setup. The existing hosted game remains separate and private.

# Field Of Vision Agents

A small shared library of roles for Unity game projects.

## Roles

- Game Designer
- Level Designer (starting point for Bob)
- Unity Architect (starting point for Fox)
- Unity Editor Tool Developer
- Technical Artist
- Game Audio Engineer
- Narrative Designer
- Economy Designer
- Reality Checker (starting point for Game QA)

## Usage

Choose the roles a project needs from `roles/`. When asking an agent to use a role, point it to that file and the relevant project documents.

Keep game briefs, mechanics, level design guides, and project-specific role instructions in each game repository. Project-specific instructions take precedence over shared role defaults.

The role definitions are adapted from Agency Agents, with shared XR guidance added for Field Of Vision projects.

## XR projects

All roles link to the [shared XR workflow](guides/xr-workflow.md). Copy the [XR setup template](templates/xr-setup.md) into each game's `docs/xr-setup.md` and fill it in there.

Installing this package makes the documents available; it does not activate roles or connect tools. Add a short instruction to the game's agent entry point identifying `com.fieldofvision.agents`, the relevant role files, and the game brief. For XR work, also point to the shared guide and the game's XR setup.

The Unity Project window shows the package under `Packages/com.fieldofvision.agents`; a Git installation is typically stored physically in `Library/PackageCache`. Agents should locate the installed package rather than hardcode a cache directory name. Keep game-specific edits in the game repository.

## Attribution

Role definitions copied from [Agency Agents](https://github.com/msitarzewski/agency-agents), using the local downloaded copy. Original copyright and MIT license are retained in `LICENSE`.

# Neuro Example Project

A small idle/crafting game ("Craft Clicker") that exercises most of
[Neuro](https://github.com/Ninjadini/Neuro) in one place: `Referencable` config types,
`Reference<T>` links, status effects via inheritance, content validators, player progress saving,
and the Neuro editor window.

This is a full Unity project rather than a folder of assets, which is why it lives in its own
repository instead of shipping inside the package — it needs its own `ProjectSettings` (URP render
pipeline assets, Input System actions) and a `NeuroData/` folder at the project root, outside
`Assets/`.

## Getting started

```
git clone https://github.com/Ninjadini/NeuroExampleProject.git
```

Open the cloned folder in Unity **6000.6 or newer**. The Neuro package is pulled from git
automatically on first open, so there is nothing else to set up.

Open `Assets/Scenes/CraftClicker.unity` and press Play.

## What to look at

| Path | What it shows |
| --- | --- |
| [`Assets/Scripts/CraftClicker/Model/`](Assets/Scripts/CraftClicker/Model/) | The Neuro data model |
| [`Assets/Scripts/CraftClicker/CraftClickerLogic.cs`](Assets/Scripts/CraftClicker/CraftClickerLogic.cs) | Loading, modifying and saving player data |
| [`Assets/Scripts/CraftClicker/UI/`](Assets/Scripts/CraftClicker/UI/) | Displaying the state of the game |
| [`Assets/Scripts/CraftClicker/Editor/`](Assets/Scripts/CraftClicker/Editor/) | Content validators and the content debugger |
| [`NeuroData/`](NeuroData/) | The authored content, as Neuro JSON |

Full walkthrough: [Docs/DemoProject.md](https://github.com/Ninjadini/Neuro/blob/main/Docs/DemoProject.md)

## Working against a local Neuro checkout

To test changes to the package itself, clone both repos side by side:

```
Workspace/
├── Neuro/                  # github.com/Ninjadini/Neuro
└── NeuroExampleProject/    # this repo
```

then point `Packages/manifest.json` at the local copy:

```json
"com.ninjadini.neuro-unity": "file:../../Neuro",
```

Don't commit that line — the git URL is what makes this repo work for everyone else.

> **Note:** don't put the project under a folder whose name ends in `~` (or starts with `.`).
> Unity treats those as hidden and the editor fails to resolve types out of package assemblies,
> which silently empties component inspectors.

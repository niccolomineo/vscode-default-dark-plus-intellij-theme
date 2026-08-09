## v1.5.3

- Clear `activityBarTop.activeBorder` so the selected view icon in a side bar tab strip is marked by the active pill alone, instead of carrying a redundant accent underline on top of it — this also matches what Modern UI already forces on the secondary side bar, where the same underline is hardcoded to transparent
- Set `sideBarActivityBarTop.border` explicitly to `#FFFFFF1A` so the edge under the tab strip uses the card idiom shared by `sideBar.border`, `panel.border` and `titleBar.border`, rather than inheriting the lighter `sideBarSectionHeader.border`

## v1.5.2

- Align `sideBarTitle.foreground` with `activityBarTop.foreground` so a side bar view icon hovers the same color whether it's the only pinned view (title mode) or one of several (Modern UI's own tab strip mode)

## v1.5.1

- Align the title bar to the card tone (`#242424`) so it matches the status bar, activity bar, sidebar and panel instead of the editor canvas
- Add `commandCenter.*` colors so the Command Center pill reads as an elevated element rather than inheriting the title bar background
- Add `activityBarTop.*` colors, which are the ones VS Code actually uses when `workbench.activityBar.location` is `top` or `bottom` — previously only `activityBar.*` was covered, leaving that layout unthemed
- Add `activityBar.activeBackground` so the selected composite-bar tab pill no longer depends on the `list.inactiveSelectionBackground` fallback
- Add `toolbar.hoverBackground` and `toolbar.activeBackground` so toolbar icons share the same hover and active tones as the composite-bar tabs instead of the lighter translucent defaults
- Add `panelTitle.*` colors so the Terminal / Problems / Output tabs use the theme palette and accent for their hover and active states, instead of the brighter `#E7E7E7` default
- Document in the README that on macOS the `titleBar.*` and `commandCenter.*` colors only apply with the custom title bar style

## v1.5.0

- Adapt to VSCode 1.129 "Modern UI": harmonize sidebar, activity bar, panel and status bar to a single card tone (`#242424`) so floating cards read as one coherent set against the editor canvas
- Add `activityBar.border` and `panel.border` for clean card edges and rounded corners
- Add `install-local` package script to build and install the extension locally in one step

## v1.4.0

- Expand workbench UI coverage (title bar, tabs, lists, inputs, widgets, scrollbars, editor diagnostics, Git decorations, 16 ANSI terminal colors)
- Manifest hygiene: migrate to `@vscode/vsce` dev dependency, drop committed `__metadata`, bump `engines.vscode`, add `keywords`, `license`, `homepage`, `bugs` and package scripts
- Add MIT `LICENSE`, expand README, add CI publish workflow

## v1.3.3

- More bold restoration for #CC7832 tokens

## v1.3.0

- Move some tokens to different color
- Group token scopes by setting

## v1.2.0

- Rename theme
- Revamp icon

## v1.1.7

- Style status bar when no folder is open

## v1.1.6

- Change icon

## v1.1.5

- Add more styling fixes

## v1.1.4

- Make sidebar panels style consistent

## v1.1.2

- Initial release

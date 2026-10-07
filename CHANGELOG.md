## v1.5.8

- Add `editorGroupHeader.connectedTabsBackground` at the card tone (`#242424`) so VSCode 1.141's connected editor tabs actually read as connected: the active tab keeps the editor canvas (`#1E1E1E`) and joins its content, while the strip behind it steps back — previously the strip inherited `editorGroupHeader.tabsBackground` (`#1E1E1E`), so strip, tab and editor were one flat color and only the `#FFFFFF1A` outline marked the active tab. The token only applies to Modern UI's connected tab style, so the classic tab bar is unchanged

## v1.5.7

- Make the icon full-bleed: the squircle now touches all four edges of the 512×512 canvas instead of sitting inside a 40 px transparent margin, so the extension no longer renders visibly smaller than its neighbours in the Extensions view and on the Marketplace
- Drop the outer drop shadow, which is what the margin existed for, and lighten the body ramp to `#585858 → #383838 → #282828` so the lower edge still separates from the dark chrome now that nothing sits behind it
- Scale the code lines with the tile so they keep occupying half its width, and return `icon.png` to 512×512 — the 1024×1024 export of v1.5.6 tripled the asset for no visible gain

## v1.5.6

- Redraw the extension icon as an Apple-style squircle — a rounded rectangle with superelliptic corners replaces the circle the old asset inherited from its vector-editor export, which also carried the geometry as opaque transform matrices rather than plain coordinates
- Relight the icon from above: a vertical gradient and a specular sheen replace the off-centre radial fill, an inner bevel runs from white at the top edge to black at the bottom, and a soft drop shadow lifts the shape off both light and dark backgrounds
- Recolor the icon's code lines with the theme's own token colors — `#CC7832` keywords, `#639250` strings, `#FFC66D` functions, `#6897BB` numbers, `#9476A5` properties and `#BEBEBE` editor foreground — in place of approximations that matched no scope in the theme
- Ship `icon.png` at 1024×1024 rather than 512×512, so the Marketplace and the Extensions view have a source large enough for every display density
- Add the icon to the top of the README, ahead of the title, so it is the first image in the file and gets picked up as the product image instead of the screenshot

## v1.5.5

- Add `surface.background`, `surface.border` and `surface.foreground`, the tokens VSCode 1.133 uses to paint the framed "card" containers — they override `sideBar.border` with `!important`, so the card edge that the whole v1.5.x chrome is built around was being drawn by their defaults rather than by the theme
- Add `sideBar.foreground`, which was unset despite being the default source for both `surface.foreground` and `sideBarSectionHeader.foreground`
- Migrate `editorIndentGuide.background` and `editorIndentGuide.activeBackground` to the `background1` / `activeBackground1` keys that replaced them, clearing two deprecation warnings
- Give editor tabs an explicit text ramp — `tab.activeForeground`, `tab.hoverForeground`, `tab.inactiveForeground`, `tab.unfocusedActiveForeground` and `tab.unfocusedInactiveForeground` now step through the theme's own tones instead of inheriting translucent-white derivations, and `tab.border` uses the card edge so tab separators are visible at all
- Cover the `statusBarItem.*` interaction states — hover, active and compact-hover now use the same raise the toolbar already uses, and `prominentBackground` replaces a default of black at 50% opacity that read as a near-black blob on the theme's dark status bar rather than as emphasis
- Add `statusBar.border` so the status bar has the same card edge as the title bar, side bar, panel and activity bar, and point `statusBar.focusBorder` / `statusBarItem.focusBorder` at the accent instead of plain white
- Tint the debugging status bar with the Darcula keyword orange (`#CC7832`) and dark text, replacing the slightly duller stock `#CC6633`

## v1.5.4

- Color Python's `cls` with the same purple as `self` — both the usage and the parameter scope were missing, so a classmethod's first argument fell back to the default foreground
- Refresh the screenshot, which still showed the pre-v1.5.0 chrome: the card tone is now `#242424` throughout with `#FFFFFF1A` edges, types use the correct `#4EC9B0`, and the activity bar's selected item shows the theme's own pill instead of an invented accent bar
- Drop the macOS title bar note from the README

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

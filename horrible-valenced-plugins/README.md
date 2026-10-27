# horrible-valenced-plugins

Valenced ports of the horrible-kettu-plugins collection. Built from the
[Valenced plugin template](https://github.com/Valenced/valenced-plugin-template).

## Plugins

| Folder | ID | Description |
| --- | --- | --- |
| `plugins/fake-voice-state` | `dev.21aansell-sketch.fake-voice-state` | Look muted/deafened in a call while you can still hear and talk. `/fakemute`, `/fakedeafen`. Needs Coco's Command Lib. |

## Adding a plugin

Create `plugins/<name>/` with a `manifest.json`, a `tsconfig.json` (`{ "extends": "../../tsconfig.base.json" }`) and a `js/index.ts` that exports `plugin({ ... })`.
Plugin IDs are permanent, so pick them once.

## Build

```sh
bun install            # or npm install --legacy-peer-deps
bun run lint:types     # typecheck every plugin
./gradlew packageAllPlugins   # ZIPs end up in build/dist/
```

Packaging needs JDK 25+, the Android SDK and a GitHub token with `read:packages`
(see the template docs: https://valenced.app/docs/plugin-development/getting-started/the-plugin-template).

## Publish

Release ZIPs are listed in an `index.json` made by `valenced-plugin generate-index`; the GitHub Actions
workflows in `.github/` do this for you. Users add the published `index.json` URL under
**Settings > Valenced > Plugins > gear > Add repository**.

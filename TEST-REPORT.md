# Study Town v2 — Repair and verification report

## Confirmed defect in original v1

- Original game declared top-level `let location='town'`. In Chromium this conflicts with browser `window.location`, causing a JavaScript startup error: `Identifier 'location' has already been declared`. The main game failed to initialize.
- Repaired by using `currentPlace` throughout game state.

## Other repaired issues

- Avatar dropdown choices previously only saved data, with nearly all choices producing no visible change. The shared canvas sprite adapter now visually updates hair color, skin tone, outfit tint, limited hairstyle silhouettes, and a few accessory overlays. The same adjusted sprites render in the editor, home, and game world.
- Location interactions with locked buildings now give a clear unlock requirement, not a silent failed Visit action.
- More defensive loading and restore for older or partially missing v1 save fields.
- Better small-screen navigation, avatar editor layout, and UI scaling.
- More accurate messaging when launching academic tools: direct deep-linking to particular dashboard tabs is not implemented.
- World rendering is skipped when hidden; game state persists under its existing key.

## Executed tests (isolated Chromium, desktop 1280×900 and mobile 390×844)

- Game startup, initial canvas drawing and no JavaScript page errors.
- All seven game navigation sections displayed and switched correctly.
- Pixel avatar hair color and outfit changes produced distinct canvas images.
- Enter Library, interact, close dialog, return to Town Square.
- Market category filters and pet listings.
- Academic XP reading (70 XP → 140 tickets), one food purchase and balance change.
- Pet purchase, selection, feed and 72-hour revival.
- Mobile D-pad movement changed avatar position.
- Enter Garden Park, open fishing, obtain collectible.
- Local save readback preserved the pet, appearance, item collection and expenditures.
- Partial older save data retained safe defaults without crashing.
- Main dashboard v105 inline JavaScript syntax check passed, and Study Town launcher link is present.

## Verification boundaries

- The browser tests loaded the project's identical HTML, CSS, and JavaScript with pixel images embedded as test data URLs; they did not navigate to GitHub Pages because local browser URL navigation was restricted. This checks interaction logic and layouts but does not prove GitHub Pages deployment or caching behavior.
- Tests do not cover every possible long play session, external GitHub Pages environment, actual Android/iPad touchscreen or Apple Pencil, cross-device synchronization, or every imported data variant.
- The original dashboard itself was only syntax-checked for this release, not exhaustively regression-tested. Its launcher code is reused from v105 without logic changes.

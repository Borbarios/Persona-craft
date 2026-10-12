# Persona Craft: handoff to Claude Code / Codex

Paste this together with a FRESH Publish prompt from Melty (it holds your token; never put the token in files).

## Decisions already made (do not re-ask)
- Idea: Steve plays in a Persona-style world (Tokyo/Metaverse), uses Personas like in Persona 5 Royal, and can still place blocks.
- Host (role primary): Minecraft Java, Fabric, via portable Prism instance.
- Companion (role companion): Persona 5 Royal. Melty gives its folder as {game:persona-5-royal}. Read music/Persona data from the player's copy at runtime. Copy nothing from it into the mod or upload. No stand-ins.
- First minute: spawn in metaverse_tokyo, get starter Persona, cast a skill, place blocks.
- Mode: solo. License: MIT. Remix: allowed.
- v1 is small: 1 dimension, 1 Persona, 1 skill, SP bar, music from P5R install.

## Work to do
1. Connect to Melty, call list_my_mods, search_mashups, game_info for both games, mashup_info on skycraft.
2. Read sheets/*.json. They are the source of truth: change the sheet first, then code. Fill every "TO_VERIFY" cell by inspecting the installed games. Preflight before each build.
3. Find both install folders, work out how P5R stores music and data, pick a route and tell the user.
4. Build the Fabric mod, test in game, capture a real screenshot of Steve using the Persona skill.
5. inspect_package, validate_recipe, one_click_check, create_mod, upload, submit_release, add_screenshot, test_release.
6. Show the user a summary and ask before calling publish.

## Known risks
- P5R music/model formats are proprietary. If runtime reading is blocked, explain it and get the user's agreement before changing the design.
- Do not use the P5R-as-host option unless the user asks.

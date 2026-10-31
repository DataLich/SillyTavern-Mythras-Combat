# Mythras Combat Companion for SillyTavern

**Early prototype (v0.1.0). Not a complete implementation of Mythras rules.**

A third-party SillyTavern UI extension providing editable character/NPC stat sheets, character-card name import, a basic opposed attack/defense roller, per-location armor and HP, a combat tracker, and optional NPC generation using a separate OpenAI-compatible API.

## Install

Copy this folder to `SillyTavern/public/scripts/extensions/third-party/mythras-combat-companion/` and restart/reload SillyTavern. Open the floating **Mythras** button. For Git installation, use SillyTavern's Extensions > Install extension and provide your published GitHub repository URL.

## Usage

- **Character**: create or import a sheet for the currently selected character card. Import currently uses the card's name, not its full description or existing numeric attributes. Edit stats manually.
- **NPC AI**: configure a separate endpoint/model/key in API Settings, then generate an NPC by name and description. "Suggest NPCs" scans the last 15 chat messages and suggests names for review; it does not silently generate stats or automatically intercept messages.
- **Combat**: add characters, roll initiative, and resolve basic attacks against a defense skill. Damage uses a configurable dice expression and applies location armor.
- **Storage**: extension settings are saved using SillyTavern's settings mechanism. Export/back up SillyTavern settings to preserve sheets.

## Rules scope and limitations

The prototype uses percentile skill tests, hit-location HP and armor, and simplified opposed attack/parry resolution. It **does not yet** implement full Mythras combat procedures, weapon reach/size, action economy, combat styles, differential success levels, special effects, wound effects, fatigue, magic, or comprehensive damage modifiers. Initiative is a prototype heuristic. It is **not rules-verified against the uploaded PDF**; consult your licensed rules for play. No rulebook text is redistributed.

## API/security

The secondary API key is stored in SillyTavern extension settings and transmitted from the browser directly to the configured endpoint. This is **not a secret vault**. Use a restricted, low-limit key and trusted HTTPS endpoint; the provider must permit CORS. Do not expose this extension to untrusted users on a shared SillyTavern instance. No credentials are committed to the repository.

## Roadmap

- Full Mythras opposed-roll success tiers and special effects
- Mythras-compliant hit location and weapon damage/armor interactions
- NPC identity reconciliation and automatic (opt-in) background generation
- Card metadata import/export and per-chat campaign persistence
- Secure server-side API proxy and provider presets
- Combat automation hooks, encounter export, and tests

## License

MIT for original extension code. Mythras is a trademark of its respective owners; this unofficial fan project is not endorsed by them.

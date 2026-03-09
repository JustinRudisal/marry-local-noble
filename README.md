# Marry a Local Noble

An EU5 mod that adds the option to marry your dynasty's characters to a randomly generated local noble for a flat cost of **25 ducats**. Useful when there are no suitable suitors available and you refuse to despoil your bloodline with lowborn rabble.

This is an updated and fixed version of [Kaiser's original mod](https://steamcommunity.com/sharedfiles/filedetails/?id=3600093580), rewritten for compatibility with **version 1.1.x**.

## Steam Workshop

*(link to be added after publishing)*

## Features

- Works for both **male and female** recipients
- Created noble shares the recipient's **culture and religion** — they are truly local
- Flat cost of **25 ducats**
- AI will use this interaction to keep old rulers and heirs from going unmarried
- Compatible with all government types (monarchy, republic, tribe, steppe horde; theocracy support gated by church marriage laws)
- Compatible with [Auto Noble Marriage](https://steamcommunity.com/sharedfiles/filedetails/?id=3606305941) — if that mod marries the recipient first, the ducats are refunded instead of leaving an orphaned noble in court

## What was fixed vs the original

| Issue | Original | Fixed |
|---|---|---|
| `effects_l_english.yml` | Entire base-game localization file accidentally included — overrides effect descriptions and crashes 1.1.x | Removed |
| Catholic theocracy check in `potential` | `law_policy:cc_marriage_of_priest = ...` (invalid trigger in 1.1.9) | `international_organization_has_policy = policy:...` |
| `supported_game_version` | `1.0.0` | `1.1.*` |
| Gold cost enforcement | Missing from `allow` block | `gold >= { value = 25 }` |
| Created noble culture | Not set — noble got a random culture | `culture = scope:recipient.culture` |
| Auto-marriage mod conflict | Created orphaned noble if recipient was married in same tick | Guards with `has_available_marriage_slot` and refunds gold if already married |

## Installation

1. Clone or download this repo into your EU5 mod folder:
   ```
   %USERPROFILE%\Documents\Paradox Interactive\Europa Universalis V\mod\
   ```
2. Enable **Marry a Local Noble (1.1 Fix)** in the EU5 launcher
3. Unsubscribe from the original mod if you were using it

## Notes

- Changes the checksum — **no achievements** can be earned with this mod active
- Save compatible — can be added to an existing save

## Contributing

Pull requests welcome. If Paradox changes something that breaks the mod, feel free to open an issue or submit a fix.

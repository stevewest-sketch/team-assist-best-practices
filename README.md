# Team Assist Best Practices

An interactive, single-file microsite that teaches customer-facing teams how to set up, prompt, and run Gladly Team Assist — the buttons to configure, the exact prompts to type, and the plays that put them together. The goal it drives toward: a resolution that holds on the first conversation.

Built for walking a team through in a session, or sharing as a link.

## What's in it

The site is organized in three layers, each building on the last:

- **Layer 1 — the button library.** The pre-canned buttons that open a session, shown with the exact message behind each one. Click any button to expand it. Three fire automatically at session start; the rest are configurable per team.
- **Layer 2 — the prompt library.** The exact statements a team member types when a button isn't specific enough, grouped by task (summarizing, drafting, finding an answer, checking a pattern, and more). Each prompt is paired with what it returns.
- **Layer 3 — the plays.** Sample scenarios that show the buttons and prompts working together — each one starts with a button press, then walks the determinative prompts that pull and distill the context, in the order that reaches a decision fastest.

Supporting sections cover why first-conversation resolution matters, how the three layers fit together, and habits that apply across any play.

## Files

| File | Description |
|---|---|
| `team-assist-best-practices.html` | The microsite. Self-contained — open it directly in any browser. |
| `build_microsite.py` | Build script that generates the HTML, embedding all assets as base64. |
| `README.md` | This file. |

## How it works

`team-assist-best-practices.html` is fully self-contained. Every asset — the Gladly logos, photography, and design-system icons — is embedded as base64, so the file works anywhere with no external dependencies: open it locally, email it, drop it in a shared drive, or host it.

Features:

- Scroll-through, full-viewport sections with a fixed logo that swaps for light and dark backgrounds
- Right-side dot navigation with scroll spy
- Scroll-triggered fade-in animations
- Click-to-expand button library (Layer 1) and plays (Layer 3)

## Viewing

Open `team-assist-best-practices.html` in any modern browser. No build step or server required.

The site is designed for desktop presentation at a 1400px viewport (laptops and projectors), so it's best viewed on a full-size screen rather than a phone.

## Editing the content

To change copy, prompts, buttons, or plays, edit `build_microsite.py` rather than the HTML directly. The content lives in plain Python data structures near the top of the script:

- `default_buttons` and `config_buttons` — the Layer 1 button library
- `prompt_cats` — the Layer 2 prompt library, grouped by category
- `plays` — the Layer 3 scenarios

Then regenerate the HTML:

```bash
pip install Pillow
python3 build_microsite.py
```

The script reads the Gladly brand logos and photography and the design-system icon set, encodes them, and writes `team-assist-best-practices.html`.

## Design

The microsite follows the Gladly brand system — Gladly Green (`#009B00`) as the primary accent, purple (`#8C69F0`) as a secondary accent, and alternating light and dark section backgrounds for rhythm. Product terminology follows Gladly conventions (for example, "team member" rather than "agent," and "conversation" rather than "ticket").

## Status

Internal enablement asset. Content is based on the Team Assist scenario playbook and is iterated with the Revenue Enablement team.

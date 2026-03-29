# Fonts

This folder is for font files bundled with the app so the same typography can be used on other computers or GitHub Pages.

## Included

- `NotoSansTC-VF.ttf`
- `NotoSerifTC-VF.ttf`

These are referenced by `D:\Project\photoFrame\photoFrame.html` through `@font-face`.

## Add more fonts

1. Put the font file in this folder.
2. Add a matching `@font-face` rule in `D:\Project\photoFrame\photoFrame.html`.
3. Add a new option to the font selector.

## Notes

- System fonts like `Courier New`, `Arial`, and `Georgia` do not need to be copied here to work on your computer.
- If you want GitHub Pages visitors to always see the same font, bundling the font file here is recommended.

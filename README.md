# ICO File Inspector

A dependency-free PowerShell utility for reading an ICO file's directory and printing its image entries as JSON. It checks the ICO header and directory length, then reports each entry's dimensions, color count, bit depth, byte size, and data offset. It does not modify the file or decode the embedded image payloads.

## Requirements

- Windows PowerShell 5.1 or PowerShell 7+
- No external modules

## Usage

```powershell
.\tools\inspect-ico.ps1 -Path .\favicon.ico
```

The JSON output includes the resolved input path, ICO header fields, image count, and one object per image entry. In ICO directory entries, a stored width or height of `0` represents `256` pixels.

## Reference data

- `data/ico-size-reference.csv` records the six size layers shown by the companion converter and their practical contexts.
- `data/supported-inputs.csv` records the four input formats shown by that converter.
- `docs/favicon-installation.md` gives a minimal example for placing an ICO at a website root and referencing it from HTML.

The tables describe the public interface and guidance of [pngtoicotool.com](https://pngtoicotool.com/). The site converts images to ICO files in the browser.

## License

MIT. See `LICENSE`.

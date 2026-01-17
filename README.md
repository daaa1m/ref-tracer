# REF Tracer

Find the source of `#REF!` errors in your Excel files.

![ref-tracer](https://img.shields.io/badge/lines-<500-green) ![single-file](https://img.shields.io/badge/files-1-blue)

## What is this?

Ever had a spreadsheet full of `#REF!` errors and no idea where they started? This tool visualizes your Excel formulas as a graph and highlights the "patient zero" - the cell where the `#REF!` actually originated. By fixing this error you will fix all the child `#REF!` errors.

## Features

- **Single HTML file** - no build step, no dependencies to install
- **Under 500 lines** - lightweight
- **Drag & drop** - just drop your `.xlsx` file
- **Patient zero detection** - find the root cause if all your `#REF!`
- **Visual graph** - see how formulas connect, looks pretty like below

![image of ref tracer outputt](<./image.png>)

## Usage

1. Clone the repo or just copy `index.html` onto your computer
2. Open it in your browser
3. Drop an `.xlsx` file (you can test it out with `test.xlsx` and `test-broken.xlsx`)
4. Click around the graph to inspect cells
5. Yellow squares with red borders = patient zeros (the actual source of `#REF!`)

## Node Colors

Follows investment banking guidelines:

- **Black** - Formula cell
- **Blue** - Hard-coded value cell (no formula)
- **Green** - Cross-sheet reference
- **Red** - External workbook reference
- **Yellow square** - Has `#REF!` error
- **Yellow square + red border** - Patient zero (this is what you're looking for)

## Tech

Just three CDN scripts:

- [SheetJS](https://sheetjs.com/) - Excel parsing
- [Cytoscape.js](https://js.cytoscape.org/) - Graph visualization
- [Tailwind CSS](https://tailwindcss.com/) - Styling

## Limitations

- Performance suffers above 5k nodes

## License

MIT

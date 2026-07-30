# JSON Workbench

Format, validate, explore, query, diff, and convert JSON entirely in your browser. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/json-workbench/

## What it does

- **Format and validate.** Pretty-print with a 2-space, 4-space, or tab indent, or minify to one line. Invalid JSON gets the browser parser's message, and, whenever the browser reports a character position, the line, the column, and a highlighted snippet around the bad character. Optional tolerant mode strips trailing commas and comments and tells you it did.
- **Tree view.** A collapsible, expandable tree of the parsed document with type-colored values and array or object counts on every node. It lazy-collapses deep nodes and caps very large documents so the tab never freezes.
- **Query.** A JSONPath input that updates live. Supports root, dot and bracket keys, indices, wildcards, recursive descent, slices, unions, and basic filters like `[?(@.price<10)]`. This is a useful JSONPath subset, not full jq, and the UI says so.
- **Diff.** Paste two documents and get a structural diff: keys added, removed, or changed, with a color-coded list and a summary count. Object keys are compared without regard to order; arrays are compared by index.
- **Convert.** Turn JSON into YAML, into CSV (for an array of flat objects, with a clear note when the shape does not fit), or into a TypeScript interface. Copy buttons on every output.

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

Pick a tab, paste JSON, and go:

- **Format and validate:** paste, choose an indent, then Pretty-print or Minify. Ctrl or Cmd + Enter pretty-prints. Turn on tolerant mode if your input has trailing commas or comments.
- **Tree:** Build tree, then expand or collapse nodes. Use Expand all or Collapse all for the whole document.
- **Query:** paste JSON, type a path such as `$.store.book[*].title` or `$..author`, and watch matches update as you type. Each result shows its computed path. Copy results gives you a JSON array of the matched values.
- **Diff:** paste into Left (A) and Right (B), then Compare.
- **Convert:** pick YAML, CSV, or TypeScript, paste, then Convert.

Every tab has a Load sample button if you just want to see it work.

## Why this exists

The popular online JSON formatters are buried in ads, run third-party scripts, and in some cases POST your payload to a server to "process" it. This is the same set of tools in one HTML file: no analytics, no signup, no upload, MIT licensed. You can read the whole thing in a single source view.

## Privacy

Everything runs in your browser. The JSON you paste, every query, every diff, and every conversion happen locally and never leave your machine. Verify by viewing the page source or by opening DevTools and watching the network tab: no requests are made.

That said, treat any web tool with care. For sensitive payloads, save the file and run it offline.

## Run locally

```bash
git clone https://github.com/0xelitesystem/json-workbench
cd json-workbench
# Open index.html in your browser, or:
python -m http.server 8000
```

## Build

There is no build. It is a single HTML file with inline CSS and JavaScript. No dependencies, no bundler, no network calls.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT.

## Related

- [json-formatter-and-validator](https://github.com/0xelitesystem/json-formatter-and-validator), pretty-print and validate JSON
- [json-to-typescript](https://github.com/0xelitesystem/json-to-typescript), generate TypeScript interfaces from JSON
- [json-path-tester](https://github.com/0xelitesystem/json-path-tester), test JSONPath expressions against a document

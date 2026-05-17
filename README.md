# webmcp-demo

A side-by-side demo of how AI agents interact with a web page today (scraping the DOM / accessibility tree) versus a future where the page declares structured tools via **WebMCP**.

## What it shows

- A booking widget rendered twice — once with annotation overlays showing the DOM nodes an agent would have to parse, once with a "Registered tools" panel showing the three tools the page exposes.
- A **Run agent** button that drives both sides at once: the left panel animates the agent scanning the DOM step by step; the right panel just calls `bookSlot({...})`.
- An explainer of how WebMCP works in three steps, with example code.
- Calls to action linking to the spec and feedback channels.

## Running locally

This is a single static page — no build step.

```sh
# any static server works; pick one
npx serve .
# or
python3 -m http.server 8000
```

Open the served URL in a browser.

## Files

- `index.html` — page structure and copy
- `styles.css` — visual design
- `app.js` — booking widget, WebMCP shim, agent simulation, annotation layout

## Notes

- The WebMCP API in `app.js` is a **shim**: it uses an in-page `window.webmcp` registry to stand in for the proposed `navigator.modelContext.registerTool(...)` surface. Update the shim and the example code in `index.html` when the canonical spec API stabilizes.
- The spec links in the CTA section (`https://github.com/webmachinelearning/webmcp`) are placeholders — point them at the real spec repo before publishing.

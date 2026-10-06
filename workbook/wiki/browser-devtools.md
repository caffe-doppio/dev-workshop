# Browser: DevTools

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** DevTools is a panel built into every browser that shows what the page asks for and what it receives, behind what you see on screen.

[Back to the workbook](../README.md)

---

## Why it matters for evidence

A screen shows what the portal **chose** to display. DevTools shows what the server **actually sent**. When the two disagree, that disagreement is your finding.

Nothing to install. Nothing you do in DevTools changes anything on the server.

## Open it

| Browser | macOS | Windows / Linux |
|---------|-------|-----------------|
| Firefox | `Cmd + Option + I` | `F12` or `Ctrl + Shift + I` |
| Chrome, Edge, Brave | `Cmd + Option + I` | `F12` or `Ctrl + Shift + I` |
| Safari | First: Settings > Advanced > tick "Show features for web developers". Then `Cmd + Option + I` | |

A panel opens, at the bottom or on the side of the window. Along its top edge: a row of **tabs**.

> [!TIP]
> Use a **private window** (`Cmd/Ctrl + Shift + P` in Firefox, `Cmd/Ctrl + Shift + N` in Chrome). It starts clean: no old cookies, no extensions mixing their traffic into your capture.

## The three tabs you need

### Console

A message log. Pages write notes there for developers. Some portals are talkative: read what it says.

- Ignore red or yellow warnings you do not understand. They are usually noise.
- You only read here. Do not type commands into the Console during the lab.

### Network

The list of every request the page made, one line each. This is where the evidence is.

1. **Keep the history.** Navigating to another page normally empties the list. Prevent it:
   - Firefox: gear icon at the right of the Network toolbar > tick **Persist Logs**.
   - Chrome: tick **Preserve log** in the Network toolbar.
2. **Open DevTools before you load the page.** Requests made before DevTools was open are not recorded. If the list is empty, reload the page (`Cmd/Ctrl + R`).
3. **Filter.** Click **Fetch/XHR** (Chrome) or **XHR** (Firefox) to keep only the data requests and hide images and styles.
4. **Inspect one request.** Click its name. A side panel opens:
   - **Headers**: the address asked, the status code, the date.
   - **Response** (Firefox) or **Preview** / **Response** (Chrome): what the server answered.

How to read an answer: see [Requests and JSON](browser-requests-json.md).

### Sources (Chrome) or Debugger (Firefox)

The code the browser received and runs. Some portals ship their display rules in readable form. You can open a file and read it like a text document. You do not need to understand every line: look for the comments and for words that match what the screen said.

## Common problems

| What you see | Fix |
|--------------|-----|
| Network list is empty | DevTools was opened after the page loaded: reload |
| Requests disappear when you click a link | Persist Logs / Preserve log is not ticked |
| Too many lines | Use the Fetch/XHR filter, or type part of a name in the filter box |
| Panel is tiny | Drag its edge. `Cmd/Ctrl +` enlarges the text inside DevTools |

## See also

- [Requests and JSON](browser-requests-json.md)
- [Export a HAR](browser-har.md)
- [Passive only](frame-passive-only.md)

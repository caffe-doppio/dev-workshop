# Frame: four evidence layers

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** screen, wire, code and correlation; any layer alone fails, together they close the chain.

[Back to the workbook](../README.md)

---

## The layers, cheapest first

| Layer | What it is | How you get it | Who can read it |
|-------|------------|----------------|-----------------|
| **Screen** | What the person saw | Screenshot, exact words copied | Anyone, including a judge |
| **Wire** | What the server actually sent | [HAR](browser-har.md), Network tab | Needs a short explanation |
| **Code** | The rule in the page that turned the answer into the screen | DevTools > Sources / Debugger | Needs a technical witness |
| **Correlation** | Wire matched against Code: "this value, through this rule, gave that screen" | Counsel's sentence | Anyone, once written well |

## Why one layer is never enough

- Screen alone: "the portal refused" says nothing about **who** refused.
- Wire alone: a value in a file, without context, means nothing to a judge.
- Code alone: a rule that may never have run in this case.

## The right defendant

When screen and wire disagree, two different bodies can be responsible: the one holding a wrong value on the server, and the one running the page that displays it. Showing where the refusal comes from sends the complaint to the right door.

And when screen and wire **agree**, that is a result too: the refusal is the authority's decision, and the dispute is about its substance, not about the portal.

## What a capture cannot show

- Logic that runs on the server and never reaches the browser.
- Other users, other files, other paths through the portal.
- Why a value is what it is.

One file is a finding, not a statistic. Anything beyond the observed case stays a hypothesis: say so.

## Writing counsel's sentence

```text
On [date, time], the portal displayed "[exact screen text]"
while the server answered [field] = [value] (capture [file], fingerprint [first 8]).
This shows that [what it proves], and does not show [what it does not].
```

## See also

- [Requests and JSON](browser-requests-json.md)
- [Passive only](frame-passive-only.md)

# Browser: requests and JSON

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** a web page is a conversation; the browser asks (a request), the server answers (a response), and modern portals answer in a text format called JSON.

[Back to the workbook](../README.md)

---

## A request, in plain words

When you click "Show my file", the page does not contain your file. It asks a server for it:

```text
Browser  ->  "GET /api/citizens/123/file"     (the request)
Server   ->  200 OK + the data                  (the response)
Page     ->  decides what to show you           (the screen)
```

The last line is the important one for litigation: **the page decides**. It can show all of the answer, part of it, or the opposite of it.

## Status codes

Shown in the **Status** column of the Network tab.

| Code | Means |
|------|-------|
| `200` | OK, the server answered |
| `304` | OK, the browser reused a copy it already had |
| `403` | Refused by the server |
| `404` | Not found |
| `500` | Server error |

A `200` with a refusal on screen is worth a second look: the server did answer.

## Reading JSON

JSON is a list of **names** and **values**. Here is an invented example, about a library loan:

```json
{
  "member_id": "LIB-0042",
  "can_borrow": true,
  "books_on_loan": [],
  "card": {
    "status": "VALID",
    "expires": "2027-01-31"
  }
}
```

| You see | It means |
|---------|----------|
| `"member_id": "LIB-0042"` | A name and its value, in quotes when it is text |
| `true` / `false` | Yes / no. No quotes |
| `[]` | An empty list. `[ ... ]` with items inside is a list of things |
| `{ ... }` inside `{ ... }` | A group of fields inside another one. Click the small triangle to unfold it |

In DevTools, **Preview** (Chrome) or **Response** (Firefox) shows JSON as a tree you can unfold. **Unfold everything**: what matters is not always at the top.

## How to write it down

For the custody log and for counsel, record a finding as:

```text
Request: <file name in the Network list>
Field:   <path to the field, for example card.status>
Value:   <exact value, copied, not retyped>
Screen:  <exact words on screen at the same moment>
```

Copy values with right click > Copy value (Firefox) or by selecting the text. Never paraphrase a value.

## See also

- [DevTools](browser-devtools.md)
- [Evidence layers](frame-evidence-layers.md)

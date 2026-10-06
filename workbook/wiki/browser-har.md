# Browser: export a HAR

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** a HAR file is a recording of everything in the Network tab, requests and responses, saved as one file you can seal and hand over.

[Back to the workbook](../README.md)

---

## Why a HAR and not a screenshot

| Screenshot | HAR |
|------------|-----|
| Shows what the page displayed | Holds what the server sent, word for word |
| Easy to fake, impossible to check | Can be opened again in any browser and compared |
| One moment, one screen | The whole session, with timestamps on each request |

The HAR is the **Wire** layer of your evidence. See [Evidence layers](frame-evidence-layers.md).

## Export it

Do it **after** reproducing what you want to document, without closing DevTools.

| Browser | How |
|---------|-----|
| Firefox | Network tab > right click on any request > **Save All As HAR** |
| Chrome, Edge | Network tab > download arrow icon in the toolbar (**Export HAR**), or right click > **Save all as HAR** |

Name it so nobody has to guess what it is:

```text
groupN_citizen-ID_YYYYMMDD-HHMM.har
```

> [!NOTE]
> Recent Chrome versions export a **sanitized** HAR by default: cookies and authorization headers are removed. For the lab this is fine. In real life, decide on purpose which version you keep, and write it in the custody log.

## Handle it as sensitive

In real life, a HAR contains:

- Session cookies: whoever holds them may be able to act as the person who was logged in.
- Personal data: everything the portal sent about the person.

So, from the moment it exists:

1. [Fingerprint it](seal-sha256.md) before anything else.
2. [Write it in the custody log](share-custody-log.md).
3. [Label it](share-tlp.md).
4. Never send it unencrypted: [age](seal-age.md).

The lab portal is fictional and its data synthetic. Handle the file as if it were real anyway: that is the exercise.

## Open a HAR again

Drag the `.har` file onto the Network tab of an open DevTools. The requests reappear and can be inspected as if live. Useful to check what a received piece contains.

## See also

- [SHA-256 fingerprint](seal-sha256.md)
- [Custody log](share-custody-log.md)

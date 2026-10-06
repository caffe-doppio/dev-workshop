# Seal: age encryption

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** age locks a file so that only the holder of one specific key can open it.

[Back to the workbook](../README.md)

---

## What it proves, and what it does not

| Proves | Does not prove |
|--------|----------------|
| Only the recipient can read the file | Who sent it: anyone with the recipient's public key can encrypt a file for them |
| | That the file was not changed before encryption: that is the [fingerprint](seal-sha256.md) |

## Two keys, two roles

| Key | Looks like | Who sees it |
|-----|------------|-------------|
| **Public** key | `age1...` (one long line) | Everyone. Post it on the wall. It only lets people lock files **for you** |
| **Private** key | `AGE-SECRET-KEY-1...`, inside `group.key` | Your group only. It opens what was locked for you. Never post it |

Think of the public key as an open padlock you hand out: anyone can close it on a box, only you can open it.

## Commands

Install: see [Terminal cheat sheet](terminal-cheatsheet.md).

### 1. Create your group key (once)

```sh
age-keygen -o group.key
```

The terminal prints `Public key: age1...`. Copy that line and post it where the other groups can see it.

### 2. Encrypt for another group

```sh
age -r age1THEIR_PUBLIC_KEY -o evidence.har.age evidence.har
```

`-r` is the **recipient**: the other group's public key, not yours.

### 3. Decrypt what was sent to you

```sh
age -d -i group.key -o received.har evidence.har.age
```

Then [fingerprint](seal-sha256.md) `received.har` and compare with the fingerprint the sender posted.

## Common mistakes

| Mistake | Result |
|---------|--------|
| Encrypting with your own public key | Only you can open it. The recipient cannot |
| Sending `group.key` instead of the public key | Your private key is exposed: make a new one, and log it |
| Decrypting and trusting the content without checking the fingerprint | You do not know what you received |

## See also

- [SHA-256 fingerprint](seal-sha256.md)
- [Custody log](share-custody-log.md)

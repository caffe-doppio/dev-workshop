# Terminal cheat sheet

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** every command used in the lab, for macOS, Linux and Windows.

[Back to the workbook](../README.md)

---

## Open a terminal

| System | How |
|--------|-----|
| macOS | `Cmd + Space`, type `Terminal`, Enter |
| Linux | `Ctrl + Alt + T` in most distributions |
| Windows | Start menu, type `PowerShell`, Enter |

Type a command, press Enter. To paste: `Cmd + V` (macOS), `Ctrl + Shift + V` (Linux), right click or `Ctrl + V` (Windows).

## Go to your evidence folder

```sh
cd ~/Downloads          # go to the Downloads folder (where the HAR usually lands)
ls                      # list files (Windows PowerShell: ls or dir)
pwd                     # show where you are
```

Tip: type `cd ` (with a space) then drag the folder from your file manager into the terminal window.

Make a folder for the lab and work there:

```sh
mkdir lab-evidence
cd lab-evidence
```

## Install the tools

Check first: `age --version`, `ots --version`. If both answer, skip this.

Install **before the session**: some steps take minutes or need admin rights. One laptop per group with `age` is enough. `ots` is optional.

| Tool | macOS (Homebrew) | Linux (Debian, Ubuntu) | Windows |
|------|------------------|------------------------|---------|
| age | `brew install age` | `sudo apt install age` | `winget install FiloSottile.age` |
| ots | `brew install opentimestamps-client` | `sudo apt install pipx`, `pipx ensurepath`, open a new terminal, `pipx install opentimestamps-client` | Use https://opentimestamps.org (no install) |

- No Homebrew on your Mac? Install it from https://brew.sh first: several minutes, admin rights.
- Why not `pip install`: recent Python refuses it outside a virtual environment (`externally-managed-environment`).

No install possible? `ots`: use https://opentimestamps.org. `age` has no web equivalent: pair with a group whose laptop has it.

## Fingerprint ([SHA-256](seal-sha256.md))

| System | Command |
|--------|---------|
| macOS | `shasum -a 256 evidence.har` |
| Linux | `sha256sum evidence.har` |
| Windows, PowerShell | `Get-FileHash .\evidence.har -Algorithm SHA256` |
| Windows, cmd | `certutil -hashfile evidence.har SHA256` |

Windows prints the fingerprint in capitals, macOS and Linux in lower case: same fingerprint. Compare a received file: [SHA-256](seal-sha256.md#check-a-file-you-received).

## Anchor ([OpenTimestamps](seal-opentimestamps.md))

```sh
ots stamp evidence.har            # creates evidence.har.ots
ots info evidence.har.ots         # inspect
ots verify evidence.har.ots       # needs a local Bitcoin node: pending during the lab, normal
```

To verify a confirmed anchor without a Bitcoin node: drop the `.ots` and its file on https://opentimestamps.org.

## Encrypt ([age](seal-age.md))

```sh
age-keygen -o group.key                                 # once; prints your public key age1...
age -r age1THEIR_KEY -o evidence.har.age evidence.har   # encrypt for another group
age -d -i group.key -o received.har evidence.har.age    # decrypt what was sent to you
```

`-o` overwrites an existing file without warning: always decrypt to a new name, never to the name of your own capture.

Windows PowerShell: same commands, `age.exe` if `age` is not found.

## When something goes wrong

| Message | Meaning |
|---------|---------|
| `command not found` / `is not recognized` | Tool not installed, or the terminal was opened before installing: open a new one |
| `No such file or directory` | You are not in the right folder: `ls`, then `cd` |
| `Permission denied` | Wrong folder, or a file open elsewhere |
| Spaces in a file name break the command | Put the name in quotes: `"my file.har"` |

## See also

- [SHA-256](seal-sha256.md) · [OpenTimestamps](seal-opentimestamps.md) · [age](seal-age.md)

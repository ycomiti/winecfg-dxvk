# winecfg-dxvk
A script for creating a wine prefix with DXVK.

---

## Installation

```bash
sudo bash -c 'FILE=/usr/bin/winecfg-dxvk; curl -L# "https://raw.githubusercontent.com/ycomiti/winecfg-dxvk/refs/heads/main/winecfg-dxvk" --output "${FILE}"; chmod -v 755 "${FILE}"'
```
---

## Uninstall

```bash
sudo rm -v "$(which winecfg-dxvk)"
```
---

## Features

- Downloads and installs DXVK (version 2.7.1 by default)  
- Supports **64-bit (`win64`) and 32-bit (`win32`) Wine prefixes**  
- Configures Wine Windows version (default: `win10`)
- Copies DXVK DLLs to the correct Wine system folders  
- Registers DXVK DLLs (`d3d8`, `d3d9`, `d3d10core`, `d3d11`, `dxgi`) as **native**  

---

## Requirements

- Linux system with Wine installed  
- `curl` and `tar` installed

---

## Usage

```bash
winecfg-dxvk <wineprefix> [arch] [winVersion] [version] [repo]
````

### Arguments

| Argument     | Description                                       | Default  |
| ------------ | ------------------------------------------------- | -------- |
| `wineprefix` | Path to the Wine prefix to install DXVK           | required |
| `arch`       | Wine architecture (`win64` or `win32`)            | `win64`  |
| `winVersion` | Windows version for Wine (`win10`, `win7`, etc.)  | `win10`  |
| `version` | DXVK version  | `2.7.1`  |
| `repo` | DKVK version  | [doitsujin](https://github.com/doitsujin/dxvk/)  |

### Examples

**Install DXVK in a 64-bit Wine prefix:**

```bash
winecfg-dxvk ~/.wine
```

---

## How It Works

1. Downloads DXVK from official GitHub repo
2. Extracts DXVK and copies DLLs to Wine system folders
3. Configures Wine Windows version
4. Registers DXVK DLLs as **native** in Wine

---

## License

This script is licensed under the GNU General Public License v3.0 (GPL-3.0).

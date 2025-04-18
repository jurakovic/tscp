﻿
# Timestamp Copy

Timestamps Copy is a lightweight Bash and PowerShell-based script that integrates directly into the Windows File Explorer context menu, enabling you to **copy** and **paste** file and folder timestamps with ease.

This solution is especially useful when you need to preserve or replicate Date Created and Date Modified values across files or folders – ideal for organizing backups, restoring files, or syncing metadata.

### Features

#### Explorer Context Menu Integration

Adds convenient right-click options for both files and folders:

![ContextMenu](img/contextmenu.png)

#### Copy Mode

Stores the selected file or folder's Date Created and Date Modified timestamps for reuse.

#### Paste Mode

Applies the previously copied timestamps to the currently selected file or folder.

#### Selective Timestamp Paste

Use the specific `Paste 'Date Created'` or `Paste 'Date Modified'` options to update only the desired timestamp.

### Usage

Right-click on a file or folder and choose `Copy` under the context menu.  
This saves the timestamps to a temporary location ("clipboard").

Right-click on another file or folder and choose:

`Paste` – to apply both timestamps  
`Paste 'Date Created'` – to apply only the Date Created  
`Paste 'Date Modified'` – to apply only the Date Modified  

Each entry starts Bash terminal and runs the [`tscp.sh`](tscp.sh) script with the appropriate parameters (example screenshots below).

### Requirements

- Windows 10/11 (tested on Windows 11 24H2)  
- PowerShell 5.1 or later  
- Bash (recommended: Git for Windows)  
- Administrator privileges (required for installation)

> **Bash** can be installed on Windows in several ways, including:
> - [Git for Windows](https://gitforwindows.org) (comes with the MSYS2 runtime – [Git for Windows flavor](https://github.com/git-for-windows/build-extra/blob/main/ReleaseNotes.md))
> - [MSYS2](https://www.msys2.org)
> - [Cygwin](https://cygwin.com)
> - [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install)
>
> The recommended way is to use **Git for Windows** as it provides a lightweight and user-friendly environment for running Bash scripts on Windows.  
> This script is designed to work with Git for Windows and the official MSYS2 runtime. It doesn't work with Cygwin or WSL. It could work with some minor modifications, and while I don't plan to do it myself, feel free to update it to suit your own needs.  

### Installation

1. Clone the repository.
	```bash
	git clone https://github.com/jurakovic/timestamp-copy.git
	```
2. Open an elevated Bash terminal ('Run as Administrator').
3. Navigate to the directory where you cloned the repository.
	```bash
	cd timestamp-copy
	```
4. Add the context menu entries. This can be done in two ways.  
	Run the `tscp.sh` script
	```bash
	./tscp.sh
	```

	and then choose the option `i`
	```text
	Timestamp Copy (1.0.0)

	[i] Install
	[u] Uninstall

	[q] Quit

	Choose option:
	```

	or run the script with the `-i` option to install it directly:
	```bash
	./tscp.sh -i
	```

### Screenshots

Copy  
![Copy](img/copy.png)

Paste  
![Copy](img/paste.png)

### Limitation

This script is designed to work with **only one selected file or folder at a time**. While it does appear in the context menu when multiple items are selected, it will be executed **independently for each item**. This can lead to unexpected behavior. For accurate and predictable results, always use it with a single selection.

### Disclaimer

This script is provided **as-is**, without any warranties or guarantees of fitness for a particular purpose. It was created solely for educational and experimental use, and I do **not** intend to actively support or maintain it. While it should work reliably in most cases, use it at your own risk.  

### Future Plans

In the future, I plan to develop a more robust and user-friendly version written entirely in PowerShell for a more native Windows experience.

---

### References

<https://stackoverflow.com/questions/20449316/how-add-context-menu-item-to-windows-explorer-for-folders>  
<https://www.tomshardware.com/software/windows/how-to-add-custom-shortcuts-to-the-windows-11-or-10-context-menu>  
<https://blog.sverrirs.com/2014/05/creating-cascading-menu-items-in.html>  
<https://learn.microsoft.com/en-us/windows/win32/shell/context-menu-handlers>  
<https://mrlixm.github.io/blog/windows-explorer-context-menu/>  

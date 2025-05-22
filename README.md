# movfzf

A terminal tool for searching and streaming movies/series from scloud.ninja using `fzf` with preview and playback with `mpv`.

---
## Demo


https://github.com/user-attachments/assets/a1bbd4f9-b950-4880-bcd3-9bd5e089fc98



## 🚀 Features

- Fuzzy search interface (via `fzf`)
- Fetches and parses results from a scloud.ninja
- Handles Cloudflare tokens and session cookies
- Clipboard integration for copying links
- Direct playback with `mpv`
- Debug and “foul mouth” modes for fun/error verbosity

---

## ⚡ Usage

### 1. **First-time Setup**

- Ensure you have `fzf` and `curl` installed.
- For best results, install `pup` (HTML parser):  
  ```sh
  sudo apt install pup
  ```
- Optionally, install `xclip` (Linux) or `pbcopy` (Mac) for clipboard support.
- `mpv` is recommended for direct playback of selected links.

### 2. **Cloudflare Token**

- On first run (or if your token expires), you’ll be prompted to get a `cf_clearance` token:
  - Visit: `https://new4.scloud.ninja`
  - Open browser DevTools (F12) → Network tab
  - Find a request and copy the value of the `cf_clearance` cookie
  - Paste it when prompted

### 3. **Running the Script**

```sh
./movfzf "search term"
```

- Replace `"search term"` with what you want to search for.
- The script will fetch results, parse them, and present them in `fzf`.
- Use arrow keys to select, press Enter to choose.

### 4. **After Selection**

- The chosen link is shown and copied to clipboard (if supported).
- If you have `mpv`, the link will try to play automatically.
- Otherwise, use the copied link as needed.

---

## 🛠️ Options

- `-d` : Enable debug mode (verbose output)
- `-f` : Enable “foul mouth” mode for fun error messages
- `-h` : Show usage/help

---

## 🖥️ Example

```sh
./movfzf -d "some movie"
```

---

## 📝 Notes

- Token is saved to `~/.scloud_ripper_token` for reuse.
- If the site changes, parsing may break—keep `pup` up to date.
- If no results are found, check your token or search term.

---

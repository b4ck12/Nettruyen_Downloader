# Manga & Comic Downloader Toolkit

A comprehensive toolkit for crawling and downloading manga and comics from popular Vietnamese reading websites (such as Nettruyen, TruyenQQ, Blogtruyen, and many more). This project includes both a Python-based desktop application with a graphical interface and a versatile JavaScript Userscript for browser integration.

## 🌟 Features

### 1. Python Desktop Downloader (`NettruyenDownloader.py` / `test_thread.py`)
- **Graphical User Interface (GUI):** Built with `tkinter`, making it easy to paste a URL, select a download directory, and monitor the progress.
- **Concurrent Downloading:** Utilizes `threading` and `concurrent.futures.ThreadPoolExecutor` to download multiple images simultaneously, significantly reducing download time.
- **Anti-Bot Bypass:** Employs `fake_useragent` and `cloudscraper` (in alternate versions) to circumvent basic Cloudflare protections and IP blocks.
- **Automatic Structuring:** Automatically creates organized folders for the comic and its respective chapters.

### 2. Browser Userscript (`main.user.js` / `test.user.js`)
- **One-Click Download:** Integrates directly into your web browser. Just right-click or press `Alt + Y` to download the entire chapter or all chapters.
- **Auto-Archive:** Fetches images and automatically packages them into a `.cbz` (Comic Book Zip) or `.zip` file using `fflate` / `zip.js` right in the browser.
- **Wide Compatibility:** Supports a massive list of Vietnamese comic websites out of the box (Nettruyen, Blogtruyen, TruyenQQ, Hamtruyen, LxHentai, etc.).

## 🚀 Getting Started

### Python Downloader

**Prerequisites:**
- Python 3.x
- Required Python packages:
  ```bash
  pip install requests beautifulsoup4 fake_useragent cloudscraper
  ```

**Usage:**
1. Run the main downloader script:
   ```bash
   python NettruyenDownload/NettruyenDownloader.py
   ```
   *(Alternatively, run `test_thread.py` for the multithreaded version).*
2. A window will appear. Paste the link of the comic's main page.
3. Click **Browse** to select the destination folder on your computer.
4. Click **Download**. The progress bar will indicate the download status, and a popup will appear when the download is complete.

### Browser Userscript

**Prerequisites:**
- A modern web browser (Chrome, Firefox, Edge, Safari).
- A userscript manager extension like Tampermonkey or Violentmonkey.

**Usage:**
1. Open the userscript manager dashboard and click **Add a new script**.
2. Copy the contents of `main.user.js` (or `test.user.js`) and paste it into the editor, then save.
3. Navigate to a supported comic reading website.
4. **To Download:**
   - Right-click on a chapter link.
   - Or press `Alt + Y` to download all chapters on the page.
   - Press `Shift + Alt + Y` to download all chapters merged into a single file.

## 📁 Project Structure

- `/NettruyenDownload/NettruyenDownloader.py`: Main GUI downloader script.
- `/NettruyenDownload/test_thread.py`: Optimized GUI downloader utilizing thread pools for faster image fetching.
- `/Nettruyen/json + main (simple ver).py`: A script demonstrating fetching chapters and writing metadata to a JSON file before downloading using `cloudscraper`.
- `main.user.js` / `test.user.js`: The Greasemonkey/Tampermonkey userscripts for browser-based downloading.
- `all_comics_links_list.json` & `comic_names_old.txt`: Data dumps containing scraped lists of available comics and their respective URLs.

## ⚠️ Disclaimer

- **Personal Use Only:** This toolkit is intended strictly for personal archiving and offline reading.
- **Copyright:** Please respect the copyrights of the original authors, translators, and publishers. Do not use this tool to re-distribute copyrighted material.
- **Website ToS:** Frequent automated requests might violate the Terms of Service of the target websites. Use responsibly to avoid getting your IP banned.

## 📄 License

This project is released under the [MIT License](./LICENSE.md).
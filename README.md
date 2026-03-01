# 🌍 Gigapan Downloader & Stitcher

> Download, reconstruct, and batch-process ultra-high-resolution Gigapan panoramas — fast, seamlessly, and automatically.

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=flat-square&logo=opencv&logoColor=white)](https://opencv.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Stars](https://img.shields.io/github/stars/zenst45/Gigapan-Downloader-Stitcher-High-Resolution-Panorama-Processing-in-Python?style=flat-square)](https://github.com/zenst45/Gigapan-Downloader-Stitcher-High-Resolution-Panorama-Processing-in-Python/stargazers)

---

## 📖 Overview

**Gigapan Downloader & Stitcher** is a Python tool designed to fetch and reassemble the individual tiles that make up [Gigapan](http://www.gigapan.com/) high-resolution panoramic images. Instead of being limited to a browser viewer, you get the full-resolution image as a single `.tiff` file — ready to use, analyze, or archive.

Built with **multithreading** for speed and **OpenCV** for pixel-perfect stitching, it handles even the most massive panoramas without breaking a sweat.

---

## ✨ Features

- ⚡ **Multithreaded tile downloading** — parallel downloads drastically reduce wait time
- 🧩 **Seamless image stitching** — OpenCV-powered reconstruction with no visible seams
- 📋 **Queue system** — batch-process multiple Gigapan photo IDs automatically
- 📝 **Detailed logging** — track progress and debug issues in real time
- 🖥️ **Interactive menu** — simple CLI interface for all operations

---

## 📁 Project Structure

```
Gigapan-Downloader-Stitcher/
├── main.py              # Main script with CLI menu
├── queue.txt            # Stores queued photo IDs for batch processing
├── tiles/               # Downloaded tile cache
├── {photo_id}_assembled.tiff  # Final stitched output
├── requirements.txt
└── LICENSE
```

---

## 🚀 Getting Started

### Prerequisites

Python 3.x is required. Install dependencies with:

```bash
pip install -r requirements.txt
```

### Run the Script

```bash
python main.py
```

You'll be greeted with an interactive menu:

```
1. Download tiles only
2. Assemble image only
3. Download and assemble
4. Process the queue
5. Add photo IDs to queue
6. View queue
7. Exit
```

---

## 🔧 Usage Examples

### Download & Assemble a Single Image

1. Run `python main.py`
2. Choose option `3` — *Download and assemble*
3. Enter the Gigapan photo ID (e.g., `123456`)
4. The final image is saved as `123456_assembled.tiff`

### Batch Processing with Queue

1. Choose option `5` to add multiple photo IDs to the queue
2. Choose option `4` to process all queued images automatically

---

## 🗂️ Output Format

All assembled panoramas are exported as **TIFF** files (`{photo_id}_assembled.tiff`), preserving maximum image quality with no compression artifacts.

---

## 🧠 How It Works

1. **Fetch metadata** — retrieves the tile grid dimensions for a given Gigapan photo ID
2. **Download tiles** — concurrently fetches all image tiles using a thread pool
3. **Stitch tiles** — assembles tiles row by row into a single seamless canvas using OpenCV
4. **Export** — saves the final reconstructed image as a full-resolution TIFF

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

Made by [zenst45](https://github.com/zenst45)

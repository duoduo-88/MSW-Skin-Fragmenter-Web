# MSW Skin Fragmenter Web

[繁體中文](README_zh-TW.md)

MSW Skin Fragmenter Web is a lightweight, browser-based PNG fragmentation tool for artwork protection workflows.

Current version: **v1.1.0**

> Fragmentation is an obfuscation aid, not encryption. It cannot guarantee that an image will never be reconstructed.

## Features

- Local PNG processing with transparency preserved
- Optional same-size PNG mask
- Adjustable fragment count, block size, and size randomness
- Optional source-pixel interference
- Combined and per-fragment previews
- Dark gray, 50% gray, and checkerboard preview backgrounds
- Traditional Chinese and English interface
- Individual PNG or ZIP export

## Privacy

Source images and masks are processed in the browser and are not uploaded by this project. The page loads JSZip from jsDelivr for ZIP export, so opening it may contact that CDN.

## Compatibility

A modern desktop browser with JavaScript and Canvas support is recommended. Large images and intensive settings can require substantial memory and processing time.

## Public Documentation

To reduce misuse, this repository intentionally provides only a high-level feature overview. Detailed operating guidance, parameter strategies, and reconstruction-related implementation notes are not included.

## License

Project code is licensed under the [MIT License](LICENSE). JSZip retains its own license; see [Third-Party Notices](THIRD_PARTY_NOTICES.md).

[Support DuoDuo on Ko-fi](https://ko-fi.com/duoduo88)

Copyright (c) 2025 DuoDuo

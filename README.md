# MSW Skin Fragmenter Web

[繁體中文](README_zh-TW.md)

MSW Skin Fragmenter Web is a browser-based PNG fragmentation tool for artwork workflows. It divides the visible area of a PNG into separate transparent PNG fragments, optionally limits the working area with a mask, and can add interference pixels to make casual reconstruction more difficult.

Current version: **v1.0.2**

> Fragmentation is an obfuscation aid, not encryption. It cannot guarantee that an image is impossible to reconstruct.

## Features

- Preserves PNG transparency while assigning image blocks to 1–10 fragments.
- Supports an optional PNG mask with the same dimensions as the source image.
- Provides adjustable block size and size randomness.
- Can add source-derived interference pixels to fragments 2 and later.
- Shows the combined result or an individual fragment in the preview.
- Allows fragment renaming and individual PNG downloads.
- Packages all generated fragments into one ZIP archive.
- Processes selected image data in the browser; the application code does not upload it to a server.

## Requirements

- A current desktop browser with JavaScript, Canvas, and `OffscreenCanvas` support.
- Internet access when loading the page unless JSZip has already been cached. ZIP export uses JSZip 3.10.0 from jsDelivr.
- A PNG source image with transparency is recommended.
- A mask, when used, should be a PNG with the same pixel dimensions as the source image.

## Run Locally

1. Download or clone this repository.
2. Open `index.html` in a supported browser.
3. Keep internet access available so the JSZip dependency can load.

No build step or package installation is required.

## Usage

1. Select the source PNG.
2. Optionally select a same-size PNG mask. Non-transparent mask areas participate in fragmentation; fully transparent mask areas are removed from the results.
3. Choose the fragment count, base block size, and size-randomness multiplier.
4. Keep interference pixels enabled when additional obfuscation is desired. This option requires at least two fragments.
5. Select **Run Split** (`執行拆解`).
6. Inspect the combined preview and individual fragments.
7. Rename or download fragments individually, or export all fragments as `fragments.zip`.

The interface recommends a 2750 × 3500 source image for compatibility with the related PSD workflow, but other dimensions can still be processed.

## Privacy and Network Behavior

Source images and masks are read through browser file APIs and processed locally. The page does not contain an image-upload request. However, it loads JSZip from `cdn.jsdelivr.net`, so opening the page can make a network request to that CDN.

## Limitations

- PNG is the supported input and output format.
- Processing large images, very small blocks, or high randomness values can consume substantial memory and CPU time.
- A mask with different dimensions is not rejected automatically and can produce incomplete or unexpected clipping.
- The generated arrangement is randomized and is not intended to be cryptographically secure.
- The tool does not create or edit the final PSD package; exported fragments must be placed into the target workflow separately.

## License

The project code is licensed under the [MIT License](LICENSE). JSZip remains under its own license; see [Third-Party Notices](THIRD_PARTY_NOTICES.md).

Copyright (c) 2025 DuoDuo

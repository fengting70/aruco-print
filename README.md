## Print ArUco Markers easily

This is a small website which allows you to easily print multiple ArUco-markers at once: you can generate a specific number of markers, set the width of the markers and the spacing on the paper.

**Live Demo:** [https://fengting70.github.io/](https://fengting70.github.io/)

### Dictionary

This fork uses OpenCV's **`cv::aruco::DICT_6X6_250`** dictionary:

- **Grid size:** 6×6 (inner content) with a 1-cell thick black border on all four sides, rendering as 8×8 visually
- **Total markers:** 250 (IDs 0–249)
- **Compatibility:** Markers are generated from OpenCV's pre-computed dictionary data (`DICT_6X6_1000_BYTES` in `opencv_contrib`), ensuring full compatibility with OpenCV's ArUco detection

### How it works

1. The marker bit patterns are extracted directly from OpenCV's source (`opencv_contrib/modules/objdetect/src/aruco/predefined_dictionaries.hpp`)
2. Each marker's 6×6 inner matrix is rendered as an inline SVG: a black background rectangle (the border) with white rectangles for each inner cell where the bit value is `1`
3. The page lets you configure marker count, IDs (sequential, random, or custom comma-separated list), width, and spacing — then generates printable SVGs

### Usage

- Open the demo page in your browser
- Enter the number of markers you want (or specify custom IDs)
- Adjust the width and spacing
- Use **Ctrl+P** (or the browser print menu) to print

### Forked from

This repository is a fork of [TN1ck/aruco-print](https://github.com/TN1ck/aruco-print), originally built for 5×5 ArUco markers (7×7 with border, 1024 markers). The dictionary was upgraded to OpenCV's DICT_6X6_250 for better detection performance.

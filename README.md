# FastFaceDetect-Library

This repository contains a library for CNN-based face detection in images, designed to be lightweight and efficient. The library is platform-independent and can run on any system with a C++ compiler. It has been enhanced to focus on high-speed detection using SIMD optimizations and is compatible with platforms including Windows, Linux, and ARM processors.

## Features

- **Platform Independence**: Requires only a C++ compiler.
- **Performance Optimizations**:
  - SIMD instructions (AVX2 for Intel CPUs, NEON for ARM).
  - Multi-threading support for enhanced speed.
- **Standalone Library**: No external dependencies required.
- **Examples Provided**: Demonstrates face detection on images and camera feeds.

## Usage

### Integrating the Library

1. Copy all files from the `src/` directory into your project.
2. Compile the files alongside your project files.
3. Add a `facedetection_export.h` file with the following content:
   ```cpp
   #define FACEDETECTION_EXPORT
   ```
4. Use the library's functions to integrate face detection into your application.

### Compilation Tips

- **GCC/Clang**: Use `-O3` for optimizations.
- **Microsoft Visual Studio**: Set the optimization level to "Maximize Speed" (`-O2`).
- **Enable OpenMP**: Use for parallel processing to further boost performance.
- Compile the library as either a static or dynamic library if needed.

### Running Examples

- Example files are provided in the `examples/` directory:
  - `examples/detect-image.cpp`
  - `examples/detect-camera.cpp`
- These examples demonstrate how to use the library for face detection.

### Performance Optimization

- Enable AVX2 instructions for Intel CPUs or NEON for ARM processors.
- Multi-threading improves performance significantly, particularly on modern CPUs.

## Performance Metrics

### Intel CPU (AVX2/AVX512)

| Resolution | Time (Single-thread) | FPS (Single-thread) | Time (Multi-thread) | FPS (Multi-thread) |
| ---------- | -------------------- | ------------------- | ------------------- | ------------------ |
| 640x480    | 50.02ms              | 19.99               | 6.55ms              | 152.65             |
| 320x240    | 13.09ms              | 76.39               | 1.82ms              | 550.54             |
| 160x120    | 3.61ms               | 277.37              | 0.57ms              | 1745.13            |
| 128x96     | 2.11ms               | 474.60              | 0.33ms              | 2994.23            |

### ARM CPU (Raspberry Pi 4 B)

| Resolution | Time (Single-thread) | FPS (Single-thread) | Time (Multi-thread) | FPS (Multi-thread) |
| ---------- | -------------------- | ------------------- | ------------------- | ------------------ |
| 640x480    | 404.63ms             | 2.47                | 125.47ms            | 7.97               |
| 320x240    | 105.73ms             | 9.46                | 32.98ms             | 30.32              |
| 160x120    | 26.05ms              | 38.38               | 7.91ms              | 126.49             |
| 128x96     | 15.06ms              | 66.38               | 4.50ms              | 222.28             |

### Minimal Face Size

- Detects faces as small as 10x10 pixels.

## Model Information

- **Pre-trained Model**: Available in `src/facedetectcnn-data.cpp` (C++ arrays).
- **ONNX Model**: Adapted for use in OpenCV Zoo.

## Customizations

This version has been adapted for:
- Improved documentation clarity.
- Simplified integration steps for new projects.
- Highlighting performance tips for different hardware platforms.

## License

This library is distributed under a custom license. Redistribution and use in source and binary forms, with or without modification, are restricted to non-commercial use only. Contact the author for licensing inquiries.

## Author and Contact

- **Author**: Arshita Sharma
- **Contact**: [arshita@example.com](mailto:asharm42@vols.utk.edu)

For questions, suggestions, or contributions, feel free to reach out!


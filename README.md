# FastFaceDetect-Library

This repository contains an open-source library for CNN-based face detection in images. The library is lightweight and platform-independent, relying solely on a C++ compiler. It is designed for high-speed detection with SIMD optimizations and is compatible with multiple platforms including Windows, Linux, ARM, and more.

## Features
- **Platform Independence**: Compatible with any C++ compiler.
- **Optimized for Performance**:
  - SIMD instructions (AVX2 for Intel CPUs, NEON for ARM).
  - Multi-threading support.
- **Standalone Library**: No external dependencies required.
- **Model Included**: Pre-trained CNN model in static C++ arrays.
- **Examples Provided**: Includes usage examples for both images and live camera feeds.

## Usage
### Integrating the Library
1. Copy all files from the `src/` directory into your project.
2. Compile the files alongside the rest of your project files.
3. Add `facedetection_export.h` with the following content:
   ```cpp
   #define FACEDETECTION_EXPORT
   ```
4. Use the provided functions to integrate face detection into your application.

### Compilation Tips
- **GCC/Clang**: Use `-O3` for optimization.
- **Microsoft Visual Studio**: Set optimization to "Maximize Speed" (`-O2`).
- **Enable OpenMP** for parallel processing to further enhance speed.
- Compile as a static or dynamic library if needed.

### Running Examples
- Examples are located in the `examples/` directory:
  - `examples/detect-image.cpp`
  - `examples/detect-camera.cpp`
- These demonstrate face detection on images and live camera feeds respectively.

### Performance Optimization
- Use AVX2 instructions for Intel CPUs.
- Use NEON instructions for ARM processors.
- Multi-threading is supported for improved performance.

## Performance Metrics
### Intel CPU (AVX2/AVX512)
| Resolution    | Time (Single-thread) | FPS (Single-thread) | Time (Multi-thread) | FPS (Multi-thread) |
|---------------|-----------------------|----------------------|----------------------|---------------------|
| 640x480       | 50.02ms              | 19.99               | 6.55ms              | 152.65              |
| 320x240       | 13.09ms              | 76.39               | 1.82ms              | 550.54              |
| 160x120       | 3.61ms               | 277.37              | 0.57ms              | 1745.13             |
| 128x96        | 2.11ms               | 474.60              | 0.33ms              | 2994.23             |

### ARM CPU (Raspberry Pi 4 B)
| Resolution    | Time (Single-thread) | FPS (Single-thread) | Time (Multi-thread) | FPS (Multi-thread) |
|---------------|-----------------------|----------------------|----------------------|---------------------|
| 640x480       | 404.63ms             | 2.47                | 125.47ms            | 7.97                |
| 320x240       | 105.73ms             | 9.46                | 32.98ms             | 30.32               |
| 160x120       | 26.05ms              | 38.38               | 7.91ms              | 126.49              |
| 128x96        | 15.06ms              | 66.38               | 4.50ms              | 222.28              |

### Minimal Face Size
- Detection of faces as small as 10x10 pixels.

## Model Information
- **Pre-trained Model**: Provided as `src/facedetectcnn-data.cpp` (C++ arrays).
- **ONNX Model**: Available in the OpenCV Zoo.
- Note: OpenCV DNN does not support the latest YuNet version with dynamic input shapes. Ensure the input shape matches the ONNX model.

## Acknowledgments
- Library trained using `libfacedetection.train`.
- Supported by the Science Foundation of Shenzhen (Grant No. 20170504160426188).

## Citation
Please cite the following works if you use this library in your research:

- Wei Wu, "YuNet: A Tiny Millisecond-level Face Detector," Machine Intelligence Research, 2023.
- Yuantao Feng et al., "Detect Faces Efficiently: A Survey and Evaluations," IEEE Transactions on Biometrics, Behavior, and Identity Science, 2022.
- Hanyang Peng and Shiqi Yu, "A Systematic IoU-Related Method: Beyond Simplified Regression for Better Localization," IEEE Transactions on Image Processing, 2021.

## License
This library is distributed under an open-source license. Please refer to the `LICENSE` file for details.

## Contact
For questions or contributions, please contact Arshita Sharma at asharm42@vols.utk.edu


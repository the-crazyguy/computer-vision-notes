# Tesseract notes

## Tesseract documentation
https://tesseract-ocr.github.io/tessdoc/

## Tesseract API documentation
https://zdenop.github.io/tesseract-doc/

## Tesseract API examples
https://tesseract-ocr.github.io/tessdoc/APIExample.html
https://tesseract-ocr.github.io/tessdoc/Examples_C++.html

## Tesseract language data
[best_improved](https://github.com/tesseract-ocr/tessdata)<br>
[best](https://github.com/tesseract-ocr/tessdata_best)<br>
[fast](https://github.com/tesseract-ocr/tessdata_fast)<br>

**Important**
Make sure to set the TESSDATA_PREFIX environment variable to your tessdata folder.<br>
Example for Tesseract built by vcpkg on Windows 10:<br> ```D:\Apps\vcpkg\vcpkg\packages\tesseract_x64-windows\share\tessdata```

## Info from vcpkg tesseract install:
Things to include in CMakeList.txt:<br>
```find_package(Tesseract CONFIG REQUIRED)```<br>
```target_link_libraries(main PRIVATE Tesseract::libtesseract)```


## Tesseract and OpenCV
[Tutorial](https://medium.com/building-a-simple-text-correction-tool/basic-ocr-with-tesseract-and-opencv-34fae6ab3400)
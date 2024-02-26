# Using Tesseract in combination with OpenCV

## 1. Set up the project following the guide in vcpkg-project-setup.md

## 2. Include OpenCV CMakeLists.txt

Assumes NON-vcpkg install

### 2.1 Set the OpenCV_DIR to the opencv build directory
```set(OpenCV_DIR D:/Apps/OpenCV/opencv/build)``` 

### 2.2 Include the package in the project as required
```find_package(OpenCV REQUIRED)```

### 2.3 Add the include directories for OpenCV
```include_directories(${OpenCV_INCLUDE_DIRS})```

### 2.4 (After a call to add_executable(...)) link library for OpenCV

```target_link_libraries(opencv_hello_world PRIVATE ${OpenCV_LIBS})```<br>
where you can choose to link it ```PUBLIC```, ```INTERFACE```, or ```PRIVATE```

## 3. Include Tesseract in CMakeLists.txt

Assumes vcpkg install

### 3.1 Include the Tesseract package

```find_package(Tesseract CONFIG REQUIRED)```

### 3.2 (After a call to add_executable(...)) link library for Tesseract

```target_link_libraries(${CMAKE_PROJECT_NAME} PRIVATE Tesseract::libtesseract)```<br>
where you can choose to link it ```PUBLIC```, ```INTERFACE```, or ```PRIVATE```

## 4. Use the libraries in the project

Tesseract - ```#include <tesseract/baseapi>```<br>
OpenCV - ```#include <opencv2/opencv.hpp>```
CMakePresets.json cannot find environment variables for some reason.

# Setting up a project with vcpkg dependencies

**Important**: Do NOT initialize the project with CMakeTools before hacing CMakePresets.json in place. See section 3. for more detailed explanation.

## 1. Create CMakePresets.json

```json
{
    "version": 3,
    "configurePresets": [
        {
            "name": "default",
            "binaryDir": "${sourceDir}/build",
            "cacheVariables": {
                "CMAKE_TOOLCHAIN_FILE": "D:/Apps/vcpkg/vcpkg/scripts/buildsystems/vcpkg.cmake"
            }
        }
    ]
}
```

Where ```CMAKE_TOOLCHAIN_FILE``` is the path to vcpkg.cmake. Need to research and look into why environment variables do not work.

## 2. Set up vcpkg .jsons

Inside the project root folder, run the following command to initialize the vcpkg-related manifest files:
```vcpkg new --application```

To add a package, use ```vcpkg add port {package name}``` (without the '{}')

## 3. Create CMakeLists.txt

**IMPORTANT**

Either manually create a CMake file or use CMakeTools to do so. Please note, that if you are using CMakeTools, configure the project after setting up CMakePresets.json so that it gets configured properly.<br>
There might be a way to reconfigure it later (by selecting the required preset) but for now it seems to cache the initial preset it runs with and changing it has proven difficult without re-creating the project 

---

3.1 Add project-specific information <br>
3.2 Use ```find_package()``` with the required vcpkg(es)<br>
example: ```find_package(fmt CONFIG REQUIRED)```

3.3 Link the newly added vcpkg with ```target_link_libraries(HelloWorld PRIVATE fmt::fmt)```

## 4. Use the newly added library in your code.

You can now include the new libraries you have <b>and</b> build the project.
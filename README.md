**languages: [English](README.md) · [中文](README_zh.md)**
This document was translated by Youdao Translator.

It took me some time to set up the environment, so I'm posting it here. I hope it can help you save time  : )
note:  The technical capabilities are limited and intended for reference only.

# Premise
VS Code requires the installation of the following plugins

C/C++ Extension Pack
![截图](./png/cxx.png)

Task Buttons
![截图](./png/button.png)

Peacock Enhancement Plugin
![截图](./png/Peacock.png)

Install the following software on the computer

vscode
![截图](./png/vscode.png)

cmake
![截图](./png/cmake.png)

git
![截图](./png/git.png)

ninja build (with environment variables configured)

mingw-gcc

mingw-gdb

# Configuration
## 1. Clone the repository
```
git clone https://github.com/bbbbmmdddd/ImGui-Demo-with-VS-Code-and-CMake.git
```
## 2. Rename the folder (ImGui-Demo-with-VS-Code-and-CMake) to "Your Project Name"

## 3. Modify launch.json
```
// Change "ImGui_vscode_Demo" to "Your Project Name"
"program": "${workspaceFolder}/build/bin/ImGui_vscode_Demo.exe",

// Change "C:\\msys64\\mingw64\\bin\\gdb.exe" to "Your installation path"
"miDebuggerPath": "C:\\msys64\\mingw64\\bin\\gdb.exe",
```

## 4. Modify tasks.json
```
// Change "ImGui_vscode_Demo" to "Your Project Name"
"command": "${workspaceFolder}/build/bin/ImGui_vscode_Demo.exe",
```
### 5. Modify settings.json (Optional)
```
// Change "C:\\Program Files\\LLVM\\bin" to "Your clangd installation path"
"clangd.path": "C:\\Program Files\\LLVM\bin"
```

## 6. Modify Cmakelists.txt
```
// Change "ImGui_vscode_Demo" to "Your Project Name"
project(ImGui_vscode_Demo)

// Change "ImGui_vscode_Demo" to "Your Project Name"
add_executable(ImGui_vscode_Demo ${SRC_FILES} ${IMGUI_SRC})

// Change "ImGui_vscode_Demo" to "Your Project Name"
target_include_directories(ImGui_vscode_Demo PRIVATE
    ImGui
)

// Change "ImGui_vscode_Demo" to "Your Project Name"
target_link_libraries(ImGui_vscode_Demo
    d3d11
    dxgi
    d3dcompiler
    user32
    gdi32
    dwmapi
    ole32
)
```

## 7. Rename the "ImGui_vscode_Demo.code-workspace" file to "Your Project Name".code-workspace

# Usage
Open the "ImGui_vscode_Demo.code-workspace" workspace and you can start coding happily : )

CMake Configure
![截图](./png/CMake%20Configure.png)

CMake Build: Build the project (it needs to execute the Configure step once before it can automatically perform the Configure process)
![截图](./png/CMake%20Build.png)

run Run binary file (Automatically build)
![截图](./png/run.png)

Set shortcut keys to quickly run "run"
```
{
    "key": "f10",
    "command": "workbench.action.tasks.runTask",
    "args": "run"
}
```
# SimpleRunningGame
一个简单的三线跑酷小游戏（未完工），使用 C++ 和 SDL2 编写。

## 项目说明

- 依赖通过 Git Submodule 管理：`third_party/SDL`
- 构建系统：CMake
- 当前推荐构建环境：Windows + MSYS2(UCRT64) + MinGW Makefiles

## 克隆与初始化

```bash
git clone <your-repo-url>
cd SimpleGame-zhx
git submodule update --init --recursive
```

## 环境准备（MSYS2）

在 `MSYS2 UCRT64` 终端安装工具链：

```bash
pacman -S --needed mingw-w64-ucrt-x86_64-toolchain mingw-w64-ucrt-x86_64-cmake mingw-w64-ucrt-x86_64-make
```

## 编译

在项目根目录执行：

```bash
cmake -S . -B build -G "MinGW Makefiles" -DCMAKE_C_COMPILER=gcc -DCMAKE_CXX_COMPILER=g++
cmake --build build
```

## 运行

```bash
./build/SimpleGame.exe
```

> 注意：请从项目根目录运行，程序会读取 `assets/` 资源目录。

## 给别人“直接运行 exe”

如果你要发“无需本地编译”的版本，请打包并发送 `build` 目录中以下内容：

- `SimpleGame.exe`
- `SDL2.dll`
- `libstdc++-6.dll`
- `libgcc_s_seh-1.dll`
- `assets/` 目录

以上文件放在同一层级（`assets` 为子目录）时，可直接双击 `SimpleGame.exe` 运行。

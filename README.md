# UAssetGUI
[![Release](https://img.shields.io/github/v/release/atenfyr/UAssetGUI.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/atenfyr/UAssetGUI/total.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/releases)
[![Issues](https://img.shields.io/github/issues/atenfyr/UAssetGUI.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/issues)
[![CI Status](https://img.shields.io/github/actions/workflow/status/atenfyr/UAssetGUI/build.yml?label=CI)](https://github.com/atenfyr/UAssetGUI/actions)
[![License](https://img.shields.io/github/license/atenfyr/UAssetGUI.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/blob/master/LICENSE.md)

UAssetGUI is a tool designed for low-level examination and modification of Unreal Engine game assets by hand.
 UAssetGUI 是一种工具，用于手动对 Unreal Engine 游戏资产进行低级检查和修改
<img src="https://i.imgur.com/cibmlbW.png" align="center">

## Installation 安装
You can find pre-built binaries of UAssetGUI in the [Releases tab of this repository](https://github.com/atenfyr/UAssetGUI/releases).
您可以在此存储库的 Releases （发布） 选项卡中找到 UAssetGUI 的预构建二进制文件
## Command line arguments命令行参数
You can run the program with command line arguments to perform various tasks, such as exporting and importing from UAssetAPI JSON without opening the GUI.
您可以使用命令行参数运行该程序来执行各种任务，例如从 UAssetAPI JSON 导出和导入，而无需打开 GUI。

In the following cases, the engine version can either be specified as an EngineVersion enum entry (e.g. `VER_UE4_23` to refer to 4.23, `VER_UE5_0` to refer to 5.0, etc.) or as an integer (e.g. `23` to refer to 4.23, `29` to refer to 5.0, etc.). Specifying a set of mappings is optional, but if specified, must be the name of a file within the Mappings config directory (with no extension).
在以下情况下，可以将引擎版本指定为 EngineVersion 枚举条目（例如，VER_UE4_23 表示 4.23，VER_UE5_0 表示 5.0 等）或整数（例如，23 表示 4.23,29 表示 5.0 等）。 指定一组映射是可选的，但如果指定，则必须是 Mappings 配置目录中的文件名称（没有扩展名）。

### Export to JSON 导出为 JSON
```
UAssetGUI tojson <source> <destination> <engine version> [mappings name]
```

Example 1: `UAssetGUI tojson A.uasset B.json VER_UE5_1`

Example 2: `UAssetGUI tojson A.uasset B.json 27 Astro`

### Import from JSON
```
UAssetGUI fromjson <source> <destination> [mappings name]
```

Example 1: `UAssetGUI fromjson B.json A.umap`
示例 1：

Example 2: `UAssetGUI fromjson B.json A.umap Outriders`
示例 2：

### Open a specific file in the GUI 从 JSON 导入
```
UAssetGUI [file name] [engine version] [mappings name]
```

Example 1: `UAssetGUI` (to simply open the GUI without opening a file)
示例 1：

Example 2: `UAssetGUI test.uasset`
示例 2：

Example 3: `UAssetGUI test.uasset 23`
示例 3：

Example 4: `UAssetGUI test.uasset VER_UE5_4 Bellwright`
示例 4：

## Compilation 在 GUI 中打开特定文件
If you'd like to compile UAssetGUI for yourself, read on:
如果您想自己编译 UAssetGUI，请继续阅读：

### Prerequisites 先决条件
* Visual Studio 2022 or later
* Visual Studio 2022 或更高版本
* Git

### Initial Setup 初始设置
1. Clone the UAssetGUI repository:
   克隆 UAssetGUI 存储库：
   
```sh
git clone https://github.com/atenfyr/UAssetGUI.git
```

2. Switch to the new UAssetGUI directory:
   切换到新的 UAssetGUI 目录：
   
```sh
cd UAssetGUI
```

3. Pull the required submodules:
   拉取所需的子模块：
   
```sh
git submodule update --init
```

4. Open the `UAssetGUI.sln` solution file in Visual Studio, right-click on the UAssetGUI project in the Solution Explorer, and click "Set as Startup Project."
   在 Visual Studio 中打开 UAssetGUI.sln 解决方案文件，右键单击解决方案资源管理器中的 UAssetGUI 项目，然后单击“Set as Startup Project”（设置为启动项目）。
   
6. Right-click on the solution name in the Solution Explorer, and press "Restore Nuget Packages."
   右键单击解决方案资源管理器中的解决方案名称，然后按“还原 Nuget 包”。
   
8. Press the "Start" button or press F5 to compile and open UAssetGUI.
   按“开始”按钮或按 F5 编译并打开 UAssetGUI。
   
## Contributing 贡献
Any contributions, whether through pull requests or issues, that you make are greatly appreciated.
非常感谢您所做的任何贡献，无论是通过拉取请求还是 issue。

If you have an Unreal Engine .uasset file that displays "failed to maintain binary equality," feel free to submit an issue on [the UAssetAPI issues page]
如果你的虚幻引擎 .uasset 文件显示“failed to maintain binary equality”，请随时在 UAssetAPI 问题页面上提交问题，并附上相关资源的副本以及游戏名称、[the UAssetAPI issues page]
(https://github.com/atenfyr/UAssetAPI/issues) with a copy of the asset in question along with the name of the game, the Unreal version that it was cooked with, and a mappings file for the game, if needed.
烘焙它的 Unreal 版本和游戏的映射文件。 如果需要。

## License 许可证
UAssetAPI and UAssetGUI are distributed under the MIT license, which you can view in detail in the [LICENSE file](LICENSE).
UAssetAPI 和 UAssetGUI 在 MIT 许可证下分发，您可以在 LICENSE 文件中详细查看该许可证[LICENSE file](LICENSE).

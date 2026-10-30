# artiq 维护说明

用于量子实验的实时控制、编译器、FPGA 固件和主机工具。

- 上游：https://github.com/m-labs/artiq
- 在线文档：https://xiaoshecode.github.io/xiaoshecode/repos/artiq/
- 检查日期：2026-10-30

## 环境与使用

- 按 doc/manual 的 Nix 或 MSYS2 说明准备匹配版本环境。

使用/检查入口（需先满足依赖条件）：

- `阅读 doc/manual/introduction.rst 和 doc/manual/installing.rst。`

## 目录职责

- artiq/compiler/ — 实验语言编译器
- artiq/coredevice/ — 核心设备驱动
- artiq/gateware/ — FPGA 逻辑
- artiq/firmware/ — Rust 固件
- doc/manual/ — 上游手册

## 本次整理

- 新增维护文档和在线文档入口，补全用途、目录、使用路径及验证边界。

## 检查记录

- **仓库目录与入口盘点**（passed）：检查 Git 索引中的 751 个路径、README 和项目配置；不等于功能验收。
- **Python AST**（passed）：557 个文件通过解析；不导入依赖、不执行应用。
- **JSON/notebook parse**（passed）：5 个文件通过解析；不导入依赖、不执行应用。
- **TOML parse**（passed）：17 个文件通过解析；不导入依赖、不执行应用。
- **XML parse**（passed）：3 个文件通过解析；不导入依赖、不执行应用。
- **JavaScript syntax**（passed）：2 个文件通过解析；不导入依赖、不执行应用。
- **完整构建与端到端运行**（not_run）：语法检查排除 11 个编译器测试夹具；未进行 Nix 构建、Rust 交叉编译、FPGA 综合或硬件时序验证。

## 验证边界与待办

- 语法检查排除 11 个编译器测试夹具；未进行 Nix 构建、Rust 交叉编译、FPGA 综合或硬件时序验证。

## 后续维护约定

保留上游许可证与作者信息。沿用现有模块边界和格式配置；修复功能时同步最小回归验证。依赖或接口变更需写明迁移步骤，避免仅为目录美观搬动公开入口。

## 🐧 一、Linux 基本命令简介

Linux 是一种流行的类 Unix 操作系统，主要通过命令行界面（CLI）进行操作。以下是一些最常用的 Linux 命令：

### 🔍 文件/目录相关

| 命令            | 功能说明        |
| ------------- | ----------- |
| `ls`          | 查看当前目录的文件列表 |
| `cd [目录]`     | 切换目录        |
| `pwd`         | 显示当前路径      |
| `mkdir [目录名]` | 创建新目录       |
| `rm [文件名]`    | 删除文件        |
| `rm -r [目录名]` | 递归删除目录      |
| `cp 源 目标`     | 复制文件或目录     |
| `mv 源 目标`     | 移动或重命名文件/目录 |
| `touch [文件名]` | 创建空文件       |
| `cat [文件名]`   | 显示文件内容      |
| `nano` / `vi` | 命令行文本编辑器    |

### 📂 权限与管理

| 命令      | 功能说明       |
| ------- | ---------- |
| `chmod` | 修改权限       |
| `chown` | 修改所有者      |
| `sudo`  | 以管理员权限执行命令 |

### 🔍 系统管理

| 命令             | 功能说明       |
| -------------- | ---------- |
| `top` / `htop` | 查看系统资源使用情况 |
| `ps aux`       | 显示所有进程     |
| `kill [PID]`   | 杀死指定进程     |
| `free -h`      | 显示内存使用情况   |

### 🌐 网络相关

| 命令                  | 功能说明     |
| ------------------- | -------- |
| `ping [地址]`         | 测试网络连接   |
| `curl` / `wget`     | 下载工具     |

---

## 🪟 二、在 Windows 上安装 WSL（适用于 Win10 和 Win11）

WSL 是微软推出的一种在 Windows 上运行 Linux 的子系统，支持大多数 Linux 命令和工具。

### ✅ 安装步骤（推荐使用 WSL 2）

#### 启用 WSL 和虚拟机平台

打开 **PowerShell（管理员权限）**，运行以下命令：

```powershell
wsl --install -d Debian
```

这将自动：

* 启用所需组件
* 安装 WSL 2
* 安装默认的 Debian Linux 发行版

> ⚠️ 如果提示命令不存在或失败，请确保系统更新到最新版本，并尝试以下命令：

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

然后重启电脑。

## 🧪 验证是否成功

安装完成后，在「开始菜单」中打开你安装的 Linux 发行版（如 Debian），第一次运行会初始化并要求你设置用户名和密码。
下面是关于如何使用 `apt`（Advanced Package Tool）在基于 Debian 的 Linux 发行版（如 Ubuntu）中安装软件的详细教程。

---

## 📦 使用 `apt` 安装软件包指南

### 🔧 一、更新软件源

在安装软件前，建议先更新本地软件包列表：

```bash
sudo apt update
```

> 作用：让系统知道有哪些软件是最新版本，但不会实际安装或升级任何软件。

---

### ✅ 二、安装软件

使用以下格式安装软件：

```bash
sudo apt install 软件包名
```

#### 示例：

```bash
sudo apt install git
```

这条命令会安装 Git 版本控制工具。

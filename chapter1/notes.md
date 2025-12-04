# 第1章 システムアーキテクチャ（LPIC-101）

## 📌 第1章学习目标
- 理解 CPU、内存、进程结构
- 掌握 BIOS / UEFI 区别
- 掌握 Linux 启动流程基础（MBR → GRUB → Kernel）
- 了解 systemd 的基本概念（unit, target）
- 理解 runlevel → target 对照关系

---

## 1. 系统结构（System Architecture）

### 🔹 CPU 基础
- 多核心（multi-core）
- 多线程（multi-thread）
- 用户态 / 内核态（User mode / Kernel mode）

### 🔹 内存
- 物理内存（RAM）
- 虚拟内存（swap）

### 🔹 进程 & 程序
- 程序：静态文件
- 进程：正在执行的程序实例 
（PID、PPID、子进程等）

---

## 2. 启动流程（Boot Process）

### 🔸 BIOS / UEFI
| 项目 | BIOS | UEFI |
|------|------|------|
| 分区 | MBR | GPT |
| 限制 | 2TB | 无 |
| 启动画面 | 简单 | 图形化 |

### 🔸 启动流程（关键考点）
1. BIOS/UEFI 
2. 读取 MBR / GPT 
3. 加载 GRUB 
4. 内核加载（vmlinuz） 
5. 启动 init → systemd

---

## 3. systemd 基础（101版本仅需基础）

- `systemctl status` 
- `systemctl start/stop` 
- unit 文件基本认识 
- target（重点）

| Target | 旧 runlevel |
|--------|--------------|
| multi-user.target | runlevel 3 |
| graphical.target | runlevel 5 |

---

## 4. 易错点总结（今天记得补充！）
- BIOS 是 MBR，不支持超过 2TB 
- systemd 的 default target 是 `/etc/systemd/system/default.target` 
- GRUB 在 101 不考深度，但流程必须记住

---

## 5. 今日操作记录（你学完记得补上）

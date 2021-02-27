<h1 align="center"> Macchina </h1>

<p align="center">
  <img src="screenshots/preview.png"/>
  <a href="https://forthebadge.com/images/badges/made-with-rust.svg" alt="Made With Rust Badge"></a>
</p>

[![Crates.io](https://img.shields.io/crates/v/macchina?style=for-the-badge&label=VERSION&color=0D3B66)](https://crates.io/crates/macchina)
[![Crates.io](https://img.shields.io/crates/d/macchina?style=for-the-badge&label=DOWNLOADS&color=0D3B66)](https://crates.io/crates/macchina)
![reposize](https://img.shields.io/github/repo-size/grtcdr/macchina?color=0D3B66&logo=github&style=for-the-badge)
![loc](https://img.shields.io/tokei/lines/github/grtcdr/macchina?color=0D3B66&label=Lines%20of%20Code&logo=rust&style=for-the-badge)

## Table of Contents:
- [About](#about)
- [Changelog](#change)
- [Benchmarks](#bench)
- [Features](#features)
- [Installation](#install)
- [Platform Support](#platform-support)

---

# About Macchina <a name="about"></a>
Macchina lets you view basic system information, like your hostname, your kernel version, memory usage, and much more.
No one wants a slow fetcher, and Macchina's main goal is to provide you with handy features while keeping performance a priority.

# Changelog <a name="change"></a>
The most recent commits have focused primarily on supporting BSD systems, Macchina previously panicks at almost every step on a BSD system, because it obtained machine information through files that might not exist on non-Linux systems.
Although the coming pushes to the repository might not be efficient, I will always work to keep Macchina under the 50ms threshold!

- Read distribution name through `lsb_release` instead of reading the contents of `/etc/os-release`
- Uppercase first letter of the terminal instance name and desktop environment

---

# Benchmarks <a name="bench"></a>
Macchina is pretty fast, see for yourself:

- Execution time is measured using [hyperfine](https://github.com/sharkdp/hyperfine)

| Command | Mean [ms] | Min [ms] | Max [ms] | Relative |
|:---|---:|---:|---:|---:|
| `macchina` | 22.2 ± 0.7 | 21.0 | 25.1 | 1.00 |
| `neofetch` | 243.9 ± 2.3 | 240.0 | 246.9 | 11.01 ± 0.37 |

__Summary__: `macchina` runs __11.01 ± 0.37__ times __faster__ than `neofetch`

- Note that hiding elements using Macchina's __--hide <element>__ significantly improves speed

---

# Features <a name="features"></a>
## Themes:
![Theme preview](screenshots/theme_preview.png)

## Macchina displays basic system information such as:
- Host
  - Username
  - Hostname
- Product
  - Manufacturer
  - Model name
- Distribution
- Desktop Environment
- Kernel version
- Package count
- Shell
- Terminal
- Processor
  - Model name
  - Frequency
  - Thread count
- Uptime
- Memory
  - Used / Total
- Battery
  - Percentage
  - Status
- Palette

> Package count: __Pacman only__, as it will print __0__ for distributions that use any other package manager. Support for other package managers is on its way.

## Macchina supports the following arguments:

`--no-color / -n` - Disable colors

`--color / -c <color>` - Specify the key color

`--separator-color / -C <color>` - Specify the separator color

`--random-color / -r` - Let Macchina pick a random color for you

`--palette / -p` - Display palette

`--short-sh / -s` - Shorten shell output (/bin/zsh -> zsh)

`--hide / -H <element>` - Hide elements such as host, os, kern, etc.

`--bar / -b` - Display memory usage and battery percentage as bars

![Preview of bar argument](screenshots/bars.png)

`--theme / -t <theme_name>` - Specify the theme to use

`--padding / -P <amount>` - Specify the amount of (left) padding to use

`--spacing / -S <amount>` - Specify the amount of spacing to use

`--help / -h` -  Print help text

`--version / -v` - Print version

---

# Installation <a name="install"></a>
Macchina is available on:

- [AUR](https://aur.archlinux.org/packages/macchina/)

  Install using your favorite AUR helper or by running:
  ```
  git clone https://aur.archlinux.org/macchina.git
  cd macchina
  makepkg -si
  ```
- [crates.io](https://crates.io/crates/macchina)

  Install using cargo:
  ```
  cargo install macchina
  ```

---

# Platform Support <a name="platform-support"></a>

|  Platform     |      Support       |
| :-:           |        :-:         |
| Linux         | :heavy_check_mark: |
| BSD           |     :question:     |
| MacOS         |                    |
| Windows       |                    |

Cells containing :heavy_check_mark:: Macchina supports that platform

Cells containing :question:: Macchina has not been tested yet on that platform

Empty cells: Macchina does not support that platform

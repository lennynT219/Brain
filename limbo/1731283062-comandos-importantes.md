---
id: 1731283062-comandos-importantes
aliases:
  - Comandos importantes
tags: []
---

# Comandos importantes

<!--toc:start-->
- [Comandos importantes](#comandos-importantes)
  - [Comandos de activacion](#comandos-de-activacion)
    - [Office](#office)
  - [Comandos de instalación](#comandos-de-instalación)
    - [Nvim](#nvim)
    - [Git](#git)
    - [Chocolatey](#chocolatey)
    - [Lazygit](#lazygit)
    - [Fd](#fd)
    - [Ripgrep](#ripgrep)
    - [Zig](#zig)
    - [Zoxide](#zoxide)
    - [Starship](#starship)
    - [Maven](#maven)
    - [Jabba](#jabba)
    - [Mingw](#mingw)
    - [Fzf](#fzf)
    - [Make](#make)
    - [Fnm](#fnm)
    - [Terminal-Icons](#terminal-icons)
    - [Bun](#bun)
    - [Scoope](#scoope)
    - [Openssl](#openssl)
    - [Cloudflare](#cloudflare)
<!--toc:end-->

## Comandos de activacion

### Office

```bash
irm https://get.activated.win | iex
```

## Comandos de instalación

### Nvim

```bash
winget install NeoVim.NeoVim
```

### Git

```bash
winget install --id=Git.Git -e --source winget
```

### Chocolatey

```bash
winget install Chocolatey.Chocolatey
```

### Lazygit

```bash
winget install jesseduffield.lazygit
choco install lazygit
```

### Fd

```bash
winget install sharkdp.fd
```

### Ripgrep

```bash
winget install --id BurntSushi.ripgrep.GNU
```

### Zig

```bash
winget install --id=Zig.Zig
```

### Zoxide

```bash
 winget install --id ajeetdsouza.zoxide
```

### Starship

```bash
winget install --id=Starship.Starship
```

### Maven

```bash
choco install maven
```

### Jabba

```bash
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
Invoke-Expression (Invoke-WebRequest
https://github.com/shyiko/jabba/raw/master/install.ps1 -UseBasicParsing).Content

choco install jabba
```

### Mingw

```bash
choco install mingw
```

### Fzf

```bash
choco install fzf
```

### Make

```bash
winget install --id GnuWin32.Make -e --source winget
```

### Fnm

```bash
winget install --id Schniz.fnm -e --source winget
```

### Terminal-Icons

```bash
Install-Module -Name Terminal-Icons -Repository PSGallery
Import-Module Terminal-Icons
```

### Bun

```bash
powershell -c "irm bun.sh/install.ps1|iex"
```

### Scoope

```bash
Set-ExecutionPolicy RemoteSigned -scope CurrentUser
irm get.scoop.sh | iex
```

### Openssl

```bash
winget install ShiningLight.OpenSSL.Dev
```

### Cloudflare

```bash
winget install --id Cloudflare.cloudflared
```

### Gradle

```bash
choco install gradle
```

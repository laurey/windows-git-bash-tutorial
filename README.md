# Windows 10 系统配置集成 Git Bash 的 Terminal 开发环境教程

## [Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/) 集成步骤

> NOTE : `Windows Terminal` 需要 Windows 10 1903 (build 18362) 或更高版本, 如需要请下载并安装 [本地升级包](resources/Windows10Upgrade9252.exe)

1. `Windows Terminal` 安装要求、方式及步骤 [点此进入](https://github.com/microsoft/terminal#installing-and-running-windows-terminal)
2. 下载安装 `Git for Windows`, [下载地址](https://git-scm.com/download/win)
3. 启动 `Git for Windows`, 将 [`.profile`](resources/.profile) 和 [`.bash_aliases`](resources/.bash_aliases) 文件复制到用户家目录(如: `C:\Users\God` 目录)
4. 重启或关闭 `Git for Windows`， 启动 `Windows Terminal`。 按下 `Ctrl+,` 键打开配置文件，进行配置设置
5. 新增 `Git Bash Profile` 示例如下, 具体配置及说明见 [文档](https://docs.microsoft.com/en-us/windows/terminal/customize-settings/profile-settings)

```
  {
    "defaults": {
      // SETTINGS TO APPLY TO ALL PROFILES
    },
    "list": [
      // PROFILE OBJECTS
      // 此处增加如下配置
      {
        // Git-Bash profile
        "guid": "{9b433567-0000-0000-0000-bafeb90509ac}", // guid 可自定义，需保证唯一性
        "name": "Git-Bash", // name 可自定义
        "commandline": "%PROGRAMFILES%\\Git\\bin\\bash.exe --login -i -l",
        "icon": "%PROGRAMFILES%\\Git\\mingw64\\share\\git\\git-for-windows.ico",
        "startingDirectory": "~"  // 默认开始目录， 可自定义
      }
    ]
  }
```

6. 重启 `Windows Terminal`， 下拉菜单选择 `Git-Bash`

## Windows VSCode 集成步骤

1. 开启 [Visual Studio Code](https://code.visualstudio.com/docs/editor/integrated-terminal) 集成终端
2. 选择默认 Shell 为 `Git Bash`
3. 新建终端即可使用 `Git Bash`

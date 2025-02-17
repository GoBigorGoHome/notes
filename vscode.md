# 设置快捷键：把当前行滚动到屏幕上部

1. 安装扩展 [Commands](https://marketplace.visualstudio.com/items?itemName=usernamehw.commands)
2. Ctrl+Shift+P，输入 Open User Settings (JSON)，打开用户设置文件 settings.json
3. 在 settings.json 里加入
   ```json
   "commands.commands": {
        "scrollTop": {
            "command": "revealLine",
            "args": {
                "lineNumber": "${lineNumber}",
                "at": "top",
            }
        }
   }
   ```
4. Ctrl+Shift+P，输入 Open Keyboard Shortcuts (JSON)，打开快捷键设置文件 keybindings.json
5. 在 keybindings.json 里加入
   ```json
   {
        "key": "ctrl+t", // or whatever bindings you choose
        "command": "scrollTop",
   }
   ```

learned from https://github.com/microsoft/vscode/issues/112665#issuecomment-968156222

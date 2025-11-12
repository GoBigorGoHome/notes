# 可执行文件格式

可执行文件是链接器把目标文件链接所得到的。目标文件和可执行文件的格式是同一格式的。

Linux 使用的可执行文件格式是 ELF。  
Windows 使用的可执行文件格式是 PE。

链接器 [mold](https://github.com/rui314/mold) 暂不支持生成 PE 格式的可执行文件。相关讨论
- https://github.com/rui314/mold/issues/190
- https://github.com/rui314/mold/discussions/346

# 把默认浏览器设置为 Chrome

检查当前的默认浏览器
```bash
xdg-settings get default-web-browser
```
设置
```bash
xdg-mime default google-chrome.desktop x-scheme-handler/http
xdg-mime default google-chrome.desktop x-scheme-handler/https
```


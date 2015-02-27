---
layout:     post
title:      "sublimetext学习笔记(持续更新)"
date:       2015-02-27 16:23:00
categories: online
author:     "金鑫"
header-img: "img/post-bg-03.jpg"
---

## package controller 安装(st3)
快捷键`ctrl+``,输入

```python
import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```

## package controller安装之后不显示
打开 `Preferences.sublime-settings` 文件,删除`Package Control`

```json
{
  "ignored_packages":
  [
  	"Vintage",
  	"Package Control"
  ]
}
```

## package controller无法下载
打开`C:\windows\system32\drivers\etc\hosts`,增加

```
50.116.34.243   sublime.wbond.net
```

## git 插件修改 git_command属性

```json
"git_command": "E:/Program Files/Git/bin/git.exe"
```

---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Pagi ini, ketika saya mau setup printer merk HP muncul error seperi berikut ini:
```shell
[sumarsono@mesin-arch ~]$ hp-setup 

HP Linux Imaging and Printing System (ver. 3.17.9)
Printer/Fax Setup Utility ver. 9.0

Copyright (c) 2001-15 HP Development Company, LP
This software comes with ABSOLUTELY NO WARRANTY.
This is free software, and you are welcome to distribute it
under certain conditions. See COPYING file for more details.

Traceback (most recent call last):
  File "/usr/bin/hp-setup", line 313, in <module>
    ui = import_module(ui_package + ".setupdialog")
  File "/usr/lib/python3.6/importlib/__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
  File "<frozen importlib._bootstrap>", line 978, in _gcd_import
  File "<frozen importlib._bootstrap>", line 961, in _find_and_load
  File "<frozen importlib._bootstrap>", line 950, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 655, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 678, in exec_module
  File "<frozen importlib._bootstrap>", line 205, in _call_with_frames_removed
  File "/usr/share/hplip/ui5/setupdialog.py", line 31, in <module>
    from base import device, utils, models, pkit
  File "/usr/share/hplip/base/pkit.py", line 38, in <module>
    from gi import _gobject as gobject
ImportError: cannot import name '_gobject'

```

### Solusi
Sangat mudah, cukup install `python-gobject` sudah beres.

Profit, happy printing.
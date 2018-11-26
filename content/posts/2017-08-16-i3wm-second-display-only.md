---
title: "i3wm Second Display Only" 
date: 2017-08-16T20:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Sudah 3 hari saya memakai i3wm di mesin arch linux saya. Bukan apa-apa sih, hanya iseng saja. Kebetulan hari ini, saya menghubungkan mesin ke external monitor yang resolusinya lebih besar yaitu 1440x900.

Sempat bingung, bagaimana caranya agar display di laptop mati, dan eksternal display ON karena secara default saya berada dalam mode *mirror*. Ternyata caranya cukup simple.

* jalankan `xrandr`

```shell-script
[sumarsono@mesin-arch ~]$ xrandr
Screen 0: minimum 8 x 8, current 1440 x 900, maximum 32767 x 32767
LVDS1 connected primary (normal left inverted right x axis y axis)
   1280x800      59.99 +  50.00  
   1024x768      60.00  
   800x600       60.32    56.25  
   640x480       59.94  
   640x400       60.00  
DP1 disconnected (normal left inverted right x axis y axis)
DP2 disconnected (normal left inverted right x axis y axis)
DP3 disconnected (normal left inverted right x axis y axis)
HDMI1 disconnected (normal left inverted right x axis y axis)
HDMI2 disconnected (normal left inverted right x axis y axis)
VGA1 connected 1440x900+0+0 (normal left inverted right x axis y axis) 420mm x 260mm
   1440x900      59.90*+
   1280x1024     60.02  
   1280x800      59.81  
   1152x864      75.00  
   1280x720      60.00  
   1024x768      75.03    60.00  
   832x624       74.55  
   800x600       75.00    60.32    56.25  
   640x480       75.00    59.94  
   720x400       70.08  
VIRTUAL1 disconnected (normal left inverted right x axis y axis)
[sumarsono@mesin-arch ~]$
```
* jalankan perintah berikut agar VGA1 hidup dab LVDS1 Matikan

```shell-script
xrandr --output VGA1 --mode 1440x900 --output LVDS1 --off
```
* Profit !

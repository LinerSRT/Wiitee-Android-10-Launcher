#### Wiite Android 10 Launcher for regular Smart-Watches
---------------------------------

![](https://img.shields.io/badge/API%20Target-29-green) **Android 10**

![](https://img.shields.io/badge/API%20Min-24-orange) ** Android 7.0** *(Downgraded)*

![](https://img.shields.io/badge/Package-com.wiite.home-blue)



---------------------------------
<div><p style="float: left;"><img src="https://cdn1.iconfinder.com/data/icons/color-bold-style/21/56-512.png" height="32" width="32"></p><p><h3>Removed</h3></p>
</div>

* Fintess screens* (Require special apps in system directory with modded framework!)

* Weather screens* (Require special apps in system directory with modded framework!)

* Notifications? Give permissions nad its should work properly.

It also included new ClockSkin engine, wich supports `*.gif`, `*.mp4 `and LiveWallpapers as resource. Am make some research and there what i got. 

First of all Wiitee added new config file, named as "**live_config.xml**"
Wich contains:
```xml
<liveconfig>
	<pkg>com.jonasl.GLES20MatrixCubes3.livewallpaper</pkg>
	<service>com.jonasl.GLES20MatrixCubes3.livewallpaper.LiveWallpaperService</service>
</liveconfig>
```

---------------------------------
<div><p style="float: left;"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/25/Info_icon-72a7cf.svg/1200px-Info_icon-72a7cf.svg.png" height="32" width="32"></p><p><h3>Tag explanation</h3></p>
</div>

**PKG** - Package name of app with live wallpapers

**SERVICE** - Live wallpaper service from app

---------------------------------
<div><p style="float: left;"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Gear_icon-72a7cf.svg/1200px-Gear_icon-72a7cf.svg.png" height="32" width="32"></p><p><h3>How it works?</h3></p>
</div>

Place new config file in folder with **clockskin.xml**, remove full screen images from watchface. 
Edit folowing tags with wanted live wallpaper, and launcher automaticaly try to apply it if you choose new clock.
So idea is simple, as background in engine wiitee use transparent (lets, call it color, but in real its using nothing :D ) color, and if engine can find new config file, its automaticaly apply wallpaper, and engine show those wallpaper as background on watchface. Other layers are same as previous versions. 


*Im use it in my beta version of launcher (yup, it can show live wallpapers, gifs and musch more, but some settings are hidden. Cause it have not much stability)*



---------------------------------
<div><p style="float: left;"><img src="https://d1nhio0ox7pgb.cloudfront.net/_img/g_collection_png/standard/512x512/sign_warning.png" height="32" width="32"></p><p><h3>Warning!</h3></p>
</div>

If you want use this new feature with modded launcher apk:

1. Place modded launcher into your `system/priv-app/` directory
Edit AndroidManifest.xml from framework-res.apk steps:
1. Extract AndroidManifest.xml from apk
2. Find in manifest :
```xml
<permission android:name="android.permission.BIND_WALLPAPER" android:protectionLevel="signature"/>
```
and change it to:
```xml
<permission android:name="android.permission.BIND_WALLPAPER" android:protectionLevel="normal"/>
```
4. Repack framework-res.apk with new manifest and replace it in system.

Now all apps have acces to set livewallpapers in your device without errors, and new launcher can show new watchfes format without errors.

Thanks, for your atention, all files and exapmles you can find in this repository


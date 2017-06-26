# Using Adaptive icons in the Android O Developer Preview

**This documentation is subject to change at any time**


I found the google documentation on creating an application with adaptive icons quite lacking(and incorrect). This guide will hopefully serve as some better documentation.

#### Step 1 - Create a project targeting the Android O preview in android studio
   If you already have a project, you can skip this step
   
#### Step 2 - Add a mipmap-anydpi and mipmap folder to the /app/src/main/res/ folder of your project
   ![res folder](https://raw.githubusercontent.com/kfechter/Adaptive-Icons-Help/master/Screenshots/resfolder.PNG)
   
   
#### Step 3 - Create a file called ic_launcher.xml in the /app/src/main/res/mipmap-anydpi folder.
**It should have the following contents:**

    <?xml version="1.0" encoding="utf-8"?>
    <adaptive-icon xmlns:android="http://schemas.android.com/apk/res/android">
        <background android:drawable="@color/ic_background"/>
        <foreground android:drawable="@mipmap/ic_foreground"/>
    </adaptive-icon>
    
**NOTE: the ic_foreground.png goes in the /app/src/main/res/mipmap folder**     

   ![mipmap folder](https://raw.githubusercontent.com/kfechter/Adaptive-Icons-Help/master/Screenshots/mipmapfolder.PNG)
   
**NOTE: a color with the name ic_background should be added to /app/src/main/res/values/colors**

    <?xml version="1.0" encoding="utf-8"?>
    <resources>
          <color name="colorPrimary">#3F51B5</color>
          <color name="colorPrimaryDark">#303F9F</color>
          <color name="colorAccent">#FF4081</color>
          <color name="ic_background">#555555</color>
    </resources>

At this point, an app targeting Android O (`buildToolsVersion 26.0.0`+) should use the new icon resource.

#### Step 4 - Working with legacy devices

Most apps will also need to run on pre-O Android devices, which do not have support for adaptive icons. The built in Android 3.0 Adaptive Icon Wizard will not perform the following step, but it is essential for legacy support.

Rename the `mipmap-anydpi` folder to `mipmap-anydpi-v26`, so that only newer versions of Android try to use the adaptive icons. Launcher icons can then be put in the relevant density folder as normal.

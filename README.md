# Using Adaptive icons in the Android O Developer Preview

** This documentation is subject to change at any time **


I found the google documentation on creating an application with adaptive icons quite lacking(and incorrect). This guide will hopefully serve as some better documentation.

#### Step 1 - Create a project in android studio
   If you already have a project, you can skip this step
   
#### Step 2 - Add a mipmap-anydpi and mipmap folder to the /app/src/main/res/ folder of your project

#### Step 3 - create a file called ic_launcher.xml to the /app/src/main/res/mipmap-anydpi folder.
it should have the following contents

    <?xml version="1.0" encoding="utf-8"?>
    <adaptive-icon xmlns:android="http://schemas.android.com/apk/res/android">
        <background android:drawable="@color/ic_background"/>
        <foreground android:drawable="@mipmap/ic_foreground"/>
    </adaptive-icon>
    
** NOTE: the ic_foreground.png goes in the /app/src/main/res/mipmap folder **
** NOTE: with ic_background as a color, a color with the name ic_background should be added to /app/src/main/res/values/colors **

At this point, an app targeting android O should use the new icon resource.

// TODO: Add Screenshots

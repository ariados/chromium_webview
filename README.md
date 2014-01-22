ChromiumWebView
================

Android WebView wrapper based on chromium

## Android Studio Fork

This is the [Chromium Webview project](https://github.com/mojoweb/chromium_webview)
with the library component converted to Gradle.

Gradle tools 0.7.3 is required for its halfassed ndk support.

## Setting Up

This section explains how to set up your Android project to use ChromiumWebView.

### Get the Code

Add the "java" directory (feel free to rename) to your project as a module dependency.
Since AS isn't very good at importing I would copy the directory over and modify
settings.gradle to include it.

### Copy Data

Copy `assets/webviewchromium.pak` to your project's `src/main/assets` directory. Also copy the
src/main/jniLibs directory to your main app project since that doesn't work automatically
in gradle tools 0.7.3.

### Initialize

In your Application subclass, call ChromeIntializer.initialize and pass it the 
application's context. For example,

```java
import com.mogoweb.chrome.ChromeInitializer;
import android.app.Application;

public class MyApplication extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        ChromeInitializer.initialize(this);
    }
}
```

Now you can use ChromiumWebView as the same as Android WebView except for different
package name.

### Copyright and License

The directories below contain code from the
[The Chromium Project](http://www.chromium.org/), which is subject to the
copyright and license on the project site.

* `assets/`
* `libs/`
* `src/com/googlecode`
* `src/org/chromium`

Some of the source code in `src/com/mogoweb/chrome` has been derived from the
Android source code, and is therefore covered by the
[Android project licenses](http://source.android.com/source/licenses.html).

The rest of the code is Copyright 2013 mogoweb, All rights reserved. Use of 
this source code is governed by a BSD-style license that can be found in the LICENSE file.

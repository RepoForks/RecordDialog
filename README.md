# RecordDialog <a href="https://github.com/IvanSotelo/RecordDialog#how-to-include"><img src="https://jitpack.io/v/IvanSotelo/RecordDialog.svg"></a>
  <a target="_blank" href="https://android-arsenal.com/api?level=18"><img src="https://img.shields.io/badge/API-18%2B-brightgreen.svg"></a>
  <a target="_blank" href="https://travis-ci.org/IvanSotelo/RecordDialog"><img src="https://travis-ci.org/IvanSotelo/RecordDialog.svg?branch=master"></a>
  <a target="_blank" href="https://www.paypal.me/IvanSotelo" title="Donate using PayPal"><img src="https://img.shields.io/badge/paypal-donate-brightgreen.svg" /></a>
A Simple Wav audio recorder dialog

![Screen Shot](https://raw.githubusercontent.com/IvanSotelo/RecordDialog/master/20180226_122509.gif)
---

## Releases:

#### Current release: 1.0.0.

You can see all the library releases [here](https://github.com/IvanSotelo/RecordDialog/releases).

---

## Usage:

#### Permissions
Add these permissions into your `AndroidManifest.xml` and [request for them in Android 6.0+](https://developer.android.com/training/permissions/requesting.html) Min API: 18
```xml
<uses-permission android:name="android.permission.RECORD_AUDIO"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```

#### Adding the depencency

Add this to your root *build.gradle* file:

```
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

Now add the dependency to your app build.gradle file:

```groovy
compile 'com.github.IvanSotelo:RecordDialog:1.0.0'
```

### Creating the dialog with Java

Here is a complete snippet of it usage:

```java
        findViewById(R.id.button).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                recordDialog = RecordDialog.newInstance(R.string.app_name);
                recordDialog.show(MainActivity.this.getFragmentManager(),"TAG");
                recordDialog.setPositiveButton(android.R.string.save, new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                        Toast.makeText(MainActivity.this,"Save audio: "+recordDialog.getAudioPath(), Toast.LENGTH_LONG).show();
                    }
                });
            }
        });
```

### Download
--------
#### Gradle
```groovy
compile 'com.ivansotelo.RecordDialog:1.0.0'
```

##### Maven
```xml
<dependency>
  <groupId>com.ivansotelo</groupId>
  <artifactId>RecordDialog</artifactId>
  <version>1.0.0</version>
  <type>aar</type>
</dependency>
```

## License

```
The MIT License (MIT)

Copyright (c) 2017Ivan Sotelo Vargas

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

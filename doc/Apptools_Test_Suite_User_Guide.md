# Apptools Test Suite User Guide

## 1. Introduction

This document provides method to run Apptools TestSuite. Currently the target platforms are Android, iOS, Linux and Windows

## 2. Setup Environment on Linux host

### 1. Android Platform

1. Install Python,version is 2.7.6

2. Install Android SDK ,JDK, git

3. Install apache-ant-1.9.6 (Download from http://www.onlinedown.net/softdown/77637_2.htm)

4. Install node and npm (node version is 0.10.30,npm version is 1.4.21)

5. Install setuptools module (Download from https://pypi.python.org/pypi/setuptools)

6. Modify the ~/.bashrc
  1) For JDK environment:
     export PATH=$PATH:/usr/lib/jvm/jdk1.6.0_45/bin:/usr/lib/jvm/jdk1.6.0_45/jre/bin
  2) For Ant environment:
     export ANT_HOME=$PATH:/usr/local/apache-ant-1.9.6
  3) For Android SDK environment:
     export PATH=$PATH:/home/qawt/Tools/adt-bundle-linux/sdk:/home/qawt/Tools/adt-bundle-linux/sdk/tools:/home/qawt/Tools/adt-bundle-linux/sdk/platform-tools

## 3. Setup Environment on OS X host

### 1. Android Platform

1. Install Python, suggest version 2.7.6 
  1) Download from https://www.python.org/downloads/mac-osx/
  2) Right-click (or control-click) the application in question and choose "Open"
  3) Click the "Open" button at the next dialog warning to launch the app anyway

2. Install Android SDK for Mac (Download from www.androiddevtools.cn , may be you need install SDK tools for SDK (www.pan.baidu.com/s/1eQsHgI2))

3. Install JDK for Mac(jdk-7u79-macosx-x64.dmg) (Download from www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html)

4. Install apache-ant-1.9.6 (Download from http://www.onlinedown.net/softdown/77637_2.htm) 
        ```
         $ sudo sh  
         $ cp apache-ant-1.6.5-bin.zip /usr/local/  
         $ cd /usr/local/  
         $ unzip apache-ant-1.6.5-bin.zip
         $ ln -s apache-ant-1.6.5 ant
        ```

5. Install node and npm (node version is 0.10.30,npm version is 1.4.21)

6. Install brew on Mac.you must agree to the license by opening Xcode.app or running(install step refer to http://jingyan.baidu.com/article/335530da8b2b0419cb41c338.html)

7. Setup Environment
  1) For Ant environment:
     export ANT_HOME=/usr/local/apache-ant-1.9.6
  2) For Android SDK environment:
     export PATH=$PATH:/Users/WebQA/Library/Android/sdk:/Users/WebQA/Library/Android/sdk/platform-tools:/Users/WebQA/Library/Android/sdk/tools:

### 2. iOS Platform

1. Install Xcode 7.1(ios SDK) from App store on Mac

2. Install Python,version is 2.7.6 s(Download from https://www.python.org/downloads/mac-osx/)
  1) Right-click (or control-click) the application in question and choose "Open"
  2) Click the "Open" button at the next dialog warning to launch the app anyway

3. Make sure node version is 4.2.1

4. Install git and ruby.(it should be pre-installed on your Mac already.)

5. Install CocoaPods through ruby gem: sudo gem install cocoapods(install step please refer to http://blog.csdn.net/wangyang2698341/article/details/22678027 and http://www.jianshu.com/p/6e5c0f78200a )

6. IDE error occurs, the ipa project has been built, but it “fail to export application. with return code：70”, here is the Way to export iOS package with smaller size.
  1) After your create, go to the App shell directory:  cd prj/ios/AppShell/
  2) Open archived.xcarchive with Xcode:  open archived.xcarchive. You will see a Xcode Organiser window is opened.
  3) Select the archive in the list, click ‘Export…” button at right side bar, choose “Save for Ad Hoc Deployment”, then next;
  4) After the account validation, select “Export one app for All compatible devices” in Device Support page, then next;
  5) In the summary page, select “Rebuild from bitcode”, which is the way to save the package size.
  6) Then next, Xcode will start the exporting process and finally an IPA package will be generated onto your desktop.
  7) After this, the “Rebuild from bitcode” will be kept selected, no matter if you export from Xcode IDE or command line with crosswalk-app.

## 4. Setup Environment on Deepin host

### 1. Linux Platform

1. Download Crosswalk test binary (64bit) from http://pan.baidu.com/ (user: crosswalk_deepin@163.com)

2. Install Crosswalk Binary:
   dpkg -i crosswalk_13.41.302-0_amd64.deb

3. The Node.js, Android SDK, JDK, apache ant and git must be functional

4. Modify the ~/.zshrc to setup Environment:

   `export ANDROID_HOME=$(dirname $(dirname $(which android)))`

5. Enable .deb Backend in App Tools
        ```
          apt-get install devscripts
          apt-get install build-essential
          apt-get install debhelper
        ```

## 5. Setup Environment on Windows host

### 1. Android Platform

1. Install Python,version is 2.7.6

2. Install Android SDK ,JDK for Windows

3. Install apache-ant-1.9.6 (Download from http://www.onlinedown.net/softdown/77637_2.htm)

4. Install node and npm (node version is 0.10.30,npm version is 1.4.21)

5. Install setuptools module (Download from https://pypi.python.org/pypi/setuptools)

6. Setup Environment:
  1) For Android SDK environment:
     $PATH;C:\Users\weiwei2X\Downloads\android-sdk_r24.2-windows\android-sdk-windows\platform-tools;C:\Users\weiwei2X\Downloads\android-sdk_r24.2-windows\android-sdk-windows;C:\Users\weiwei2X\Downloads\android-sdk_r24.2-windows\android-sdk-windows\tools;
  2) For npm and node environment:
     $PATH;C:\Program Files\nodejs\;C:\Program Files\nodejs\node_modules\npm;C:\Program Files\nodejs\node_modules\ms
  3) For ANT environment:
     $PATH;C:\Users\weiwei2X\Downloads\apache-ant-1.9.6-bin\apache-ant-1.9.6\bin

### 2. Windows Platform

1. Install WiX per https://msdn.microsoft.com/en-us/library/gg513936.aspx (do not forget to add the WiX tools to the windows path environment variable)

2. Install node and git.

3. Setup Environment:
  1) For Python environment:
     $PATH;C:\Python27;C:\Python27\Scripts;C:\Python27\Lib
  2) For Wix environment:
     $PATH;C:\Program Files (x86)\WiX Toolset v3.9\bin

## 6. Precondition for AppTools
        ```
          $ Unzip testsuit zip
          $ cd opt/apptools-xxx-tests/tools/
          $ git clone https://github.com/crosswalk-project/crosswalk-app-tools
          $ cd crosswalk-app-tools/
        ```

### 1. Android Platform
        ```
          $ sudo npm install
          $ sudo npm install exec-sync
        ```
1. Setup Environment: export CROSSWALK_APP_TOOLS_CACHE_DIR=/path/to/opt/apptools-android-tests/tools

2. Install BeautifulSoup: `sudo pip install BeautifulSoup`

3. Install webp conversion tool from http://downloads.webmproject.org/releases/webp

4. Connect Android devices to your localhost

5. Need to edit the file "apptools-android-tests/arch.txt" according to the type of test device.
   If test device is "arm" platform, content of the file should be "arm". If test device is "x86" platform, content of the file should be "x86".
   If test devices are "arm" and "x86" platforms, content of the file should be "arm,x86", default value is "x86,arm"

6. Need to edit the file "apptools-android-tests/mode.txt" according to the type of build mode.
   If create project with crosswalk lite zip, content of the file should be "lite". If create project with crosswalk zip and build "shared" mode apk, content of the file should be "shared". If create project with crosswalk zip and build "embedded" mode apk, content of the file should be "embedded".
(Note: If you test "shared" mode, when uninstall crosswalk runtime library from android device before testing, it will be prompted to download crosswalk runtime library from google play in formal test process.)

7. Need to edit the file "apptools-android-tests/host.txt" according to the type of test host.
   If test host is "Windows" platform, content of the file should be "Windows", default value is "Android".

8. Need to edit the file "apptools-android-tests/version.txt" according to the Crosswalk which you want to test.
   For example: if you want to test with "crosswalk-17.45.434.0.zip", content of the file should be "17.45.434.0 32". If you want to test with "crosswalk-17.45.434.0-64bit.zip", content of the file should be "17.45.434.0 64".

9. Download release crosswalk zip to apptools-android-tests/tools from https://download.01.org/crosswalk/releases/crosswalk/android/

### 2. iOS Platform

        ```
          $ npm install
          $ cd node_modules
          $ git clone https://github.com/crosswalk-project/crosswalk-app-tools-ios.git crosswalk-app-tools-backend-ios
          $ cd crosswalk-app-tools-backend-ios
          $ npm install
        ```
1. Connect iOS devices to your localhost

### 3. Linux Platform

        ```
          $ npm install
          $ cd node_modules
          $ git clone https://github.com/crosswalk-project/crosswalk-app-tools-deb.git crosswalk-app-tools-backend-deb
          $ cd crosswalk-app-tools-backend-deb
          $ npm install
        ```
1. Add crosswalk-app-tools/src/ to environment PATH

### 4. Windows Platform

        ```
          $ npm install
        ```
1. Setup Environment: export CROSSWALK_APP_TOOLS_CACHE_DIR=/path/to/opt/apptools-windows-tests/tools

2. Install BeautifulSoup: `pip install BeautifulSoup`

3. Download Crosswalk windows binary to apptools-windows-tests/tools from https://download.01.org/crosswalk/releases/crosswalk/windows/

## 7. Run Test Suit With testkit-lite

### 1. Android Platform
        ```
          $ cd [testprefix-path]/opt/apptools-android-tests/
          $ testkit-lite -f [testprefix-path]/opt/apptools-android-tests/tests.xml -A -o [testprefix-path]/opt/apptools-android-tests/result.xml --comm androidmobile --deviceid=Medfield3C6DFF2E --testprefix=[testprefix-path]
        ```
### 1. iOS Platform
        ```
          $ cd [testprefix-path]/opt/apptools-ios-tests/
          $ testkit-lite -f [testprefix-path]/opt/apptools-ios-tests/tests.xml -A -o [testprefix-path]/opt/apptools-ios-tests/result.xml --comm localhost --testprefix=[testprefix-path] --non-active
        ```
### 1. Linux Platform
        ```
          $ cd [testprefix-path]/opt/apptools-linux-tests/
          $ testkit-lite -f $PWD/tests.xml -A --comm deepin --testprefix $PWD/../../ -o $PWD/result.xml
        ```
### 1. Windows Platform
        ```
          $ cd [testprefix-path]/opt/apptools-windows-tests/
          $ testkit-lite -f [testprefix-path]/opt/apptools-windows-tests/tests.xml -A -o [testprefix-path]/opt/apptools-windows-tests/result.xml --comm localhost --testprefix=[testprefix-path] --non-active
        ```

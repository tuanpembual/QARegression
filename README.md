# QARegression
Automation Testing for Mobile apps using Calabash and Apium

### Requerments
* Install JDK
* Install VirtualBox
* Install GenyMotion (Nexus 5, Androit 5.1.0 API 22, Install gapss)
* Download Android SDK and Set sdk location as ANDROID_HOME

### How do I get set up? ###
#### Setup Env ####
```
#!bash
keytool -genkey -v -keystore ~/.android/debug.keystore -alias debugkey -storepass android -keypass android -keyalg RSA -keysize 2048 -validity 10000 -dname "CN=Android Debug,O=Android,C=US"
```

```
#!bash
export ANDROID_HOME=~/Library/Android/sdk
```

```
#!bash
git clone git@github.com:tuanpembual/QARegression.git
```

#### Run Testing ####
```
#!bash
cd QARegression
bundle install
calabash-android setup app/staging.apk # Or using proper apk path
```

* keystore location : ~/.android/debug.keystore
* password : android
* alias : debugkey

```
#!bash
calabash-android resign app/staging.apk # Or using proper apk path
calabash-android run app/gojek-staging.apk # Or using proper apk path
--format html --out reports.html # for html output
```

### How to get Step Command
https://github.com/calabash/calabash-android/blob/master/ruby-gem/lib/calabash-android/canned_steps.md

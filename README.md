# QARegression
Automation Testing for Mobile apps using Calabash and Appium

### Requerments
* Install JDK
* Install VirtualBox
* Install GenyMotion (Nexus 5, Android 5.1.0 API 22, Install gapss)
* Download Android SDK and Set sdk location as ANDROID_HOME

### How do I get set up? ###
#### Setup Env ####
```
keytool -genkey -v -keystore ~/.android/debug.keystore -alias debugkey -storepass android -keypass android -keyalg RSA -keysize 2048 -validity 10000 -dname "CN=Android Debug,O=Android,C=US"
```

```
git clone git@github.com:tuanpembual/QARegression.git
```

#### Run Testing ####
Only run for first time.
```
cd QARegression
bundle install
bundle exec calabash-android setup app/staging.apk # Or using proper apk path
```

* keystore location : ~/.android/debug.keystore
* password : android
* alias : debugkey

```
bundle exec calabash-android resign app/staging.apk # Or using proper apk path
bundle exec calabash-android run app/staging.apk # Or using proper apk path
--format html --out reports.html # for html output
```

### How to get Step Command
https://github.com/calabash/calabash-android/blob/master/ruby-gem/lib/calabash-android/canned_steps.md

### Done ###
* Set profile to reduce run command | -p profile, add config/cucumber.yml file
* Set multi scenario, set by tag
add option ```-t @nametag```
* Set specific scenario by add tag too
add option ```-t @namescenario```
* Add backgrout to run login scenario

### To do ###
* Set login from config | fail
* Run multi device, deference scenario, avoid backdoor api

How to install realm for Mac
High Sierra 10.13.3
XCode 9.4
Node 8.11.1
react-native-cli@2.0.1
react-native@57.8
android studio 3.6.3
Android Emulator: Pixel API 28 : Android Pie 9
Also Tested: Genymotion 3.1.0 : Samsung Galaxy S10 Android 10
Iphone Emulator 11.3

Xcode Build location Unique: xcode -> Preference->Locations -> Advanced


Install nvm
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.35.2/install.sh | bash

Add the following to .bash_profile:

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

install Node 8.11.1 using nvm:
nvm install 8.11.1

To uninstall unnecessary version of node:

nvm deactivate
nvm uninstall 7.10.0

nvm use v8.11.1

THIS VERSION DOES NOT REQUIRE yarn. So I deleted yarn cause later version was making trouble for yarn,
You may try with yarn if it is already installed but for this build not required
brew uninstall yarn
brew install watchman



npm install -g react-native-cli@2.0.1
add react-native to .bash_profile:
export PATH="/Users/hasan/.nvm/versions/node/v8.11.1/bin/:$PATH"


To create React Native project MAKE SURE use the above configuration first:

*if you have used oracle java over version 8, uninstall that with the following:
sudo rm -rf /Library/Java/JavaVirtualMachines/jdk-11.jdk


Install openJDK8:
brew tap AdoptOpenJDK/openjdk
brew cask install adoptopenjdk8

ALWAYS USE VERSION NUMBER. REACT NATIVE DOESN'T FIX ANYTHING MAGICALLY
[react-native init RealmProject --version 0.57.8]

Change gradle-wrapper.properties 4.4 to 4.9:
distributionUrl=https\://services.gradle.org/distributions/gradle-4.9-all.zip

android>build.gradle plugin version change to 3.2.1

Install android sdk: 
http://reactnative.dev/docs/0.57/getting-started

Add the following to .bash_profile:

export ANDROID_HOME=/Users/hasan/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools

Run Android Emulator then :

npm install
react-native run-android
react-native run-ios

if you had any error MAKE SURE you delete all caches:
watchman watch-del-all && rm -rf $TMPDIR/react-* && rm -rf node_modules/ && npm cache verify && npm install && npm start -- --reset-cache

[DO NOT UPDATE REALM TO LATEST VERSION]

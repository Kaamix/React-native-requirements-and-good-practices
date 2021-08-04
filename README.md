# React Native Project Requirements & Good practices

## Setup

### Android

1. Download the [JDK](https://www.oracle.com/fr/java/technologies/javase-downloads.html)

2. Download the [Android Debug Bridge](https://dl.google.com/android/repository/platform-tools-latest-windows.zip) to allow developing on your phone.
Then verify the environment variable is correctly setup. (C:\Users\USERNAME\AppData\Local\Android\Sdk\platform-tools\adb)
3. Download [Gradle](https://gradle.org/releases/)

In android folder :
> Add local.properties defining SDK dir like below : 

*Windows*
- `sdk.dir = C:\\Users\\USERNAME\\AppData\\Local\\Android\\sdk`


*Mac*
- `sdk.dir = /Users/USERNAME/Library/Android/sdk`

*Linux*
- `sdk.dir = /home/USERNAME/Android/Sdk`

## Structure

Just a structure example

```
/android
/ios
/src
    /components
        /ComponentFolder
            +index.js
            +partOfComponent.js
    /helpers
        +helperFunction.js
    /api
        /actionType
            +getSomething.js
    /resources
        /images
            +index.js
        /fonts
            +index.js
        /colors
            +index.js
    /redux
        reducers/
            +exampleReducer.js
```


## Components

> **Use hooks.**

> A good component *should'nt exceed* **100 lines**.

> Avoid to the max using stores like redux, always search to use **parent/child props** and **local state**

## Assets & Stores

For the in-app assets, best are Svg's

**[Link](https://easyappicon.com/)** to generate icons

## Deployment

## Android

Change the number version in *android/app/build.gradle > android > defaultConfig*

**In folder _/android_ :**

Clean the build folder
```bash
gradlew clean
```

**At root / :**

Launch the server
```bash
npm start
```

**In folder _/android_ :**

Generate an apk
```bash
gradlew assembleRelease
```
Generate an aab
```bash
gradlew bundleRelease
```

You can find the generated package here : `android/app/build/outputs/bundle`
## iOS
On XCode

Change the **version** and the **build number** in *Targets > General* 

> Product > Clean Build Folder

> Product > Archive
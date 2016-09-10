Auto generate keystore if not exists.

## Installation

Basically, add 2 lines only.

* Add keytool plugin

```gradle
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'org.figurate:gradle-keytool-plugin:1.0.0'
    }
}
```

* Download [keytool.gradle](https://github.com/yongjhih/gradle-android-keystore-boilerplate/raw/master/app/keytool.gradle) into your module.

* Add the following line into `build.gradle` above `android { ... }`:

```gradle
apply from: 'keytool.gradle'
```

That's it.

## Test

Enable regular signing and release build:

```gradle
android {
    signingConfigs {
        release {
            storeFile file("${projectDir}/.release-keystore")
            storePassword 'changeit'
            keyAlias  "${defaultConfig.applicationId}-release"
            keyPassword 'changeit'
        }
    }
    buildTypes {
        release {
            signingConfig signingConfigs.release
        }
    }
}
```

```sh
./gradlew assembleRelease
```

## Configuration

dname:

```gradle
android {
    signingConfigs {
        release {
            genkey.options.dname = "CN=Release,OU=Android,O=GitHub,L=Taipei,ST=Taiwan,C=TW"
        }
    }
}
```

## Features

* Support auto generate multi-keystore

## TODO

* Support auto-gen multi-keyAlias in the same keystore

## Ref.

* http://stackoverflow.com/questions/29060064/sun-security-x509-certandkeygen-and-sun-security-pkcs-pkcs10-missing-in-jdk8

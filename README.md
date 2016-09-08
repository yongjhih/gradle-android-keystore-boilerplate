Auto generate keystore if not exists.

## Usage

Basically, add 2 lines only.

* Add keytool plugin

```
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'org.figurate:gradle-keytool-plugin:1.0.0'
    }
}
```

* Download `keytool.gradle` into your module: [raw/master/app/keytool.gradle](raw/master/app/keytool.gradle)


* Append the following line into `build.gradle`:

```
apply from: 'keytool.gradle'
```

That's it.

## Features

* Support auto generate multi-keystore

## TODO

* Support auto-gen multi-keyAlias in the same keystore

## Ref.

* http://stackoverflow.com/questions/29060064/sun-security-x509-certandkeygen-and-sun-security-pkcs-pkcs10-missing-in-jdk8

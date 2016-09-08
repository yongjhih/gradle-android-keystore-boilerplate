modules:

* app (kotlin + java)
* lib (kotlin + java)
* eclipse-app (kotlin + java)
* eclipse-app2 (kotlin + java)
* android-java-app (java) for reference
* android-java-lib (java) for reference

## Usage

Setup Pure Android Application:

```sh
git clone https://github.com/yongjhih/gradle-android-kotlin-boilerplate
cd gradle-android-kotlin-boilerplate
rm -fr lib eclipse-app eclipse-app2 android-java-app android-java-lib
echo "include ':app'" > settings.gradle
```

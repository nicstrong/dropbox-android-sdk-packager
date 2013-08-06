# Dropbox Android SDK Packager

Packages the Dropbox sync SDK so it can be used from a Maven build.

## How to Use

Download the latest Dropbox SDK from [here](https://www.dropbox.com/developers/datastore/sdks/android). Currently the version is 2.0.0-b4.

Update the version information in pom.xml and AndroidManifest.xml with the correct version information.

Unpack the zip file and place pom.xml and AndroidManifest.xml from the git repo into the root of the unpacked directory.

Install the apklib (contains the native shared objects) to your local repo with:
```xml
mvn clean install
```

Install the jar dependency to the local repo with:
```xml
mvn install:install-file -Dfile=libs/dropbox-sync-sdk-android.jar -DgroupId=com.dropbox -DartifactId=dropbox-android-sync-sdk -Dversion=2.0.0-b4 -Dpackaging=jar
```

To use the dropbox SDK from your maven project add the following dependencies:
```xml
<dependency>
    <groupId>com.dropbox</groupId>
    <artifactId>dropbox-android-sync-sdk</artifactId>
    <version>2.0.0-b4</version>
    <type>apklib</type>
</dependency>
<dependency>
    <groupId>com.dropbox</groupId>
    <artifactId>dropbox-android-sync-sdk</artifactId>
    <version>2.0.0-b4</version>
    <type>jar</type>
</dependency>
```
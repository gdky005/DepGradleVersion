# DepGradleVersion
依赖的第三方开源库的 gradle 版本。

## 在线版本
```
https://www.zkteam.cc/android/gradle/versions.gradle
```

## 使用方式

1. 引入 versions.gradle

```
buildscript {
    //apply from: 'versions.gradle'
    apply from: 'https://www.zkteam.cc/android/gradle/versions.gradle' //推荐使用在线版本，更新及时，还能随时查看。
    ...
}
```

2. 导入常用的 maven 库，内部包含 google()，jcenter()，mavenCentral()，jitpack.io，maven.aliyun.com

项目根目录下的：gradle.build
```
buildscript {
    ...
    addRepos(repositories)
    ...
}
```

```
allprojects {
    addRepos(repositories)
}
```

只要这个一个即可

3. 引入构建版本

```
android {

    compileSdkVersion build_versions.target_sdk
    buildToolsVersion build_versions.build_tools
    
    defaultConfig {
        minSdkVersion build_versions.min_sdk
        targetSdkVersion build_versions.target_sdk
    }
}
```

4. 引用依赖

然后就可以使用库中的所有资源，如果要导入相关库，请直接使用根目录下的 version.gradle，使用方式如下：

```
dependencies {

    // okhttp
    implementation deps.okhttp
    implementation deps.okhttp_interceptor
    
}
```



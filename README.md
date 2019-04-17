# DepGradleVersion
优秀的第三方开源库的 gradle 版本集合，它将众多开源项目整理后，把优质的开源项目的依赖整理出来，方便大家快速浏览和了解相关功能，以满足自己的需求。提升开发效率，以及闭坑。

## 在线版本
```
https://www.zkteam.cc/android/gradle/versions.gradle
```

## 使用方式

1. 引入 versions.gradle

```
buildscript {
    //apply from: 'versions.gradle' //可以把工程中的 versions.gradle 文件放入项目根目录，然后直接使用下面的。
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



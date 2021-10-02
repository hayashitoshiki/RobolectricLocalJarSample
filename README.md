# RobolectricLocalJarSample

## 概要
Robolectricオフライン設定用スクリプトメモ

## 使用方法 
1.  プロジェクト直下に[robolectric.gradle](https://github.com/hayashitoshiki/RobolectricLocalJarSample/blob/master/robolectric.gradle)を追加

2.  build.gradleに下記を記載
```gradle:build.gradle  
    apply from: '../robolectric.gradle'

    android {
        testOptions {
            unitTests {
                includeAndroidResources = true
            }
        }
    }
```  
3.  [robolectric.gradle](https://github.com/hayashitoshiki/RobolectricLocalJarSample/blob/master/robolectric.gradle)のconfigurationsからテストで使用しないAPIレベルの変数をコメントアウトしてテスト実施。  
または下記のコマンドを実施
```
/gradlew downloadRobolectricDependencies 
```  

#### ※ AndroidStudioのプロキシ設定等でAPIレベルにに対応するJarをインストールできない場合  
下記から[robolectric.gradle](https://github.com/hayashitoshiki/RobolectricLocalJarSample/blob/master/robolectric.gradle)に記載されている使用したいAPIレベルに該当するJarをダウンロードして、/.robolectric-dependenciesに配置（/.robolectric-dependenciesが存在しない場合はプロジェクト直下に.robolectric-dependenciesを作成）

https://search.maven.org/artifact/org.robolectric/android-all-instrumented/8.1.0-robolectric-4611349-i1/jar

## 参考URL
https://blog.keithyokoma.dev/entry/2018/04/03/182446  
https://star-zero.medium.com/robolectric%E3%81%AEoffline%E8%A8%AD%E5%AE%9A-1d8662d5cfaf

## Common Libraries
Common libraries and coordinates that you may use everyday.

# Retrofit with its family
module level
```
implementation "com.squareup.retrofit2:retrofit:$retrofitVersion"
implementation "com.squareup.retrofit2:converter-gson:$retrofitVersion"
implementation "com.squareup.okhttp3:logging-interceptor:4.9.1"
implementation "com.squareup.retrofit2:converter-scalars:$retrofitVersion"
```
# Dagger
applying plugin in root level
```
id 'com.google.dagger.hilt.android' version '2.44' apply false
```
inside module level plugins
```
id 'kotlin-kapt'
id 'com.google.dagger.hilt.android'
```
module level dependency 
```
implementation "com.google.dagger:hilt-android:2.44"
kapt "com.google.dagger:hilt-compiler:2.44"
```
# Dagger for compose with nav dependency
module level dependency
```
implementation "com.google.dagger:hilt-android:2.44"
implementation 'androidx.hilt:hilt-navigation-compose:1.1.0-alpha01'
kapt "com.google.dagger:hilt-compiler:2.44"
kapt "com.google.dagger:hilt-android-compiler:2.41"
```
# Room with dagger
module level dependency
```
//room
def room_version = "2.5.1"
implementation "androidx.room:room-runtime:$room_version"
implementation "androidx.room:room-ktx:$room_version"
kapt "androidx.room:room-compiler:$room_version"
```
module level config for migrations inside default config
```
    javaCompileOptions {
        annotationProcessorOptions {
            arguments += [
                "room.schemaLocation":"$projectDir/schemas".toString(),
                "room.incremental":"true",
                "room.expandProjection":"true"
            ]
        }
    }
```
or if you are using kapt
```
        kapt {
            arguments {
                arg("room.schemaLocation", "$projectDir/schemas"),
                arg("room.incremental", 
            }
        }
```
# material design
module dependecy
```
implementation 'com.google.android.material:material:1.3.0'
```
# image loading and glide
module dependecy
```
implementation "io.coil-kt:coil:$coilVersion"
implementation 'com.github.bumptech.glide:glide:4.15.1'
```
# Pagination with Paging3
module dependency 
```
def paging_version = "3.1.1"

implementation "androidx.paging:paging-runtime:$paging_version"

// alternatively - without Android dependencies for tests
testImplementation "androidx.paging:paging-common:$paging_version"

// optional - RxJava2 support
implementation "androidx.paging:paging-rxjava2:$paging_version"

// optional - RxJava3 support
implementation "androidx.paging:paging-rxjava3:$paging_version"

// optional - Guava ListenableFuture support
implementation "androidx.paging:paging-guava:$paging_version"

// optional - Jetpack Compose integration
implementation "androidx.paging:paging-compose:1.0.0-alpha18"
```

# workmanager (with hilt)
module dependency
```
//work manager
implementation 'androidx.work:work-runtime-ktx:2.8.1'
implementation 'androidx.hilt:hilt-work:1.0.0'
```
# Navigation
```
//navigation
implementation("androidx.navigation:navigation-fragment-ktx:$nav_version")
implementation("androidx.navigation:navigation-ui-ktx:$nav_version")
```

# timber
```
//timber
implementation("com.jakewharton.timber:timber:5.0.1")
```

add more if you have one.

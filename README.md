# FirebaseMessaging
A simple android firebase notification example 

### Notification : 
<img src="https://github.com/datanapps/FirebaseMessaging/blob/master/screens/fcm_1.png" height="600" width="360">


### Download APK : 

https://github.com/datanapps/GoogleExoPlayerSample/blob/master/screens/app-debug.apk



#### Android Dependency :


            Project Lable : 

            // Top-level build file where you can add configuration options common to all sub-projects/modules.

            buildscript {
                repositories {
                    google()
                    jcenter()

                }
             dependencies {
                  classpath 'com.android.tools.build:gradle:3.5.0'
                  classpath 'com.google.gms:google-services:4.3.2'
                    // NOTE: Do not place your application dependencies here; they belong
                    // in the individual module build.gradle files
               }
            }

            allprojects {
                repositories {
                    google()
                    jcenter()

                }
            }

task clean(type: Delete) {
    delete rootProject.buildDir
}



Application Dependency : 

    // add firebase message
   **implementation 'com.google.firebase:firebase-messaging:20.0.0'**

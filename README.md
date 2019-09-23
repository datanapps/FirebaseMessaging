# FirebaseMessaging
A simple android firebase notification example 

### Notification : 
<img src="https://github.com/datanapps/FirebaseMessaging/blob/master/screens/fcm_1.png" height="600" width="330">


### Download APK : 

https://github.com/datanapps/GoogleExoPlayerSample/blob/master/screens/app-debug.apk


#### Setup project on firebase :

https://console.firebase.google.com


#### Android Dependency :

            Project Lable : 
            // Top-level build file where you can add configuration options common to all sub-projects/modules.
            buildscript {
                repositories {
                    google()
                }
             dependencies {
                  classpath 'com.google.gms:google-services:4.3.2'
               }
            }
            allprojects {
                repositories {
                    google()
                }
            }
            task clean(type: Delete) {
                delete rootProject.buildDir
            }


#### Application Dependency : 

    // add firebase message
   **implementation 'com.google.firebase:firebase-messaging:20.0.0'**
   
#### Manifest File : 


             <service
                        android:name=".fcm.MyFirebaseMessagingService"
                        android:exported="false">
                        <intent-filter>
                            <action android:name="com.google.firebase.MESSAGING_EVENT" />
                        </intent-filter>
                    </service>


#### Messaging Service : 

     public class MyFirebaseMessagingService  extends FirebaseMessagingService {

    @Override
    public void onMessageReceived(RemoteMessage remoteMessage) {
        super.onMessageReceived(remoteMessage);
        Log.d("FCM", remoteMessage.toString());
    }
    }
    
    
#### Create Token :

    FirebaseInstanceId.getInstance().getInstanceId()
                .addOnCompleteListener(new OnCompleteListener<InstanceIdResult>() {
                    @Override
                    public void onComplete(@NonNull Task<InstanceIdResult> task) {
                        if (!task.isSuccessful()) {
                            Log.w(TAG, "getInstanceId failed", task.getException());
                            return;
                        }

                        // Get new Instance ID token
                        String token = task.getResult().getToken();

                        // Log and toast

                        Log.d(TAG, token);
                        Toast.makeText(MainActivity.this, token, Toast.LENGTH_SHORT).show();
                    }
                });
                
                
       
#### Read More :

https://firebase.google.com/docs/cloud-messaging/android/client


#### Firebase Console :

https://console.firebase.google.com

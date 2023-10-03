
# Ex.No:6 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by:
Registeration Number :
*/
Android Manifest File:
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android" 
xmlns:tools="http://schemas.android.com/tools">
<uses-permission android:name="android.permission.SEND_SMS" />
<uses-permission android:name="android.permission.READ_PHONE_STATE" /> 
<application
android:allowBackup="true"
android:dataExtractionRules="@xml/data_extraction_rules"
android:fullBackupContent="@xml/backup_rules"
android:icon="@mipmap/ic_launcher"
android:label="@string/app_name"
android:supportsRtl="true"
android:theme="@style/Theme.Smsintent" 
tools:targetApi="31">
Activity_xml File:
<activity
android:name=".MainActivity" 
android:exported="true">
<intent-filter>
<action android:name="android.intent.action.MAIN" />
<category android:name="android.intent.category.LAUNCHER" /> 
</intent-filter>
</activity> 
</application>
</manifest>
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools" 
android:layout_width="match_parent"
android:layout_height="match_parent" 
tools:context=".MainActivity">
<EditText
android:id="@+id/number"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginTop="192dp"
android:ems="10"
android:inputType="textPersonName"
android:text=""
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintHorizontal_bias="0.497"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent" />
<EditText
MainActivity.java File:
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginStart="88dp"
android:layout_marginTop="140dp"
android:ems="10"
android:inputType="textPersonName"
android:text=""
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toBottomOf="@+id/number" />
<Button
android:id="@+id/send"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginTop="56dp"
android:backgroundTint="#4CAF50"
android:text="SEND"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintHorizontal_bias="0.498"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toBottomOf="@+id/text" />
<TextView
android:id="@+id/textView"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginStart="16dp"
android:layout_marginBottom="23dp"
android:text="Enter Number:"
android:textColor="#F44336"
android:textSize="36dp"
app:layout_constraintBottom_toTopOf="@+id/number" 
app:layout_constraintStart_toStartOf="parent" />
<TextView
android:id="@+id/textView2"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_marginStart="16dp"
android:layout_marginTop="46dp"
android:text="Enter Message:"
android:textColor="#673AB7"
android:textSize="36dp"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toBottomOf="@+id/number" /> 
</androidx.constraintlayout.widget.ConstraintLayout>
package com.example.smsintent;
import androidx.appcompat.app.AppCompatActivity;
import android.Manifest;
import android.annotation.SuppressLint;
import android.content.pm.PackageManager;
import android.os.Build;
import android.os.Bundle;
import android.telephony.SmsManager;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity { 
private EditText number,message;
private Button send;
@SuppressLint("MissingInflatedId") 
@Override
protected void onCreate(Bundle savedInstanceState) { 
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main); 
number = findViewById(R.id.number);
message = findViewById(R.id.text); 
send = findViewById(R.id.send);
send.setOnClickListener(new View.OnClickListener() { 
@Override
public void onClick(View view) {
if (Build.VERSION.SDK_INT>=Build.VERSION_CODES.M){
if (checkSelfPermission(Manifest.permission.SEND_SMS) ==
PackageManager.PERMISSION_GRANTED){
sendSMS(); 
}else {
requestPermissions(new String[]
{Manifest.permission.SEND_SMS},1);
} 
}
} 
});
}
private void sendSMS(){
String phoneNo = number.getText().toString().trim(); 
String SMS = message.getText().toString().trim();
try{
SmsManager smsManager = SmsManager.getDefault(); 
smsManager.sendTextMessage(phoneNo,null,SMS,null,null);
Toast.makeText(this,"Message is sent",Toast.LENGTH_SHORT).show(); 
} catch (Exception e){
e.printStackTrace();
}
} 
}
Toast.makeText(this,"Failed to send message",Toast.LENGTH_SHORT).show();
```

## OUTPUT
![267216153-d7b6bdac-35ad-49ef-8c03-3806944a206a 1](https://github.com/Lathishkum/exp6/assets/144109092/85af226a-7953-46bf-add6-5659e2938310)
![267216217-01d497fc-4155-4a82-be23-a5519a0a3d15 1](https://github.com/Lathishkum/exp6/assets/144109092/3c0d9413-4b6c-40de-90de-f60a5a75314f)

![267217049-35e64b32-34ad-4275-bca3-ecdfacd6728a 1](https://github.com/Lathishkum/exp6/assets/144109092/d80e8323-b19f-4fd5-8c0c-ea7c0e28be59)



## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.

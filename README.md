# Ex.No: 2(b) To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.

## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1. **Start the project:** Create a new Android project with two Empty Activities (`MainActivity` and `MainActivity2`).

2. **Design the First Screen:** In `activity_main.xml`, add an `EditText` to receive the number input and a `Button` to trigger the calculation.

3. **Design the Second Screen:** In `activity_main2.xml`, add a `TextView` to display the calculated factorial result.

4. **Get Input (MainActivity):** Inside `MainActivity.java`, set an `OnClickListener` on the button to retrieve the entered number from the `EditText`.

5. **Pass Data using Explicit Intent:** Create an `Intent` targeting `MainActivity2.class`. Attach the entered number to the intent using `intent.putExtra()`, and start the activity using `startActivity(intent)`.

6. **Receive Data (MainActivity2):** In `MainActivity2.java`, use `getIntent().getStringExtra()` (or `getIntExtra()`) to retrieve the passed number.

7. **Calculate Factorial:** Write a loop or recursive function to compute the factorial of the received number.

8. **Display Result:** Update the `TextView` in the second activity to show the computed factorial value.

9. **Stop:** Run and test the application.

## PROGRAM:

```
Program to print the text “Explicit Intent”.
Developed by: Prideesh M
Registeration Number: 212223040154
```

### MainActivity.java

```java
package com.example.explicitintent;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        Button button = findViewById(R.id.button);
        button.setOnClickListener(view -> {
            Intent i = new Intent(this, MainActivity2.class);
            startActivity(i);
        });
    }
}
```

### MainActivity2.java

```java
package com.example.explicitintent;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity2 extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        Button button = findViewById(R.id.button);
        button.setOnClickListener(view -> {
            Intent i = new Intent(this, MainActivity.class);
            startActivity(i);
        });
    }
}
```

### activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="@font/poppins"
        android:text="Explicit Intent"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="@font/poppins"
        android:text="Click"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

### activity_main2.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="@font/poppins"
        android:text="This is Second Activity"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="@font/poppins"
        android:text="Home"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

### AndroidManifest.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.ExplicitIntent">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

        <activity android:name=".MainActivity2" />

        <meta-data
            android:name="preloaded_fonts"
            android:resource="@array/preloaded_fonts" />
    </application>

</manifest>
```

## OUTPUT

### Home Screen : 
<img width="1920" height="1200" alt="Screenshot (92)" src="https://github.com/user-attachments/assets/a57da73b-a3cb-4ec3-8886-0e7cf879663b" />

### Next Screen:
<img width="1920" height="1200" alt="Screenshot (93)" src="https://github.com/user-attachments/assets/8614fdaf-4e8d-4c5b-a30b-ae86a8781864" />

## RESULT

Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.

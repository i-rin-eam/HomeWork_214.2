<p align="center">
<h1 align='center'>Season 2 / Section 1 / HomeWork 214.2 Solution</h1>
<h3 align='center'>
   Visit my youtube channel <a href="https://www.youtube.com/@CodeCraftArena">CodeCraft Arena</a>
</h3>
</p>

## Step 1: Here is `activity_main.xml` code.
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textViewDescription"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginBottom="16dp"
        android:text="Enter a year to check if it's a leap year."
        android:textSize="16sp" />

    <EditText
        android:id="@+id/editTextYear"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Year"
        android:inputType="number" />

    <Button
        android:id="@+id/buttonCheck"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="16dp"
        android:text="Check Leap Year" />

    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="16dp" />

</LinearLayout>
```
## Step 2: Here is `MainActivity.java` code.
```java
package com.myeamin.homework_2142;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

/**
 * MainActivity class defines the behavior for an app that checks if a year
 * entered by the user is a leap year.
 */
public class MainActivity extends AppCompatActivity {

    // UI components
    EditText editTextYear;
    Button buttonCheck;
    TextView textViewResult;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize the UI components
        editTextYear = findViewById(R.id.editTextYear);
        buttonCheck = findViewById(R.id.buttonCheck);
        textViewResult = findViewById(R.id.textViewResult);

        // Set a click listener on the check button
        buttonCheck.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Retrieve the user input as a trimmed string
                String yearString = editTextYear.getText().toString().trim();

                // Check if the input string is empty
                if (yearString.isEmpty()) {
                    // If no input provided, display a request for input
                    textViewResult.setText("Please enter a year");
                } else {
                    // Parse the input string to an integer
                    int year = Integer.parseInt(yearString);

                    // Determine if the year is a leap year
                    if (year % 400 == 0) {
                        // If year is divisible by 400, it's a leap year
                        textViewResult.setText(year + " is a Leap Year");
                    } else if (year % 4 == 0 && year % 100 != 0) {
                        // If year is divisible by 4 and not divisible by 100, it's a leap year
                        textViewResult.setText(year + " is a Leap Year");
                    } else {
                        // Otherwise, it's not a leap year
                        textViewResult.setText(year + " is not a Leap Year");
                    }
                }
            }
        });

    }
}
```
## Authors
**MD YEAMIN** - *Android Software Developer* - <a href="https://github.com/i-rin-eam">MD YEAMIN</a> - *Learn with Ease*
<h1 align="center">Thank You ❤️</h1>

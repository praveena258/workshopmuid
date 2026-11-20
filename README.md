# workshopmuid

## ADDITION OF TWO NUMBERS

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Start the application.

Initialize the user interface.

Get the first number from the user.

Get the second number from the user.

Click the ADD button.

Read both input values.

Convert the input values into numeric data.

Calculate the sum using sum = num1 + num2.

Display the sum in the Result text box.

Stop the application.

## PROGRAM

activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="24dp"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/num1"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Enter First Number"
        android:inputType="numberDecimal|numberSigned"
        android:layout_marginBottom="16dp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toTopOf="@id/num2"
        app:layout_constraintVertical_chainStyle="packed"/>

    <EditText
        android:id="@+id/num2"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Enter Second Number"
        android:inputType="numberDecimal|numberSigned"
        android:layout_marginBottom="20dp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@id/num1"
        app:layout_constraintBottom_toTopOf="@id/addBtn"/>

    <Button
        android:id="@+id/addBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="ADD"
        android:layout_marginBottom="20dp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@id/num2"
        app:layout_constraintBottom_toTopOf="@id/result"/>

    <EditText
        android:id="@+id/result"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Result"
        android:focusable="false"
        android:clickable="false"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@id/addBtn"
        app:layout_constraintBottom_toBottomOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>

```
mainactivtity.java
```
package com.example.workshop;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {

    private EditText num1, num2, result;
    private Button addBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        result = findViewById(R.id.result);
        addBtn = findViewById(R.id.addBtn);

        addBtn.setOnClickListener(v -> {
            String s1 = num1.getText().toString();
            String s2 = num2.getText().toString();

            if (s1.isEmpty() || s2.isEmpty()) {
                Toast.makeText(this,
                        "Enter both numbers",
                        Toast.LENGTH_SHORT).show();
                return;
            }

            double a = Double.parseDouble(s1);
            double b = Double.parseDouble(s2);

            double sum = a + b;

            result.setText(String.valueOf(sum));
        });
    }
}

```

## OUTPUT
<img width="1917" height="1126" alt="image" src="https://github.com/user-attachments/assets/e696849c-725d-4d20-95f6-b2a511b728ee" />
<img width="1917" height="1092" alt="image" src="https://github.com/user-attachments/assets/fc82aa93-6136-4dbc-9570-dd6c1c6671f0" />

## RESULT
Thus, the Android application for addition of two numbers was successfully developed using Android Studio. The application accepts two numbers from the user, calculates their sum when the ADD button is clicked, and displays the result in the Result text box.

# kuliah-pakAli

## 1. Konfigurasi String & Color
Buka file `res/values/strings.xml`.

<img width="393" height="977" alt="image" src="https://github.com/user-attachments/assets/3dc9e5a8-fcf1-4099-9b2c-de6509e87a2d" />


 Masukkan Kode:
```xml
<resources>
 <string name="app_name">kuliah</string>
    <string name="awal">Ini adalah tampilan awal</string>
    <string name="Textprima">Bilangan prima ke %1$d adalah %2$d</string>
    </resources>
```

Buka colors.xml (filenya dibawah strings.xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="purple_200">#FFBB86FC</color>
    <color name="purple_500">#FF6200EE</color>
    <color name="purple_700">#FF3700B3</color>
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name= "hijaubaru">#8BC34A</color>
</resources>
```


# 2. Desain Loginnya (activity_main.xml)

## 1. Halaman Login
`res/layout/activity_main.xml/`

<img width="378" height="311" alt="image" src="https://github.com/user-attachments/assets/a3733e8d-65a5-4cd3-9fc8-9737d44d52a3" />

di kode baris ke 8 ganti sesuai sama nama file kotlin pertama kelen, contoh punyaku MainActivity(huruf besar dan kecil harus sama)

<img width="355" height="130" alt="image" src="https://github.com/user-attachments/assets/4d34e7e4-9e0a-494d-97b3-23d8fba44fbc" />

Masukkan Kode:

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"> 

    <Button
        android:id="@+id/btn1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintStart_toStartOf="parent"
        android:text="Proses"
        android:textSize="20dp"
        app:layout_constraintBottom_toBottomOf="parent"
        android:textColor="@color/black"
        android:backgroundTint="@color/hijaubaru"/>

    <TextView
        android:id="@+id/txt1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="25dp"
        android:textColor="@color/black"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/hapus"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:text="Reset"
        android:textSize="20sp"
        android:backgroundTint="@color/hijaubaru"
        android:textColor="@color/black"/>


    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/tl_username"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginBottom="20dp"
        app:layout_constraintBottom_toTopOf="@+id/tl_password">

        <EditText
            android:id="@+id/username"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukkan Username Anda"
            android:inputType="textPersonName" />

    </com.google.android.material.textfield.TextInputLayout>

    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/tl_password"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toTopOf="@id/btn1"
        app:counterEnabled="true"
        app:counterMaxLength="10"
        app:passwordToggleEnabled="true">

        <EditText
            android:id="@+id/password"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukkan Password"
            android:inputType="textPassword" />
    </com.google.android.material.textfield.TextInputLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```

## 2. Halaman Hasil (activity_second.xml)
`res/layout/activity_second.xml/`

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".second">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent">

        <TextView
            android:id="@+id/tv_username"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="username ="
            android:textSize="20sp" />

        <TextView
            android:id="@+id/tv_password"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="10dp"
            android:text="password ="
            android:textSize="20sp" />

        <TextView
            android:id="@+id/hasil"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="10dp"
            android:text="Hasil akan muncul di sini"
            android:textSize="20sp" />

    </LinearLayout>

</androidx.constraintlayout.widget.ConstraintLayout>

```
# 3. Kode Kotlin

## 1. MainACtivity.kt
buka file `app/kotlin+java/com.example.kuliah`.

<img width="395" height="236" alt="image" src="https://github.com/user-attachments/assets/f338f33b-2c69-4d52-b4e1-7bff05588536" />

-

#### Note: ganti pake nama usernameStr nya terserah, di baris ke 62
Masukkan kode ke MainActivity.kt:

```kt
package com.example.kuliah

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import android.widget.Toast
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat
import kotlin.math.sqrt

fun isPrime(num: Int): Boolean {
    if (num < 2) return false
    val limit = sqrt(num.toDouble()).toInt()
    for (i in 2..limit) {
        if (num % i == 0) return false
    }
    return true
}

fun prima(n: Int): Int {
    var hit = 0
    var x = 1
    while (hit < n) {
        x++
        if (isPrime(x)) {
            hit++
        }
    }
    return x
}

var angka: Int = 0
fun hitung() {
    angka++
}

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }

        val tombol: Button = findViewById(R.id.btn1)
        val tampil: TextView = findViewById(R.id.txt1)
        val reset: Button = findViewById(R.id.hapus)
        val un: EditText = findViewById(R.id.username)
        val pw: EditText = findViewById(R.id.password)

        tombol.setOnClickListener {
            val usernameStr = un.text.toString()
            val passwordStr = pw.text.toString()

            if (usernameStr == "rafli" && passwordStr == "12345") {
                Toast.makeText(applicationContext, "Login Berhasil", Toast.LENGTH_SHORT).show()
                val intent = Intent(this, second::class.java)
                intent.putExtra("EXTRA_USERNAME", usernameStr)
                intent.putExtra("EXTRA_PASSWORD", passwordStr)
                startActivity(intent)
            } else {
                Toast.makeText(applicationContext, "Login Gagal", Toast.LENGTH_SHORT).show()
            }
        }

        reset.setOnClickListener {
            angka = 0
            tampil.text = ""
        }
    }
}
```

## 2. Second.kt

Masukkan kode ke second.kt
```kt
package com.example.kuliah

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat
import android.widget.TextView
import android.widget.Toast

class second : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_second)
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }

        val tvUsername : TextView = findViewById(R.id.tv_username)
        val tvPassword : TextView = findViewById(R.id.tv_password)
        val hasil : TextView = findViewById(R.id.hasil)

        if(intent.hasExtra("EXTRA_USERNAME") && intent.hasExtra("EXTRA_PASSWORD")){
            val usernameStr = intent.getStringExtra("EXTRA_USERNAME")
            val passwordStr = intent.getStringExtra("EXTRA_PASSWORD")

            tvUsername.text = "Username = $usernameStr"
            tvPassword.text = "Password = $passwordStr"
            hasil.text = "Status: Login Berhasil & Data Tertarik!"
        } else {
            Toast.makeText(applicationContext, "Tidak ada data yang dilempar", Toast.LENGTH_SHORT).show()
        }
    }
}
```

## WARNING!!! 
## Di 2 kode kotlin nya ada package com.example.(nama projek) sesuaikan nama projek nya sama punya kelen contoh punya ku com.example.kuliah

<img width="914" height="92" alt="image" src="https://github.com/user-attachments/assets/94f29ee2-1f98-4698-aed3-8d0afac23a04" />


Oke done, terimakasih dan Selamat Ulang Tahun Diannn Ganteng!!! 🎂


<img width="432" height="861" alt="WhatsApp Image 2026-04-17 at 12 05 56" src="https://github.com/user-attachments/assets/fb474278-2ea7-41d2-b08c-5a29dbd69e35" />

No Dana:
089527387081









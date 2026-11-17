# inter-login
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="[http://schemas.android.com/apk/res/android](http://schemas.android.com/apk/res/android)"
    xmlns:app="[http://schemas.android.com/apk/res-auto](http://schemas.android.com/apk/res-auto)"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="24dp"
    android:background="?attr/colorSurface">

    <com.google.android.material.card.MaterialCardView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:cardCornerRadius="24dp"
        app:cardElevation="2dp"
        style="@style/Widget.Material3.CardView.Elevated">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:padding="24dp">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Iniciar Sesión"
                android:textAppearance="?attr/textAppearanceHeadlineMedium"
                android:textColor="?attr/colorOnSurface"
                android:layout_marginBottom="8dp" />

            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/tilUsuario"
                style="@style/Widget.Material3.TextInputLayout.OutlinedBox"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Usuario"
                android:layout_marginBottom="16dp">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/etUsuario"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:inputType="text" />
            </com.google.android.material.textfield.TextInputLayout>

            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/tilPassword"
                style="@style/Widget.Material3.TextInputLayout.OutlinedBox"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Contraseña"
                app:endIconMode="password_toggle"
                android:layout_marginBottom="24dp">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/etPassword"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:inputType="textPassword" />
            </com.google.android.material.textfield.TextInputLayout>

            <com.google.android.material.button.MaterialButton
                android:id="@+id/btnIngresar"
                style="@style/Widget.Material3.Button"
                android:layout_width="match_parent"
                android:layout_height="56dp"
                android:text="Ingresar"
                app:cornerRadius="16dp" />

        </LinearLayout>
    </com.google.android.material.card.MaterialCardView>
</LinearLayout>

package com.tesoem.practica2material3;

import android.content.Intent;
import android.os.Bundle;
import android.text.TextUtils;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
import com.google.android.material.button.MaterialButton;
import com.google.android.material.color.DynamicColors;
import com.google.android.material.textfield.TextInputEditText;
import com.google.android.material.textfield.TextInputLayout;

public class MainActivity extends AppCompatActivity {

    private TextInputLayout tilUsuario, tilPassword;
    private TextInputEditText etUsuario, etPassword;
    private MaterialButton btnIngresar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        // Activar Material You / Dynamic Colors si el dispositivo lo soporta
        DynamicColors.applyToActivityIfAvailable(this);
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        tilUsuario = findViewById(R.id.tilUsuario);
        tilPassword = findViewById(R.id.tilPassword);
        etUsuario = findViewById(R.id.etUsuario);
        etPassword = findViewById(R.id.etPassword);
        btnIngresar = findViewById(R.id.btnIngresar);

        btnIngresar.setOnClickListener(v -> validarAcceso());
    }

    private void validarAcceso() {
        String usuario = etUsuario.getText() != null ? etUsuario.getText().toString().trim() : "";
        String password = etPassword.getText() != null ? etPassword.getText().toString().trim() : "";

        tilUsuario.setError(null);
        tilPassword.setError(null);

        if (TextUtils.isEmpty(usuario)) {
            tilUsuario.setError("Ingrese su usuario");
            return;
        }
        if (TextUtils.isEmpty(password)) {
            tilPassword.setError("Ingrese su contraseña");
            return;
        }

        Toast.makeText(this, "Bienvenido, " + usuario, Toast.LENGTH_SHORT).show();
        Intent intent = new Intent(MainActivity.this, HomeActivity.class);
        intent.putExtra("USUARIO_ACTIVO", usuario);
        startActivity(intent);
    }
}

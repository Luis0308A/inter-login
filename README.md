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

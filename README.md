# dropdown-menu-in-android-studio-
a dropdown menu in android studio 
# first lets create a spinner in the xml layout 
<Spinner
        android:id="@+id/spinner1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_toRightOf="@+id/text"
        android:layout_alignBottom="@+id/text"
        android:textSize="10dp"
        />

  # now lets go the main activity in kotlin 
  package com.example.icash

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.view.View
import android.widget.AdapterView
import android.widget.ArrayAdapter
import android.widget.Spinner
import android.widget.Toast

class iso1 : AppCompatActivity(), AdapterView.OnItemSelectedListener {
    private val users = arrayOf("Suresh Dasari", "Trishika Dasari", "Rohini Alavala", "Praveen Kumar", "Madhav Sai")

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.iso1)

        // Initialize the Spinner
        val spin = findViewById<Spinner>(R.id.spinner1)
        val adapter = ArrayAdapter(this, android.R.layout.simple_spinner_item, users)
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item)
        spin.adapter = adapter
        spin.onItemSelectedListener = this
    }

    override fun onItemSelected(arg0: AdapterView<*>?, arg1: View?, position: Int, id: Long) {
        val selectedUser = users[position]
        Toast.makeText(applicationContext, "Selected User: $selectedUser", Toast.LENGTH_SHORT).show()
    }

    override fun onNothingSelected(arg0: AdapterView<*>?) {
        // TODO - Custom Code
    }
}

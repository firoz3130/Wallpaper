# Wallpaper
MAD Lab
kotlin code here
____________
package com.example.wallpaper<br>
import android.graphics.Bitmap<br>
import android.graphics.BitmapFactory<br>
import androidx.appcompat.app.AppCompatActivity<br>
import android.os.Bundle import android.widget.Button import android.widget.Toast import java.util.*<br>
import android.app.WallpaperManager import kotlin.concurrent.schedule import kotlin.concurrent.timerTask<br>
class MainActivity : AppCompatActivity() {<br>
var myWallpaperlist = arrayOf( R.drawable.one,R.drawable.two, R.drawable.three, R.drawable.four)<br>
private lateinit var changeWallpaper: Button override fun onCreate(savedInstanceState: Bundle?) { super.onCreate(savedInstanceState)<br>
setContentView(R.layout.activity_main)<br>
changeWallpaper = findViewById(R.id.set_wallpaper)<br>
changeWallpaper.setOnClickListener { setWallpapper() }<br>
}<br>
fun setWallpapper() {<br>
Toast.makeText(this, "Setting Wallpaper please wait", Toast.LENGTH_SHORT).show() Timer().schedule(200)<br>
{<br>
for (i in myWallpaperlist) {<br>
val Bitmap = BitmapFactory.decodeResource(resources, i)<br>
val wallpapermanager = WallpaperManager.getInstance(baseContext) wallpapermanager.setBitmap(Bitmap)<br>
}<br>
}<br>
}<br>
}<br>
<br>
changes to be made<br>
_______________________<br>
inside the file androidmanifest.xml<br>
<uses-permissionandroid:name="android.permission.SET_WALLPAPER"/><br>
<br>
xml file(only one button)<br>
___________________________<br>
<br>
<?xml version="1.0" encoding="utf-8"?><br>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"<br> xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent"<br> android:layout_height="match_parent" tools:context=".MainActivity"><br>
<Button android:id="@+id/set_wallpaper" android:layout_width="wrap_content" android:layout_height="wrap_content" android:text="set wallpaper"<br> tools:layout_editor_absoluteX="141dp"<br>
tools:layout_editor_absoluteY="310dp" /><br>
</androidx.constraintlayout.widget.ConstraintLayout><br>

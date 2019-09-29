## Change actionBar text color 
This tutorial is define that how we change the text color of actionBar. So follow the below code.

```
<style name="AppTheme" parent="Theme.AppCompat.Light">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorWhite</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorApp</item>
</style>

<style name="TextAppearance.AppCompat.Widget.ActionBar.Title" parent="@android:style/TextAppearance">
    <item name="android:textSize">23dp</item>
    <item name="android:textColor">@color/colorApp</item>
</style>
```
In second style tag we customize the actionBar title.

Now Add this above code in the application in ```Manifest File```
```
<application
        android:theme="@style/AppTheme">
        <activity>  .....  </activity>
        <activity>  .....  </activity>
</application>
```


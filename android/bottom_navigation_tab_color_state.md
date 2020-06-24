Create a drawable and add below code.
```
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:state_checked="true" android:color="@color/color_blue"/>
    <item android:state_checked="false" android:color="@color/color_gray"/>
</selector>
```

and add this drawble file to below lines in bottom navigation view.

```
app:itemIconTint="@drawable/bottom_navigation_view_color_state"
app:itemTextColor="@drawable/bottom_navigation_view_color_state"
```

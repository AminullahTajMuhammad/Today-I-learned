## Added shade on ImageView to write text on it

First of all create a gradient drawable file that generates gradient and then create a view of same size and dimesion just like imageview.

### Gradient Drawable Xml named   ``` image_shadow_gradient.xml```
Here is the code of drawable xml
```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android" android:shape="rectangle" >
    <corners
        android:radius="10dp"
        />
    <gradient
        android:angle="270"
        android:centerX="300%"
        android:startColor="#00000000"
        android:endColor="#99000000"
        android:type="linear"
        />
    <size
        android:width="270dp"
        android:height="60dp"
        />
    <stroke
        android:width="1dp"
        android:color="#878787"
        />
</shape>
```

and then create a view in your activity xml file just like your imageView and set above code as background of view widget
```
<androidx.appcompat.widget.AppCompatImageView
                android:layout_width="wrap_content"
                android:layout_height="100dp"
                android:scaleType="centerCrop"
                android:src="@drawable/image_src"/>
            <View
                android:layout_width="match_parent"
                android:layout_height="100dp"
                android:background="@drawable/image_shadow_gradient"/>
```

and finally done. Thanks

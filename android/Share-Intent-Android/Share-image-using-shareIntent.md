## Share image using shareIntent in android kotlin

Dependencies  ```implementation 'com.squareup.picasso:picasso:2.71828'```

First of all add these below lines these line ignore the uri errors
```
  // for Image send ignore URI error
  val builder: StrictMode.VmPolicy.Builder = StrictMode.VmPolicy.Builder()
  StrictMode.setVmPolicy(builder.build())
```

Now added below code this method share the image on other application from url/uri using shareIntent.
In My case I used url in below method's parameter
```
    fun shareImageFromURI(url: String?) {
          Picasso.get().load(url).into(object : Target {
              override fun onBitmapLoaded(bitmap: Bitmap?, from: Picasso.LoadedFrom?) {
                  val intent = Intent(Intent.ACTION_SEND)
                  intent.type = "image/*"
                  intent.putExtra(Intent.EXTRA_STREAM, getBitmapFromView(bitmap))
                  startActivity(Intent.createChooser(intent, "Share Image"))
              }
              override fun onPrepareLoad(placeHolderDrawable: Drawable?) { }
              override fun onBitmapFailed(e: java.lang.Exception?, errorDrawable: Drawable?) { }
          })
    }
```

This below method is used to create uri of giving bitmap for sharing.

```
    fun getBitmapFromView(bmp: Bitmap?): Uri? {
       var bmpUri: Uri? = null
          try {
            val file = File(this.externalCacheDir, System.currentTimeMillis().toString() + ".jpg")
            val out = FileOutputStream(file)
            bmp?.compress(Bitmap.CompressFormat.JPEG, 90, out)
            out.close()
            bmpUri = Uri.fromFile(file)

        } catch (e: IOException) {
            e.printStackTrace()
        }
        return bmpUri
    }
```

#### Follow this article and code line by line and share image on other application using shareIntent Dialog

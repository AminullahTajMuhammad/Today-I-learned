Scene Animation Android

val animOn = android.util.Pair.create<View, String>(createBtn, "createBtn")
            val activityOptionsCompat = ActivityOptions.makeSceneTransitionAnimation(this, animOn)
            startActivity(Intent(
                    this@SignUpScreen,
                    FindRestaurantScreen::class.java
            ), activityOptionsCompat.toBundle())

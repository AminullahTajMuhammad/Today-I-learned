# Share Appication Link Using ShareIntent in android in kotlin

## Implementation
``` 
val sendIntent = Intent()
sendIntent.action = Intent.ACTION_SEND
sendIntent.putExtra(
      Intent.EXTRA_TEXT,
      "Hey check out My Application app at: https://play.google.com/store/apps/details?id=${packageName}"
)

sendIntent.type = "text/plain"
startActivity(sendIntent)

```
private var onItemClicked: ((Any) -> Unit)? = null
    fun onItemClickListener(any: ((Any) -> Unit)) {
        onItemClicked = any
}
```

```
_scrollListener() {
  if (isShrink != widget.lastStatus) {
    setState(() {
      widget.lastStatus = isShrink;
    });
  }
}

bool get isShrink {
  return widget._scrollController.hasClients &&
    widget._scrollController.offset > (200 - kToolbarHeight);
}

@override
void initState() {
  widget._scrollController = ScrollController();
  widget._scrollController.addListener(_scrollListener);
  super.initState();
}

@override
void dispose() {
  widget._scrollController.removeListener(_scrollListener);
  super.dispose();
}
```

Call this isShirk getter into Scaffold. Here is the scaffold method.

```
return Scaffold(
  body: NestedScrollView(
    controller: widget._scrollController,
    headerSliverBuilder: (BuildContext context, bool innerBoxIsScrolled) {
      return <Widget>[
        SliverAppBar(
          leading: GestureDetector(
            onTap: () => {},
            child: Icon(
              Icons.arrow_back_sharp,
              color: isShrink ? Colors.black : Colors.white,
            ),
          ),
          expandedHeight: 200.0,
          floating: false,
          pinned: true,
          backgroundColor: Colors.white,
          flexibleSpace: FlexibleSpaceBar(
            centerTitle: true,
            title: Text(
                "Request a Proposal",
                style: TextStyle(
                  color: isShrink ? Colors.black : Colors.white,
                  fontSize: 16.0,
                )),
            background: Image.asset(
              widget.imageUrl,
              fit: BoxFit.cover,
            )
          ),
        ),
      ];
    },
    body: Center(child: Text('Text'),),
  ),
);
```

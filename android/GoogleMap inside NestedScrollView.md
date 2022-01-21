```
public class ScrollGoogleMap extends SupportMapFragment {
    private OnTouchListener mListener;

    @Override
    public View onCreateView(LayoutInflater layoutInflater, ViewGroup viewGroup, Bundle savedInstance) {
        View layout = super.onCreateView(layoutInflater, viewGroup, savedInstance);

        TouchableWrapper frameLayout = new TouchableWrapper(getActivity());

        frameLayout.setBackgroundColor(getResources().getColor(android.R.color.transparent));

        ((ViewGroup) layout).addView(frameLayout,
                new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, ViewGroup.LayoutParams.MATCH_PARENT));

        return layout;
    }

    public void setListener(OnTouchListener listener) {
        mListener = listener;
    }

    public interface OnTouchListener {
        public abstract void onTouch();
    }

    public class TouchableWrapper extends FrameLayout {

        public TouchableWrapper(Context context) {
            super(context);
        }

        @Override
        public boolean dispatchTouchEvent(MotionEvent event) {
            switch (event.getAction()) {
                case MotionEvent.ACTION_DOWN:
                    mListener.onTouch();
                    break;
                case MotionEvent.ACTION_UP:
                    mListener.onTouch();
                    break;
            }
            return super.dispatchTouchEvent(event);
        }
    }
}
```

# Then change your xml where you create google map:

```
<fragment
            android:id="@+id/mygoogle_map"
            android:name="com.example.ScrollGoogleMap"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />
```

# Then change your activity code where you initialize your googlemap:

```
GoogleMap mMap = ((ScrollGoogleMap) getSupportFragmentManager().findFragmentById(R.id.mygoogle_map)).getMap();
mMap.setListener(new WorkaroundMapFragment.OnTouchListener() {
    @Override public void onTouch() {
        binding.nestedScrollView.requestDisallowInterceptTouchEvent(true);
    }
}); 
```

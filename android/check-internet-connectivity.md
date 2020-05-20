## Check Internet is connected or not

````
public static boolean isNetworkAvailable(Context context) {
  ConnectivityManager connectivityManager = 
      (ConnectivityManager) context.getSystemService(Context.CONNECTIVITY_SERVICE);
  NetworkInfo activeNetworkInfo = connectivityManager.getActiveNetworkInfo();
  return activeNetworkInfo != null && activeNetworkInfo.isConnected();
}
````

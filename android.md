### **Useful links**  
[AndroidInterview-Q-A](https://github.com/JackyAndroid/AndroidInterview-Q-A)  
[Android Interview Questions](https://github.com/derekargueta/Android-Interview-Questions)  
[Android Guides](https://github.com/codepath/android_guides)  

### [**Apllication fundamentals**](https://developer.android.com/guide/components/fundamentals.html)


### **Activity Lifecycle**  
![lifecycle](/images/Android-Activity-Lifecycle.png)

### [**Intent**](https://developer.android.com/reference/android/content/Intent.html)  
a messaging object you can use to request an action from another app component  

### [**Fragment** ](https://developer.android.com/reference/android/app/Fragment.html)    


### [**Service**](https://developer.android.com/reference/android/app/Service.html)  
A Service is an application component representing either an application's desire to perform a longer-running operation while not interacting with the user or to supply functionality for other applications to use. Each service class must have a corresponding <service> declaration in its package's AndroidManifest.xml. Services can be started with Context.startService() and Context.bindService().  

### [**AsyncTask**](https://developer.android.com/reference/android/os/AsyncTask.html)  
AsyncTask enables proper and easy use of the UI thread. This class allows you to perform background operations and publish results on the UI thread without having to manipulate threads and/or handlers.  
```
private class DownloadFilesTask extends AsyncTask<URL, Integer, Long> {
    protected Long doInBackground(URL... urls) {
        int count = urls.length;
        long totalSize = 0;
        for (int i = 0; i < count; i++) {
            totalSize += Downloader.downloadFile(urls[i]);
            publishProgress((int) ((i / (float) count) * 100));
            // Escape early if cancel() is called
            if (isCancelled()) break;
        }
        return totalSize;
    }

    protected void onProgressUpdate(Integer... progress) {
        setProgressPercent(progress[0]);
    }

    protected void onPostExecute(Long result) {
        showDialog("Downloaded " + result + " bytes");
    }
}
```

### [**Recyclerview**](https://developer.android.com/reference/android/support/v7/widget/RecyclerView.html)  


### [**Linear Layout**](https://developer.android.com/reference/android/widget/LinearLayout.html)  
A layout that arranges other views either horizontally in a single column or vertically in a single row.  
```
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
   android:layout_width="match_parent"
   android:layout_height="match_parent"
   android:paddingLeft="16dp"
   android:paddingRight="16dp"
   android:orientation="horizontal"
   android:gravity="center">

   <!-- Include other widget or layout tags here. These are considered
           "child views" or "children" of the linear layout -->

 </LinearLayout>
 ```

### [**Relative Layout**](https://developer.android.com/guide/topics/ui/layout/relative.html)  
RelativeLayout is a view group that displays child views in relative positions.

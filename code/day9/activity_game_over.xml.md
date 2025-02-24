```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center">

    <TextView
        android:id="@+id/scoreTextView"
        android:text="Your Score: 0"
        android:textSize="24sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="16dp"/>

    <TextView
        android:id="@+id/leaderboardTextView"
        android:text="Top Scores:\n"
        android:textSize="18sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="16dp"/>
</LinearLayout>

```
# Middle
##基础要求
1.在noteslist里添加时间戳：
 public static final String COLUMN_NAME_CREATE_DATE = "created";
 private static final String[] PROJECTION = new String[] {
            NotePad.Notes._ID, // 0
            NotePad.Notes.COLUMN_NAME_TITLE, // 1
            NotePad.Notes.COLUMN_NAME_CREATE_DATE
    }; 
    SimpleCursorAdapter adapter
                = new SimpleCursorAdapter(
                this,                             // The Context for the ListView
                R.layout.noteslist_item,          // Points to the XML for a list item
                cursor,                           // The cursor to get items from
                dataColumns,                    //data
                viewIDs                            //对应id
        );
        //在ContentProvider中使用COUNT()函数，直接调用数据库，在noteslist类里添加date
        <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:id="@+id/date"
                android:textAppearance="?android:attr/textAppearanceLarge"
                android:gravity="center_vertical"
                android:paddingLeft="5dip"
                android:textColor="#fff"
                />


</LinearLayout>//xml中插入textview，显示时间
2.按标题搜索的查询功能
  private SearchView searchView;
    /**
     * The columns needed by the cursor adapter
     */
    private static final String[] PROJECTION = new String[] {
            NotePad.Notes._ID, // 0
            NotePad.Notes.COLUMN_NAME_TITLE, // 1
            NotePad.Notes.COLUMN_NAME_CREATE_DATE
    };
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <SearchView
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:id="@+id/myquary" />
    <ListView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/mylist"
        android:textFilterEnabled="true">

    </ListView>
</LinearLayout>
//在layout中新建list.xml，并插入searchview
3.美化ui
    
    android:layout_width="match_parent"
    android:layout_height="45dp"
    android:orientation="horizontal"
    android:background="#FA8072"
    android:textColor="#fff"
    //noteslist中
    android:background="#FF6347"
    android:orientation="vertical"
    android:paddingLeft="6dip"
    android:paddingRight="6dip"
    android:paddingBottom="3dip"
    //titleview中
    

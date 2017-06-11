# Middle
##基础要求

![](https://github.com/hellomangogo/Middle/blob/master/images/1.png)

1.在noteslist里添加时间戳：
//新建DateUtil.class类，用于将时间戳转换为指定格式的日期字符串

public class DateUtil {

    /**
     * 将时间戳转换为日期
     * @param seconds
     * @param format
     * @return
     */
    public static String timeStamp2Date(String seconds, String format) {
        if(seconds == null || seconds.isEmpty() || seconds.equals("null")) {
            return "";
        }
        if(format == null || format.isEmpty()) {
            format = "yyyy-MM-dd HH:mm:ss";
        }
        SimpleDateFormat simpleDateFormat = new SimpleDateFormat(format);
        return simpleDateFormat.format(new Date(Long.valueOf(seconds)));
    }
}
//在修改或者创建笔记的时候，保存当前时间为修改时间


        // Sets up a map to contain values to be updated in the provider.
        ContentValues values = new ContentValues();
        //将时间戳转换为日期，保存
        String updateTimeStr = DateUtil.timeStamp2Date(String.valueOf(System.currentTimeMillis()),null);
        values.put(NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE, updateTimeStr);
 public static final String COLUMN_NAME_CREATE_DATE = "created";
 
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
![](https://github.com/hellomangogo/Middle/blob/master/images/G_SISAGIFTO7)J%7DHYNT%7B25M.png)
2.按标题搜索的查询功能
//添加搜索控件SearchView

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
              android:orientation="vertical"
              android:layout_width="match_parent"
              android:layout_height="match_parent">
    <SearchView
        android:id="@+id/search_view"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:queryHint="请输入关键字"
        />
    <ListView
        android:id="@android:id/list"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:drawSelectorOnTop="false"
        >
    </ListView>

    <TextView
        android:id="@android:id/empty"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:text="暂无笔记"
        android:gravity="center"
        />

</LinearLayout>

//新建searchable.xml文件，配置搜索模式

<?xml version="1.0" encoding="utf-8"?>
<!-- 配置搜索模式 -->
<searchable xmlns:android="http://schemas.android.com/apk/res/android"
            android:label="@string/app_name"
            android:hint="@string/search_hint"
            android:searchMode="queryRewriteFromText" />

  
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
![](https://github.com/hellomangogo/Middle/blob/master/images/JQ%5BDGQNKV7%7B%5B86DKWH%40B%60(Y.png)
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
    

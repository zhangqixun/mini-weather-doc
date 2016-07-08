# 顶部工具栏制作

要制作的界面如图所示，可以分为四部分“工具栏”、“今日天气信息”、“一周天气信息”，“其他”。

本次任务为制作工具栏布局,本模块中，只制作顶部工具栏，包含“选择城市”、“分隔符”、“天气名称”、“定位”、“刷新”等控件。如下图所示。

![](imags/02/1.png)

 
## 资源文件

  [下载地址](http://mobile100.zhangqx.com/assets/docs/projects/weather02_res.zip)
  
## 主要步骤

### 1.将资源文件导入到drawable目录中
![](imags/02/2-2.png)

### 2.在“weather_info”布局文件中增加一个RelativeLayout布局
首先将上一节添加的测试用的TextView控件删除。然后，在“weather_info”布局文件中增加一个RelativeLayout布局，之后会在这个布局中依次增加城市图标、城市信息、定位图标、分享图标等。
![](imags/02/image009.png)
### 3.接下来依次在上面的RelativeLayout布局中增加以下组件。
![](imags/02/image010.png)
![](imags/02/image011.png)
![](imags/02/image012.png)
![](imags/02/image013.png)
![](imags/02/image014.png)
![](imags/02/image015.png)

### 4.将程序部署到模拟器或真实机器上运行，查看效果如图所示。

![](imags/02/3-4.png)



## 附录：关键程序代码（weather_info.xml）
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <RelativeLayout
        android:id="@+id/title"
        android:layout_width="fill_parent"
        android:layout_height="45.0dip"
        android:background="#ffcd2626"
        android:gravity="center_vertical">

        <ImageView
            android:id="@+id/title_city_manager"
            android:layout_width="45.0dip"
            android:layout_height="45.0dip"
            android:src="@drawable/title_city" />

        <ImageView
            android:id="@+id/city_seperator"
            android:layout_width="1.0dip"
            android:layout_height="40dip"
            android:layout_marginTop="2.0dip"
            android:layout_toRightOf="@id/title_city_manager"
            android:background="#A71717" />

        <TextView
            android:id="@+id/title_city_name"
            android:layout_width="fill_parent"
            android:layout_height="fill_parent"
            android:layout_toRightOf="@id/city_seperator"
            android:gravity="center_vertical"
            android:paddingLeft="5dip"
            android:text="北京天气"
            android:textColor="#ffffffff"
            android:textSize="22.0sp" />


        <ImageView
            android:id="@+id/title_update_btn"
            android:layout_width="45.0dip"
            android:layout_height="45.0dip"
            android:layout_alignParentRight="true"
            android:layout_gravity="center"
            android:src="@drawable/title_update"
            android:visibility="visible" />


        <ImageView
            android:id="@+id/title_share"
            android:layout_width="45.0dip"
            android:layout_height="45.0dip"
            android:layout_toLeftOf="@id/title_update_btn"
            android:src="@drawable/title_share" />

        <ImageView
            android:id="@+id/title_location"
            android:layout_width="45.0dip"
            android:layout_height="45.0dip"
            android:layout_toLeftOf="@id/title_share"
            android:src="@drawable/base_action_bar_action_city" />
    </RelativeLayout>
</RelativeLayout>

```









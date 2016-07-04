# 获取网络数据


## 主要步骤
### 1.为更新按钮添加单击事件

在UI线程中，为更新按钮(ImageView)增加单击事件，如下图所示。


### 2.从SharedPreferences中读取城市的id，拼接URL地址



通过SharedPreferences读取城市id，如果没有定义则缺省为101010100（北京城市ID）。



### 3.使用******获取网络数据




### 4.在AndroidManifest.xml文件中增加访问INTERNET的权限




### 5.在访问网络前需检查当前网络状态




### 6.程序运行结果






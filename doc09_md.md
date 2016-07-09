# 从数据库中读取城市列表


数据库文件：[下载地址](http://mobile100.zhangqx.com/assets/docs/projects/weather09_res.zip)

city.db城市数据库文件格式如下
![](imags/09/image001.png)


## 主要步骤


### 1.将数据库文件导入到assets目录

![](imags/09/9-1.png)
![](imags/09/9-2.png)
### 2.建立City的Bean
![](imags/09/9-3.png)
![](imags/09/9-4.png)
```
    private String province;
    private String city;
    private String number;
    private String firstPY;
    private String allPY;
    private String allFristPY;
```
### 3.建立MyApplication类
![](imags/09/9-5.png)
![](imags/09/9-7.png)
在AndroidManifest.xml文件中注册Application，代码如下图所示：
![](imags/09/9-6.png)

运行程序结果如下：
![](imags/09/9-8.png)
### 4.在MyApplication类中创建geiInstance方法
![](imags/09/9-9.png)

```
private static MyApplication mApplication;
```
```
mApplication = this;
```
```
    public static MyApplication getInstance(){
        return  mApplication;
    }
```

### 5.创建CityDB操作类


### 6.创建初始化数据库的方法

### 7.初始化城市信息列表

### 8.在程序运行时调用数据库访问方法

程序运行结果如下，可以在程序运行时，在Application对象中打开数据库，并取出城市列表信息数据。






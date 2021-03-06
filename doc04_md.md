# 网络状态检查

应用程序在访问网络资源时，需要先检测网络状态，如果网络不可用，需要提示用户请打开网络，或检查网络连接状况。

因此本次任务是制作一个工具类，用于检查网络状态。


## 主要步骤



### 1.创建一个util包，存放公共的工具类

![](imags/04/4-1.png)
![](imags/04/4-2.png)
### 2.在util文件夹中创建一个NetUtil类

![](imags/04/4-3.png)
### 3.在NetUtil类中实现getNetworkState方法

![](imags/04/4-5.png)

### 4.调用检测网络连接状态方法

在连接网络之前，可以直接通过以下语句检测网络是否连接。

     NetUtil.getNetworkState(this) != NetUtil.NETWORN_NONE

例如，在Activity中增加以下代码，进行测试。
```
 if (NetUtil.getNetworkState(this) != NetUtil.NETWORN_NONE) {
            Log.d("myWeather", "网络OK");
            Toast.makeText(MainActivity.this,"网络OK！", Toast.LENGTH_LONG).show();
        }else
        {
            Log.d("myWeather", "网络挂了");
            Toast.makeText(MainActivity.this,"网络挂了！", Toast.LENGTH_LONG).show();
        }
```

![](imags/04/4-6.png)

### 5.需要增加访问网络状态的权限



![](imags/04/4-4.png)


### 6.运行结果


![](imags/04/4-7.png)
![](imags/04/4-8.png)



## 附录：NetUtil.java源码


```
package cn.edu.pku.zhangqixun.util;

import android.content.Context;
import android.net.ConnectivityManager;
import android.net.NetworkInfo;

/**
 * Created by zhangqixun on 16/7/4.
 */
public class NetUtil {
    public static final int NETWORN_NONE = 0;
    public static final int NETWORN_WIFI = 1;
    public static final int NETWORN_MOBILE = 2;

    public static int getNetworkState(Context context) {
        ConnectivityManager connManager = (ConnectivityManager) context
                .getSystemService(Context.CONNECTIVITY_SERVICE);

        NetworkInfo networkInfo = connManager.getActiveNetworkInfo();
        if (networkInfo == null) {
            return NETWORN_NONE;
        }

        int nType = networkInfo.getType();
        if (nType == ConnectivityManager.TYPE_MOBILE) {
            return NETWORN_MOBILE;
        } else if (nType == ConnectivityManager.TYPE_WIFI) {
            return NETWORN_WIFI;
        }
        return NETWORN_NONE;
    }


}

```




(1)点击桌面图标正常启动App或者杀死进程后点击推送消息启动App

复制代码
1.application:willFinishLaunchingWithOptions

2.application:application:didFinishLaunchingWithOptions

3.applicationDidBecomeActive

4.application:didRegisterForRemoteNotificationsWithDeviceToken
复制代码
 

（2）拖下通知中心/双击Home键使App界面上移

applicationWillResignActive
 

（3）拖上通知中心/使App界面恢复原位

applicationDidBecomeActive
 

（4）按Home键使App进入后台

1.applicationWillResignActive

2.applicationDidEnterBackground 
 

（5）点击App图标，使App从后台恢复至前台

1.applicationWillEnterForeground

2.applicationDidBecomeActive
 

（6）点击通知中心里面的远程推送，使App从后台进入前台

1.applicationWillEnterForeground

2.application:didReceiveRemoteNotification

3.applicationDidBecomeActive
 

（7）按住减号图标杀死App进程

applicationWillTerminate
 

（8）从APP切换到微信之类的其他应用之后，再切换回来时

1.applicationWillEnterForeground

2.application:openURL:sourceApplication

3.applicationDidBecomeActive
 

注:当程序处于后台时，点击推送消息进入前台会执行application:didReceiveRemoteNotification，但直接点击推送消息启动App是不会执行该didReceiveRemoteNotification的，在didFinishLaunchingWithOptions的options里面已经有数据表明当前是直接启动还是点击推送消息启动，localNotification与remote类似，略。

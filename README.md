# aidl
AS中进程间的通信
改用Android Studio后aidl文件不能按照传统ADT的方式在src目录下建包引入文件，这样操作在类里无法导包找不到class文件。
多处询问未果，最后才发现AS初次导入Eclipse项目时的已经再import-summary.txt中提醒了


Android Gradle projects use a different directory structure than ADT

Eclipse projects. Here's how the projects were restructured:

 项目迁移后文件夹变动如下：

* AndroidManifest.xml => app\src\main\AndroidManifest.xml

* assets\ => app\src\main\assets\

* libs\xUtils-2.5.5.jar => app\libs\xUtils-2.5.5.jar

* proguard-android.txt => app\proguard-android.txt

* proguard-project.txt => app\proguard-project.txt

* res\ => app\src\main\res\

* src\ => app\src\main\java\

* src\android\content\pm\IPackageDataObserver.aidl => app\src\main\aidl\android\content\pm\IPackageDataObserver.aidl

* src\android\content\pm\IPackageStatsObserver.aidl => app\src\main\aidl\android\content\pm\IPackageStatsObserver.aidl

* src\android\content\pm\PackageStats.aidl => app\src\main\aidl\android\content\pm\PackageStats.aidl

* src\android\telephony\NeighboringCellInfo.aidl => app\src\main\aidl\android\telephony\NeighboringCellInfo.aidl

* src\com\android\internal\telephony\ITelephony.aidl => app\src\main\aidl\com\android\internal\telephony\ITelephony.aidl

引入aidl文件:如提示中所说需要在app\src\main下创建aidl目录，接着包名\文件名.aidl


例：adt中文件路径：
src\android\content\pm\IPackageDataObserver.aidl 

Android Studio中文件路径：
app\src\main\aidl\android\content\pm\IPackageDataObserver.aidl 

最后，如果你根据我的路径创建导入aidl还是报错找不到，只需要Clean Project一下就好

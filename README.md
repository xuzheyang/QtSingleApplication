# QtSingleApplication  

Qt程序的单实例实现  

使用步骤：  
1.git clone git@github.com:xuzheyang/QtSingleApplication.git  
2.在Qt项目中添加`SingleApplication.cpp`和`SingleApplication.h`  
3.在`main.cpp`中添加：  

~~~  
#include "mainwindow.h"
#include <QApplication>
#include <QtSingleApplication>

int main(int argc, char *argv[])
{
    SingleApplication a(argc, argv);
    if(!a.isRunning()) {
        MainWindow w;
        a.w = &w;

        w.show();

        return a.exec();
    }
    return 0;
}
~~~

4.在`xxx.pro`文件中添加：  

~~~
Qt    += network
~~~

# cactus库内容如下:

- 常用字符串操作
- 数据缓冲区封装
- 异常基类
- 文件访问
- 注册表访问
- 进程操作
- windows服务操作
- windows系统信息获取
- dll调用封装
- ini文件操作
- md5
- base64
- 高精度定时器
- mongoose http服务器封装
- sqlite操作
- ahk 封装
- log日志
- tracetool 调试信息
- libcurl 的简单封装，http client 

待添加的新特性:

- ...


cactus 可编译为C++ dll动态导出库， 与导出接口不同的是，这些导出类可以直接以 new 实例的方式创建对象， cactus的目标是构建一个常用的
底层基类库，dll导出库容易出现的问题就是“DLL Hell”，向后版本的二进制兼容性上，解决这个问题的方式基本上是导出没有虚函数的类，比如采用
Pimpl的方式导出类，这样的类没有虚函数，没有成员变量，往后升级没有问题。

cactus 库依赖于STL， ATL(CString, CRegKey等帮助类)， Boost， libcurl

windows sdk下的Shlwapi.h提供了大量的路径操作和字符串操作可用

+----------------+--------------------------------------------------------------------------+
|                                                                                          |
|                               UI                                                         |
|                                                                                          |
+----------------+--------------------------------------------------------------------------+
|                |            |              |                                              |
|    业务 dll      |   业务dll   |    业务dll    |    业务dll...                                 |
|                |            |              |                                              |
+----------------+--------------------------------------------------------------------------+
|                             |                   |                                         |
|               cactus        |     duilib        |     3rdparty                            |
|                             |                   |                                         |
+----------------+--------------------------------------------------------------------------+
|                |               |             |                                            |
|     STL        |     ATL       |    Boost    |            ...                             |
|                |               |             |                                            |
+----------------+--------------------------------------------------------------------------+









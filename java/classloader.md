### 自定义类加载器
##### 为什么需要自定义类加载器？

原因比如，默认的classloader只能加载本地目录的class文件，有时候需要从远程加载class文件，所以有URLClassLoader。
  
##### 怎么自定义classloader？

包括三个重要api：
* loadClass函数
* findClass函数
* defineClass函数：可以将字节码转成类,在漏洞利用中非常重要

loadClass没有找到类时，会调用findClass、defineClass。

##### defineClass是怎么实现的？

查看java.lang.ClassLoader的defineClass函数，最终有个native实现`defineClass1`

# 参考
java-sec/基础/工具/yso/3.漏洞利用时TemplatesImpl类的作用.md
访问127.0.0.1:8080报500
网页报错：Servlet.service() for servlet [jsp] in context with path [] threw exception [org.apache.jasper.JasperException: Unable to compile class for JSP] with root cause
这个是因为没有添加jsp解析器，添加即可，方法如下
编辑 org.apache.catalina.startup.ContextConfig 文件的 configureStart() 方法，添加初始化 JSP 解析器的代码
context.addServletContainerInitializer(new JasperInitializer(), null);

————————————————
版权声明：本文为CSDN博主「huhuhu1234565asdf」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_41452805/article/details/113716210

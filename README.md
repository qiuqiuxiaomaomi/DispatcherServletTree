# DispatcherServletTree
DispatcherServlet源码，处理流程


![](https://i.imgur.com/zZWHyS6.png)

<pre>
具体请求过程：
 
      1）用户请求发送至 DispatcherServlet类进行处理。
      2）DispatcherServlet类遍历所有配置的HandlerMapping类请求查找Handler
      3) HandlerMapping类根据request请求的URL等信息查找能够进行处理的Handler，以及相关
         拦截器interceptor并构造HandlerExecutionChain
      5）HandlerMapping类将构造的HandlerExecutionChain类的对象返回给前端控制器
         DispatcherServlet类。
      6）前端控制器拿着上一步的Handler遍历所有配置的HandlerAdapter类请求执行Handler。
      7）HandlerAdapter类执行相关的Handler并获取ModelAndView类的对象。
      8）HandlerAdapter类将上一步Handler执行的结果ModelAndView类的对象返回给前端控制器。
      9）DispatcherServlet类遍历所有的配置的ViewResolver类进行视图解析。
      10）ViewResolver类进行视图解析并获取View对象。
      11）ViewResolver类向前端控制器返回上亿步骤的View对象。
      12）DispatcherServlet类进行视图View的渲染，填充Model
      13）DispatcherServlet向用户返回响应。
</pre>

### Servlet生命周期

![](https://i.imgur.com/1lecgj3.png)

<pre>
Servlet生命周期

      init()方法
      容器调用 Servlet的doPost, doGet等方法
      destroy()方法
</pre>
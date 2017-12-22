# JSP九大内置对象  
>在Servlet中经常会使用到HttpSession、ServletContext等对象，为了方便，在JSP页面加载完毕后,jsp自动帮开发者创建好了这些对象,开发者只需要使用相应的对象调用相应的方法即可。  

内置对象名|类型|作用
--------|----|---
request|HttpServletRequest|
response|HttpServletResponse|
config|ServletConfig|
application|ServletContext|
session|HttpSession|
exception|Throwable|
page|Object(this)|
out|JspWriter|向JSP缓冲区写内容
pageContext|PageContext|JSP上下文对象，可以获取其他内置对象


# EL表达式
> EL表达式替代的是<%=%>JSP输出脚本，也就是说EL只能做输出；  
EL可以输出的东西都在11个内置对象中，11个内置对象，其中10个是Map，只有pageContext不是Map，它就是PageContext类型。  

## EL表达式的用法：  
```
用法：${...}  
EL表达式在获取Map的值或Bean的属性值值，可以使用“点”的方法，也可以使用“下标”的方法。  
${initParam.a}与${initParam['a']}，它们是完成的东西相同的。  
但是，如果Map的键或Bean的属性名中包含下划线或横岗时，那么就必须使用“下标”方法。
例如：${initParam['a_a']}
```

## 11个内置对象：
- pageScope  
  相当于jsp的`pageContext.getAttribute("xxx");`用于获取pageContext域的属性值;
- sessionScope  
  相当于`session.getAttribute("xxx");`用于获取当前会话域的属性值;
- applicationScope  
  相当于`application.getAttribute("xxx");`用于获取当前服务器域的属性值;
- requestScope  
  相当于`request.getAttribute("xxx");`用于获取当前请求域的属性值;
- param  
  是一个MAP，key是参数，value是参数对应的值;  
  相当于`request.getParameter("xxx");`用于获取当前请求传来的参数;
- paramValues  
  是一个MAP，key是参数，value是参数对应的多个值;  
  相当于`request.getParameterValues("xxx");`用于获取当前请求传来的多个参数;
- header  
  是一个MAP，key是头名，value是单值;  
  相当于`request.getHeader("xxx");`用于单值的请求头;
- headerValues  
  是一个MAP，key是头名，value是多值;  
  相当于`request.getParameterValues("xxx");`用于多个值的请求头。
- initParam  
  ```xml
    <context-param>
      <param-name>SpringConfig</param-name>
      <param-value>/WEB-INF/application-context.xml</param-value>
    </context-param>
  ```
  用于获取web.xml中定义的<context-param>上下文参数;  
  ${intiParam.xxx}其中xxx是<param-name>标签的值;  
  ${intiParam.xxx}就得到了<param-value>标签的值;
- cookie  
  是一个MAP，key是cookie的那么，value是Cookie对象;  
  用于获取Cookie对象，如`${cookie.JSESSIONID.value}`获取获取Cookie中的sessionID;  
- pageContext  
  用于获取JSP的九大对象;
  `${pageContext.request}`相当于`pageContext.getRequest`

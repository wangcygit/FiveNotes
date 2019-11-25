# 						                                                                                                         <span style='color:red;'> http协议 </span>

1. ### <span style='color:purple;'> http的简介：</span>

   http是一个简单的请求-响应协议，它通常运行在TCP之上。它指定了客户端可能发送给服务器什么样的消息以及得到什么样的响应。请求和响应消息的头以ASCII码形式给出；而消息内容则具有一个类似MIME的格式。这个简单模型是早期Web成功的有功之臣，因为它使得开发和部署是那么的直截了当

2. ### <span style='color:purple;'> 工作原理：</span>

   HTTP是基于客户/服务器模式，且面向连接的。典型的HTTP事务处理有如下的过程：

   （1）客户与服务器建立连接；

   （2）客户向服务器提出请求；

   （3）服务器接受请求，并根据请求返回相应的文件作为应答；

   （4）客户与服务器关闭连接。

3. ### <span style='color:purple;'> 运作方式：</span>

   在WWW中，“客户”与“服务器”是一个相对的概念，只存在于一个特定的连接期间，即在某个连接中的客户在另一个连接中可能作为服务器。基于HTTP协议的客户/服务器模式的信息交换过程，它分四个过程：建立连接、发送请求信息、发送响应信息、关闭连接。

4. ### <span style='color:purple;'> 报文格式：</span>

   HTTP报文由从客户机到服务器的请求和从服务器到客户机的响应构成。请求报文格式如下： [7] 

   请求行 － 通用信息头 － 请求头 － 实体头 － 报文主体

   请求行以方法字段开始，后面分别是 URL 字段和 HTTP 协议版本字段，并以 CRLF 结尾。SP 是分隔符。除了在最后的 CRLF 序列中 CF 和 LF 是必需的之外，其他都可以不要。有关通用信息头，请求头和实体头方面的具体内容可以参照相关文件。

   应答报文格式如下：

   状态行 － 通用信息头 － 响应头 － 实体头 － 报文主体

   状态码元由3位数字组成，表示请求是否被理解或被满足。原因分析是对原文的状态码作简短的描述，状态码用来支持自动操作，而原因分析用来供用户使用。客户机无需用来检查或显示语法。有关通用信息头，响应头和实体头方面的具体内容可以参照相关文件。

5. ### <span style='color:purple;'> 状态消息：</span>

   ![](/home/wangcy/notes/wcy/picture/1状态码.jpg)

   ![](/home/wangcy/notes/wcy/picture/2状态码.jpg)

   ![](/home/wangcy/notes/wcy/picture/3状态码.jpg)



<img src="/home/wangcy/notes/wcy/picture/4状态码.jpg" style="zoom:150%;" />

<img src="/home/wangcy/notes/wcy/picture/5状态码.jpg" style="zoom:150%;" />




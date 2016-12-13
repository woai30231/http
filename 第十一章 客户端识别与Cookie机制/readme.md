## 内容提要

* 本章介绍了http验证用户的一种机制————cookie,以及cookie的一些概念细节！

### 外在原因

* http最初是一个匿名、无状态的请求/响应协议。服务器处理来自客户端的请求，然后向客户端回送一条响应。web服务器几乎没有什么信息可以用来判定是哪个用户发送的请求，也无法记录来访用户的请求序列。

### 能解决的问题

* 以在线商店为例讲解有了http有了验证身份的机制之后可以实现那些功能，（当然没有这个机制的情况下也可以实现，但是可能会传很多参数来保证身份信息）：

1、个性化的问候

2、有的放矢的推荐

3、管理信息的存档

4、记录会话

#### http报文中承载用户信息的首部

1、From:用户的E-mail地址

2、User-Agent:用户代理或爬虫标记

3、Referer:当前页面是从那个页面跳过来的

4、Authoriztion:用户的用户名和密码

5、Client-IP : 扩展（请求）

6、X-Forwarded-For : 扩展（请求）

7、Cookie:扩展（请求）


#### 客户端IP地址

* 早起的web曾以客户端的ip地址信息来作为验证用户的身份机制，但存在很多缺点，如：

1、首先ip标记是客户端机器，而不是用户，也就是说多个用户公用一台机器，是无法识别的！

2、很多ip地址是动态的，所以不能在一次会话之间用ip地址来验证一个用户信息

3、使用代理的时候，此时发送的ip地址是代理的ip地址，而不是用户的ip地址，虽然代理可以加一个首部来保证最初的ip地址信息，但是不兼容

4、ip地址很容伪造，所以不安全


#### 用户登录

* 这种方法的主要原理就是：在初始访问的时候，服务器返回报文并添加WWW-Authorization首部，用以弹出一个窗口要求用户填写用户名和密码等信息！客户端在下次访问的时候就可以传送带有Authorization的首部，并把相关身份信息传输过去以此验证用户信息，以后的每次请求都会带上这个首部！

#### 胖URL

* 把用户信息添加进url的url称为胖url，以此来验证用户身份，但这种机制有以下缺点：

1、丑陋的url

2、无法共享url,因为用户信息在url里面，共享url同时也会把用户信息共享出去了

3、破坏缓存

4、额外的服务器负荷

5、逃逸口，很容易造成用户不小心跳到另一个网站，返回过来的收用户的信息全部没了，比如购物车里面的东西全部没了

6、会话是非持久的

#### Cookie

* 分类：会话Cookie（非持久Cookie）和持久Cookie

* 原理：用户第一次请求服务器时，服务器返回一个带Set-Cookie（Set-Cookie1）首部的报文，值为键值对，描述了cookie的名字、值、域、路径等信息，然后客户端接下来每次访问服务器的时候都会带上一个Cookie首部的报文，它的值刚好是前面响应报文返回的名字键值对，从而达到验证用户身份的信息。

#### Cookie的属性

* domain : cookie的域

* allh : 那些主机可以使用此cookie

* path ：那些路径能使用cookie

* secure : 是否在发送https报文的时候使用cookie

* expires ： 过期时间

* name ： cookie的名字

* value : cookie的值

#### 不同站点使用不同的cookie

 
 * cookie不能任意使用，只能在它自己设定的域、主机、路径里面使用

#### cookie版本

 * cookie机制有个两个版本，一个是网景公司主导的“版本0”，主要是服务器返回“Set-Cookie”首部，而客户端请求发送“Cookie”首部，客户端发送请求时，会将所有与域、路径和安全过滤器相匹配的未过期cookie都发送给这个站点。所有cookie都被组合到一个Cookie首部中，如：

 ``` 
 		Cookie: session-id=002-1145265-8016938; session-id-time=1311313313131
 ```

 cookie机制还有一个版本就是RFC 2965定义的一个cookie的扩展版本。这个版本1标准引入了Set-Cookie2首部和Cookie2首部，但它也能与“版本0”系统进行互操作。“版本1”跟“版本0”的区别就是，提供了更多的属性来描述一个cookie,同时服务器端发送的是“Set-Cookie”首部，而客户端发送的是“Cookie”首部，如：

 ```
 		服务器端
 	 	Set-Cookie2: ID="29046"; Domain=".joes-hardware.com"
 	 	Set-Cookie2: color=blue
 	 	Set-Cookie2: support-pref="L2"; Domain="customer-care.joes-hardware.com"
 	 	Set-Cookie2: Coupon="hammer027"; Version="1"; Path="/tools"
 	 	Set-Cookie2: Coupon="handvac103"; Version="1";Path="/tools/cordless"

 	 	客户端
 	 	Cookie: $Version="1";
 	 			ID="29046"; $Domain=".joes-hardware.com";
 	 			color="blue";
 	 			Coupon="hammer027"; $Path="/tools";
 	 			Coupon="handvac103"; $Path="/tools/cordless"
 ```

另外Cookie2首部是用来沟通支持版本0和版本1的服务器的，它会发送当前客户端支持的最新版本cookie版本，如：

```
		Cookie2: $Version="1"
```











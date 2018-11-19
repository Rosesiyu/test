### 1、存储位置不同

***Cookie的数据信息存放在客户端浏览器上

***Session的数据信息存放的服务器

### 2、存储容量不同

***单个Cookie保存的数据≤4Kb，一个站点最多保存20个Cookie

***对于Session并没有上限，但出于对服务器端的性能考虑，Session内不要存放过多的东西，设置Session删除机制

### 3、存取方式的不同

***Cookie中只能保管ASCII字符串，需要通过编码的方式存取Unicode字符或者二进制数据。运用Cookie难以实现存储略微复杂的信息

***Session中能够存取任何类型的数据，包括且不限于String、Integer、List等

### 4、隐私策略嗯大不同

***Cookie对客户端是可见的，别有用心的人可以分析存放在本地的Cookie并进行Cookie欺骗，所以它是不安全的

***Session存储在服务器上，对客户端是透明的，不存在敏感信息泄露的风险。

假如选用Cookie，比较好的方法是：敏感的信息如账号密码等，尽量不要写道Cookie中。可以将Cookie信息加密，提交到服务器后再进行解密。

### 5、有效期上的不同

***可通过设置Cookie的属性，达到使Cookie长期有效的效果

***由于Session依赖于名为JSESSIONID的Cookie，而Cookie JSESSIONID的过期时间默认为-1，只需关闭窗口，该Session就会失效，因而Session不能达到长期有效的效果。就算不依赖于Cookie，运用URL地址重写也不能完成，因为加假如设置Session的超时时间过长，服务器累计的Session就会越多，越容易导致内存溢出。

### 6、服务器压力的不同

***Session是保管在服务器端的，每个用户都会产生一个Session。假如并发访问的用户十分多，会产生十分多的Session，耗费大量的内存。

***Cookie保存在客户端，不占用服务器资源。对于并发用户十分多的网站，Cookie是很好的选择

### 7、浏览器支持的不同

假如客户端浏览器不支持Cookie

***Cookie是需要客户端浏览器支持的。假如客户端禁用了Cookie，或者不支持Cookie，则会话跟踪会失效

***运用Session需要使用URL地址重写的方式。一切用到Session程序的URL都要进行URL地址重写，否则Session会话跟踪还会失效。

假如客户端支持Cookie

***Cookie既能够设为本地浏览器窗口以及子窗口内有效（把过期时间设为-1），也能够设为一切窗口内有效（过期时间设为大于0的整数）

***Session只能在本窗口以及其子窗口有效。假如两个浏览器窗口互不相干，它们将运用两个不同的Seesion。

### 8、跨域支持上的不同

***Cookie支持跨域名访问，例如，将domain属性设置为“.biaodianfu.com”，则以“.biaodianfu.com”为后缀的一切域名均能够访问该Cookie。

***Session则不会支持跨域名访问。Session仅在它所在的域名内有效。

参考书籍《Python测试之道》

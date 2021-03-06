## ETag
在HTTP1.1规范中，新增了一个HTTP头信息：ETag。对Web开发者来说，它是一个非常重要的信息。它是用作缓存使用的两个主要的头信息之一 (另一个是Expires)。除此之外，在REST架构中，它还可以用于控制并发操作。

ETag：是实体标签(Entity Tag)的缩写。ETag一般不以明文形式相应给客户端。在资源的各个生命周期中，它都具有不同的值，用于标识出资源的状态。当资源发生变更时，如果其头信息中一个或者多个发生变化，或者消息实体发生变化，那么ETag也随之发生变化。

**ETag标示URL对象是否改变，这样可利用客户端（例如浏览器）的缓存。** 由服务器首先产生ETag，客户端通过将该记号传回服务器要求服务器验证其（客户端）缓存。服务器使用它来判断页面是否已经被修改，如果未修改返回304，而不必重新传输整个对象。

## 情景

当发送一个服务器请求时，浏览器首先会进行缓存过期判断。浏览器根据缓存过期时间判断缓存文件是否过期。<br>

情景一：若没有过期，则不向服务器发送请求，直接使用缓存中的结果，此时我们在浏览器控制台中可以看到  `200 OK`(from cache) ，此时的情况就是完全使用缓存，浏览器和服务器没有任何交互的。


情景二：若已过期，则向服务器发送请求，此时请求中会带上①中设置的文件修改时间，和`Etag`



然后，进行资源更新判断。服务器根据浏览器传过来的文件修改时间，判断自浏览器上一次请求之后，文件是不是没有被修改过；根据`Etag`，判断文件内容自上一次请求之后，有没有发生变化

情形一：若两种判断的结论都是文件没有被修改过，则服务器就不给浏览器发`index.html`的内容了，直接告诉它，文件没有被修改过，你用你那边的缓存吧—— `304 Not Modified`，此时浏览器就会从本地缓存中获取`index.html`的内容。此时的情况叫协议缓存，浏览器和服务器之间有一次请求交互。<br>

情形二：若修改时间和文件内容判断有任意一个没有通过，则服务器会受理此次请求，之后的操作同①

<br>

① 只有get请求会被缓存，post请求不会

<!-- YAML
added: v8.0.0
-->

* {number} 超时毫秒. 默认为 5000 (5秒).

服务器完成最后的响应之后需要等待的额外的传入数据的活跃毫秒数, socket 才能被销毁.  
如果服务器在 keep-alive 计时已激活时接收到新的数据, 他会重置常规的非活动计时, 即[`server.timeout`][]. 

值为 `0` 时禁用传入连接 keep-alive 的超时行为。
A value of `0` makes the http server behave similarly to Node.js versions prior to 8.0.0,
which did not have a keep-alive timeout.

*注意*: scoket 的超时逻辑上取决于服务器连接, 所以改变这个值只影响服务器的新连接, 不影响任何已存在的连接.

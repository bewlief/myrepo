https://www.php.cn/web/web-http.html
#1xx 临时响应  
##100 Continue 继续
服务器已经收到了请求的第一部分，现正在等待接受其余部分
##101 Switching Protocols 切换协议
请求者已要求服务器切换协议，服务器已确认并准备进行切换
#2xx 成功  
##200 OK 成功
服务器已成功处理了请求
##201 Created 已创建
请求成功且服务器已创建了新的资源
##202 Accepted 已接受
服务器已接受了请求，但尚未对其进行处理。最终该请求
也可能不会被执行
##203 Non-Authoritative Information 非授权信息
服务器已经处理了请求，但返回的实体头部元信息不是在原始服务器上有效的确定集合，而是来自本地或者第三方的拷贝
##204 No Content 无内容
服务器成功处理了请求，但不需要返回任何实体内容。用户浏览器应保留发送了该请求的页面，而不产生任何文档视图上的变化
##205 Reset Content 重置内容
服务器成功处理了请求，但未返回任何内容，此响应要求请求者重置文档视图
##206 Partial Content 部分内容
服务器成功处理了部分 GET 请求
#3xx 重定向  
##300 Multiple Choice 多种选择
服务器根据请求可执行多种操作，根据请求者来选择一项操作，或提供操作列表供请求者选择
##301 Moved Permanently 永久移动
请求的网页已永久移动到新位置，返回的信息中包含新的URI，浏览器会自动定向到新的 URI。以后的请求应该使用新的 URI
##302 Moved Temporarily 临时移动
服务器目前正从不同位置的网页响应请求，但请求者应继续使用原有位置来进行以后的请求
##303 See Other 查看其它位置
对当前请求的响应，可以在另一个 URI 上被找到，而且客户端应该使用 GET 去访问那个资源
##304 Not Modified 未修改
自从上次请求后，请求的网页未被修改过，不会返回网页内容
##305 User Proxy 使用代理
请求者只能使用代理访问请求的网页，Location 域中给出指定的代理的 URI 信息
##306 Switch Proxy  此状态码已不再使用
##307 Temporary Redirected 临时重定向
服务器目前正从不同位置的网页响应请求，但请求者应继续使用原有位置来进行以后的请求
#4xx 请求错误  
##400 Bad Request 错误请求
服务器不理解请求的语法
##401 Unauthorized 未授权
请求要求进行身份验证。登陆后，服务器可能会返回对页面的此响应
##402 Payment Required  （预留）
##403 Forbidden 已禁止
服务器拒绝执行请求
##404 Not Found 未找到
服务器找不到请求的网页
##405 Method NotAllowed 方法禁用
禁用请求中所指定的方法，返回的 Allow 头信息中包含当前资源能够接受的请求方法的列表
##406 Not Acceptable 不接受
请求的资源的内容特性无法满足请求头中的条件，因此无法生成响应实体
##407 Proxy Authentication Required 需要代理授权
此状态码与 401 相似，但却指定了请求者应当使用代理进行授权，代理服务器必须返回 Proxy-Authenticate
##408 Request Timeout 请求超时
服务器等候请求时超时
##409 Confilict 冲突
服务器在完成客户端的 PUT 请求时发生冲突。响应实体中可能包含有关响应中所发生的冲突的信息
##410 Gone 已删除
请求的资源已被永久删除
##411 Length Required 需有效长度
服务器不会接纳包含无效内容长度标头字段的请求，即缺少 Content-Length 标记头
##412 Precondition Failed 未满足前提条件
服务器未满足请求者再请求中设置的一个前提条件
##413 Request Entity Too Large 请求实体过大
请求实体过大，超出服务器的处理能力，服务器可能会关闭连接。如果返回 Retry-After，则表示服务器只是暂时无法处理
##414 Request-URI Too Long 请求的 url 过长
请求的 URL 过长，服务器无法处理。
##415 Unsupported Media Type 不支持的媒体类型
请求的格式不受请求页面的支持
##416 Requested Range Not Satisfiable 客户端请求的范围无效。
并且 Range 中指定的任何数据范围都与当前资源的可用范请求范围不符合要求  围不重合，同时请求中又没有定义 If-Range 请求头，那么服务器就应当返回 416 状态码
##417 Expectation Failed 未满足期望值
服务器为满足“期望”请求标头字段的要求
##421 too many connections 
##422 Unprocessable Entity  
请求格式正确，但包含语义错误，无法响应
##423 Locked  当前资源被锁定
##424 Faield Dependency  
之前的某个请求发生的错误，导致当前请求失败，如 PROPATCH
##425 Unordered Collection 
##426 Upgrade Required  
客户端应当切换到 TLS/1.0
##449 Retry With  
微软扩展，请求应当在执行完适当的操作后重试
##451 Unavailable For Legal Reasons
当用户请求访问某个经政府审核等查核方法后认定不合法的来源时，就会显示这个错误代码。
必须携带一个带有一个 Link 头部，列出要求封禁该地址的实体 URI；且应带有一个"rel"字段，值应为"blocked-
by"。
#5xx 服务器错误
##500 Internal Server Error 服务器内部错误
服务器遇到错误无法完成请求
##501 Not Implented 尚未实施
服务器 u 不具备完成请求的功能
##502 Bad Gateway 错误网关
服务器作为网关或代理，从上游服务器受到了无效的响应
##503 Service Unavailable 服务不可用
目前无法使用服务器（由于超载或进行停机维护）
##504 Gateway Time-out 网关超时
服务器作为网关或代理，未及时从上游服务器接收请求
##505 HTTP Version not supported HTTP 版本不受支持
服务器不支持请求中所使用的 HTTP 协议版本

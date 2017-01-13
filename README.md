# local.http.proxy
------
要求：
> * openresty-1.11.2.2 使用其中函数split
> * openresty的第三方http包(https://github.com/agentzh/lua-resty-http-simple)

###PHP示例代码：

```php
$ch = curl_init('http://www.baidu.com/');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_HEADER, 0);
curl_setopt($ch,CURLOPT_PROXY,'127.0.0.1:8888');//设置代理服务器

$output = curl_exec($ch);
if($output === false)
{
    echo 'Curl error: ' . curl_error($ch);
}
curl_close($ch);
echo $output;
```
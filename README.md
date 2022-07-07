# crypto-api

Spring boot Api接口，请求参数解密，请求结果加密例子  
加密选择简单的AES加密。`AES/CBC/PKCS5Padding`  
主要针对 `@RequestParam` `@RequestBody` `@ResponseBody`进行实现。

## 实现

1. `@RequestBody` 使用了`RequestBodyAdviceAdapter`
2. `@ResponseBody` 使用了 `ResponseBodyAdvice`
3. `@RequestParam` 使用了 `HttpServletRequestWrapper` + `Filter`


测试例子见 `sample`包下。

使用需要配置文件，如下

```yaml
crypto-api:
  urls:
    demo1:
      url: /user
      aesKey: f5d830d77163a58f
    demo2:
      url: /query
      aesKey: f5d830d77163a58f
```

<!--
 * @Author: 殷晨东 462085920@qq.com
 * @Date: 2024-10-23 11:53:22
 * @Description:
-->

# deploy-certificate-to-aliyun

自动部署泛解析证书到阿里云 CDN 上
2024-10-23 14:37

## 如何使用

fork 该项目，并填写对应参数，再 push 一次代码即可（随便改点啥，workflow 需要 push 才能触发）

GitHub 仓库的 "Settings" -> "Secrets and variables" -> "Actions" 中添加以下 secrets：

- `ALIYUN_ACCESS_KEY_ID`：阿里云账户 AK
- `ALIYUN_ACCESS_KEY_SECRET`：阿里云账户 SK
- `DOMAINS`: 要设置域名的二级域名，例如要设置\*.example.com，这里填写的就是 example.com, 多个域名用英文逗号隔开
- `ALIYUN_CDN_DOMAINS`：设置阿里云 cdn 域名，一般是三级域名，例如 cdn.example.com，需要跟上面的 DOMAINS 对应，否则会设置错误
- `EMAIL`: 证书过期时提醒的邮件

## 相关文档

> 这里使用的是阿里云提供的 api 进行的调用
>
> - 设置 CDN 证书：https://next.api.aliyun.com/document/Cdn/2018-05-10/SetCdnDomainSSLCertificate

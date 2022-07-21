# 使用 OpenSSL 自制 SSL 证书 和 Nginx 配置 Https

## 实现 https://localhost 访问 API

### 生成私钥

```
openssl genrsa -des3 -out server.pass.key 2048
```

genra 生成 RSA 私钥<br />
-des3 des3 算法<br />
-out server.key 生成的私钥文件名<br />
2048 私钥长度

#### log

```
Enter PEM pass phrase:需输入一个 4 位以上的密码
Verifying - Enter PEM pass phrase:
```

### 去掉私钥密码

```
openssl rsa -in server.pass.key -out server.key
```

#### log

```
Enter pass phrase for server.pass.key:上一步输入的密码
writing RSA key
```

### 生成 CSR 文件（用于请求证书签名）

```
openssl req -new -key server.key -out server.csr -subj "/C=CN/ST=Zhejiang/L=Hangzhou/O=Developers/OU=Developers/CN=localhost"
```

req 生成证书签名请求<br />
-new 新生成<br />
-key 私钥文件<br />
-out 生成的 CSR 文件 <br />
-subj 生成 CSR 证书的参数

subj 参数说明如下：<br />
/C = Country 国家 CN<br />
/ST = State or Province 省 Zhejiang<br />
/L = Location or City 城市 Hangzhou<br />
/O = Organization 组织或企业 Developers<br />
/OU = Organization Unit 部门 Developers<br />
/CN = Common Name 域名 或 IP localhost

### 生成自签名 SSL 证书

```
openssl x509 -req -days 3650 -in server.csr -signkey server.key -out server.crt
```

-days 证书有效期

X.509 证书包含三个文件：key，csr，crt
key 是服务器上的私钥文件，用于对发送给客户端数据的加密，以及对从客户端接收到数据的解密
csr 是证书签名请求文件，用于提交给证书颁发机构（CA）对证书签名
crt 是由证书颁发机构（CA）签名后的证书，或者是开发者自签名的证书，包含证书持有人的信息，持有人的公钥，以及签署者的签名等信息
在密码学中，X.509 是一个标准，规范了公开秘钥认证、证书吊销列表、授权凭证、凭证路径验证算法等。

### 以上，就成功制作了 ssl 证书

## Nginx 配置使用

```
# https默认端口是443
server {
    listen 443 ssl;
    server_name localhost;

    # 证书路径
    ssl_certificate credentials/server.crt;
    ssl_certificate_key credentials/server.key;

    location / {
            proxy_pass http://127.0.0.1:9090/;
        }
}
```



# SSL 证书管理

SSL 证书管理功能可管理实例证书

## 进入管理页面

在产品主页中找到对应的实例， 点击“详情”按钮进入详情页面。

![](https://tidb-doc.cn-bj.ufileos.com/basic/instance.list.detail.button.1.png)

## 上传 SSL 证书

切换到 “证书管理” 面板

![](https://tidb-doc.cn-bj.ufileos.com/ssl/证书管理.png)

上传证书支持 USSL导入，本地上传和手动输入三种方式 

![](https://tidb-doc.cn-bj.ufileos.com/ssl/证书上传.png)

## 证书格式

UTiDB证书支持两种上传方式，第一种是本地上传证书文件，第二种是手动输入证书文本信息。

### 本地上传文件

如果您选择本地上传证书文件，那么需要准备好以下文件：

* 必选，网站的证书文件（cer/crt/pem格式），文件的文本格式如下：

```
-----BEGIN MY CERTIFICATE-----
...
-----END MY CERTIFICATE-----
```

* 必选，私钥文件（key文件）

数字签名算法为RSA的文件的文本格式如下：

```
-----BEGIN RSA PRIVATE KEY-----
... 
-----END RSA PRIVATE KEY-----
```

数字签名算法为ECDSA的文件的文本格式如下，EC PARAMETERS为可选：

```
-----BEGIN EC PARAMETERS-----
... 
-----END EC PARAMETERS-----
-----BEGIN EC PRIVATE KEY-----
... 
-----END EC PRIVATE KEY-----
```

* 可选，中间证书、根证书（证书链，cer/crt/pem格式），文件的文本格式如下：

```
-----BEGIN CERTIFICATE-----
...
-----END CERTIFICATE-----
-----BEGIN CERTIFICATE-----
...
-----END CERTIFICATE-----
```

您提供的证书需要去除口令保护。您在上传证书或手动填写证书时，请确保证书格式正确，如果校验格式错误，则会添加证书不成功。

### 手动输入证书

如果您选择手动输入证书，则文本需要依次包含以下字段：私钥、网站证书、中间证书、根证书等。

数字签名算法为RSA格式参考如下（在复制时请核对证书的完整性）：

```
-----BEGIN RSA PRIVATE KEY-----
... 
-----END RSA PRIVATE KEY-----
-----BEGIN MY CERTIFICATE-----
...
-----END MY CERTIFICATE-----
-----BEGIN MY CERTIFICATE-----
...
-----END MY CERTIFICATE-----
```

数字签名算法为ECDSA格式参考如下（在复制时请核对证书的完整性）：

```
-----BEGIN EC PRIVATE KEY-----
... 
-----END EC PRIVATE KEY-----
-----BEGIN MY CERTIFICATE-----
...
-----END MY CERTIFICATE-----
-----BEGIN MY CERTIFICATE-----
...
-----END MY CERTIFICATE-----
```

若您的证书为其他格式，建议您使用openssl工具进行格式转换。

DER转PEM：

证书转化：openssl x509 -inform der -in certificate.cer -out certificate.pem 

私钥转化（RSA证书）：openssl rsa -inform DER -outform PEM -in privatekey.der -out privatekey.pem

私钥转化（ECDSA证书）：openssl ec -inform DER -outform PEM -in privatekey.der -out privatekey.pem

## 开启 SSL 配置

证书上传后可在列表操作列开启SSL证书配置，默认开启所有用户SSL认证，新连接生效

![](https://tidb-doc.cn-bj.ufileos.com/ssl/证书使用.png)

开启SSL证书配置后，可在证书列表中查看当前使用证书
![](https://tidb-doc.cn-bj.ufileos.com/ssl/使用中证书查询.png)



## 关闭 SSL 配置

关闭SSL证书配置，新连接生效

![](https://tidb-doc.cn-bj.ufileos.com/ssl/停止使用证书.png)


## 删除 SSL 证书

删除SSL证书仅支持未使用证书，使用中证书须先关闭使用或切换证书使用后方可删除

![](https://tidb-doc.cn-bj.ufileos.com/ssl/删除证书.png)

## 查看证书详情

USSL导入证书查看详情会很跳转USSL详情

![](https://tidb-doc.cn-bj.ufileos.com/ssl/ussl证书详情.png)

本地上传和手动输入证书可直接查看证书内容

![](https://tidb-doc.cn-bj.ufileos.com/ssl/UTiDB证书详情.png)
# Wormhole 协议

| [English](./WORMHOLE.md) | [한국어](./WORMHOLE_KR.md) | [中文(繁体)](./WORMHOLE_ZH.md) | [中文(简体)](./WORMHOLE_CN.md) |

本教程将指导如何通过 Bitcoin Cash 的 Wormhole 协议创建一个众筹

## Wormhole 协议的规范

利用`Wormholed-cli`与虫洞协议进行交互

下载: [Wormhole 客户端](https://github.com/copernet/wormhole)

#### 获取 WHC 用于 Wormhole 协议

您必须使用BCH来获得WHC，汇率为1 BCH：100 WHC。
将您的BCH发送到以下地址以获得WHC：

网络     | 地址                                        |                              |
--------|---------------------------------------------|------------------------------|
主网     | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqu08dsyxz98whc  | 1000块确认后，WHC将转移到您的钱包地址|
测试网   | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqdmwgvnjkt8whc  | 3块确认后，WHC将转移到您的钱包地址 address|

## Wormhole 命令

#### 获取 WHC
通过`Wormholed-cli`来获得WHC
```
Wormholed-cli whc_burnbchgetwhc 1 ""
```

#### Token Transfer
转移WHC的方法
```
Wormholed-cli whc_send fromaddress toaddress propertyid amount (redeemaddress) (referenceamount)
```

#### Airdop Token
将对等数量Token发送到空投地址
```
Wormholed-cli whc_sendsto fromaddress propertyid amount redeemaddress distributionproperty
```

#### Transfer All Token
将所有Token从`fromaddress`转移到`toaddress`
```
Wormholed-cli whc_sendall fromaddress toaddress ecosystem (redeemaddress) (referenceamount)
```

#### Create Token
创建具有一定数量的Token
```
Wormholed-cli whc_sendissuancefixed fromaddress ecosystem type previousid category subcategory name url data amount
```

#### Create Crowdsale
用`Wormhole-cli`创建crowdsale，`fromaddress`将有令牌
```
Wormholed-cli whc_sendissuancecrowdsale fromaddress ecosystem type previousid category subcategory name url data propertyiddesired Tokensperunit deadline earlybonus issuerpercentage
```

#### Partipant Crowdsale
透过`Wormhole-cli`参与指定的众筹交易
```
Wormholed-cli whc_particrowsale fromaddress toaddress amount (redeemaddress) (referenceamount)
```

#### Close Crowdsale
众筹的所有者可以透过命令关闭它
```
Wormholed-cli whc_sendissuancemanaged fromaddress ecosystem type previousid category subcategory name url data
```

#### Grant Token
该命令可以将Token授予`toaddress`
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### Destroy Token
此命令可以销毁Token
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### Transfer Ownership
将所有权转移到指定的`toaddress`
```
Wormholed-cli whc_sendchangeissuer fromaddress toaddress propertyid
```

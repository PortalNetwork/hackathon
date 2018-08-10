# 웜홀 프로토콜

| [English](./WORMHOLE.md) | 한국어 | [中文(繁体)](./WORMHOLE_ZH.md) | [中文(简体)](./WORMHOLE_CN.md) |

이 문서는 비트코인 캐시에서 웜홀 프로토콜을 통해 클라우드세일을 실행하는 가이드다.

## 웜홀 프로토콜 사양

웜홀 프로토콜과 상호 작용하기 위해 Wormholed-cli를 사용합니다.

다운로드: [웜홀 클라이언트](https://github.com/copernet/wormhole)

#### 웜홀 프로토콜에 WHC 활용

WHC를 받으려면 BCH를 사용해야하며 1 BCH당 100 WHC를 받을 수 있습니다.
아래 주소로 BCH를 보내서 WHC를 받으세요.

Network | Address |        
--------|---------------------------------------------|------------------------------  
메인넷 | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqu08dsyxz98whc  | 1,000 블록 확인 후 지갑에 WHC를 확인할 수가 있다.
테스트넷 | qqqqqqqqqqqqqqqqqqqqqqqqqqqqqdmwgvnjkt8whc  | 3 블록 확인 후 지갑에 WHC를 확인할 수가 있다.

## 웜홀 명령어

#### WHC 받기
`Wormholed-cli` 통해 WHC 받기
```
Wormholed-cli whc_burnbchgetwhc 1 ""
```

#### 토큰 전송
WHC 전송 방법
```
Wormholed-cli whc_send fromaddress toaddress propertyid amount (redeemaddress) (referenceamount)
```

#### 에어드롭 토큰
에어드롭 주소로 토큰 보내기
```
Wormholed-cli whc_sendsto fromaddress propertyid amount redeemaddress distributionproperty
```

#### 참가자 클라우드 세일
`Wormhole-cli` 통해 참가자 클라우드 세일
```
Wormholed-cli whc_particrowsale fromaddress toaddress amount (redeemaddress) (referenceamount)
```

#### 모든 토큰 전송
`fromaddress` 에서 `toaddress` 로 모든 토큰 전송하기
```
Wormholed-cli whc_sendall fromaddress toaddress ecosystem (redeemaddress) (referenceamount)
```

#### 토큰 생성
특정 금액 토큰 생성하기
```
Wormholed-cli whc_sendissuancefixed fromaddress ecosystem type previousid category subcategory name url data amount
```

#### 클라우드 세일 생성하기
웜홀로 클라우드 세일 생성하기. `fromaddress` 에는 토큰 보유.
```
Wormholed-cli whc_sendissuancecrowdsale fromaddress ecosystem type previousid category subcategory name url data propertyiddesired Tokensperunit deadline earlybonus issuerpercentage
```

#### 클라우드 세일 마감
클라우드 세일의 소유자는 무슨 이유로든 클라우드 세일을 마감할 수 있다
```
Wormholed-cli whc_sendissuancemanaged fromaddress ecosystem type previousid category subcategory name url data
```

#### 토큰 부여
이 명령으로 토큰을`toaddress`에 부여 하기
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### 토큰 삭제
이 명령으로 토큰을 삭제 하기
```
Wormholed-cli whc_sendgrant fromaddress toaddress propertyid amount ("data")
```

#### 소유권 양도
특정 `주소`로 소유권 양도
```
Wormholed-cli whc_sendchangeissuer fromaddress toaddress propertyid
```

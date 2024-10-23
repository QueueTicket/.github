# QueueTicket
![image](https://github.com/user-attachments/assets/3902588e-8875-47c1-a1aa-b1e126276ce5)


### DNS(gateway)
* http://qticket-gateway-alb-855210072.ap-northeast-2.elb.amazonaws.com:19091
<br> <br/>
## 📘 프로젝트 개요
#### 🚚 [프로젝트 노션 바로가기](https://www.notion.so/fffe2b2fe1ba80f38452c705639f1dcc?pvs=4)
### 프로젝트 소개
* 실시간 공연 좌석 예매 서비스입니다. 분산 환경에서 확장성을 고려하여 구성 되었기에 대규모 트래픽과 동시성 문제에도 안정적인 서비스를 제공합니다.

### 프로젝트 목표
> 대규모 트래픽 대응
* 대기열 시스템을 이용해 동시에 몰리는 대규모 트래픽을 안정적으로 처리

> 쿠폰 발급
* Redis를 통해 쿠폰 발급 시 동시성 문제 처리
* Kafka를 통해 쿠폰 발급 비동기 처리

> 좌석 선택
* Redis를 통해 좌석 선택 시 동서싱 문제 처리

> 결제 및 정산
* 결제 시 사용자에게 맞게 최적의 쿠폰을 사용해 결제 시스템 구축
* 정산 시스템을 이용해 판매자의 편의성 제공

### 👨‍👩‍👧‍👦 Our Team

|                 박기도                   |                 박상훈                   |                전민기                 |                 전민기                 | 
| :------------------------------------: | :------------------------------------: | :----------------------------------: | :----------------------------------: | 
| [@shoon95](https://github.com/shoon95) | [@shoon95](https://github.com/shoon95)  | [@InHees](https://github.com/InHeeS) | [@InHees](https://github.com/InHeeS) |
|                   BE                   |                   BE                   |                  BE                  |                   BE                 |



## 🗺️ 인프라 설계도
![image](https://github.com/user-attachments/assets/ee10be02-f70c-4548-aec3-d1204d443b65)

## 🪄 주요 기능
> 쿠폰 발급 및 적용
- Redis를 통해 Lock 없이 동시성 제어
- Kafka를 통한 비동기 쿠폰 발급
- 레지스트리 패턴을 통해 확장성을 고려한 쿠폰 도메인 설계

> 대기열
- webfulx를 이용한 비동기 대기열 처리
- kafka, redis를 이용해 트래픽 분산
- msa gateway 로드밸런서를 통한 트래픽 분산
- Spring scheduler를 이용한 대기열 처리

> 좌석 선점
- Redis를 활용한 좌석 선점

> 결제 및 정산
- Toss Payments sandbox 환경에서 webFulx를 이용한 비동기 기반 결제 승인
- 결제 승인 실패 시, 지수 Backoff와 Jitter를 이용한 비패턴화 기반 결제 재 시도
- Transaction Outbox Pattern과 Kafka Transaction을 이용한 트랜잭션 기반의 이벤트 처리

> 공연 / 공연장 관리
- DDD에 입각한 도메인 관리
- 좌석 조회나 삭제 등 필요한 부분에서 트레이드 오프를 고려한 설계
- 엘라스틱 스택을 이용한 로그 관리

> CICD + 모니터링
- ithub Action을 활용한 CICD 구축
- Docker 를 사용하여 Container 이미지 관리
- AWS Fargate 를 통하여 스프링 서비스 배포
- AWS EC2 를 통하여 Util 서버 배포(kafka, redis 등)
- AWS Lambda + AWS SNS + Slack API 연동하여 모니터링 시스템 구축

## 💬 기술적 의사결정
### [대용량 트래픽에서 동시성 문제를 고려한 선착순 쿠폰 발급 처리](https://fir-turkey-016.notion.site/128e2b2fe1ba81238bedfde1725b1323?pvs=4)
> Redis(동시성) + Kafka(비동기 대용량 트래픽 처리)를 활용하여 문제 해결
### [Kafka와 Redis Sort set을 이용한 대기열 구현](https://fir-turkey-016.notion.site/Kafka-Redis-Sort-set-128e2b2fe1ba8195bb6bd5296b8c1a54?pvs=4)
> kafka(트래픽 분산처리) + Redis(sorted set) 을 통한 대기열 순서 관리 맟 실시간 순위 조회

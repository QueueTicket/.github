# QueueTicket
![image](https://github.com/user-attachments/assets/3902588e-8875-47c1-a1aa-b1e126276ce5)


### DNS(gateway)
* http://qticket-gateway-alb-855210072.ap-northeast-2.elb.amazonaws.com:19091
<br> <br/>
## 💡 기술 스택

- ![Java](https://img.shields.io/badge/Java17-%23ED8B00.svg?style=square&logo=openjdk&logoColor=white) <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=square&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/Spring Security-6DB33F?style=square&logo=Spring Security&logoColor=white"> ![Spring Data JPA](https://img.shields.io/badge/Spring%20Data%20JPA-6DB33F?style=square&logo=Spring&logoColor=white) ![Spring Gateway](https://img.shields.io/badge/Spring%20Gateway-6DB33F?style=square&logo=Spring&logoColor=white) <br>
![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-6DB33F?style=square&logo=Spring&logoColor=white) ![Eureka](https://img.shields.io/badge/Eureka-6DB33F?style=square&logo=Spring&logoColor=white)  ![JWT](https://img.shields.io/badge/JWT-black?style=square&logo=JSON%20web%20tokens) ![Gradle](https://img.shields.io/badge/Gradle-02303A.svg?style=square&logo=Gradle&logoColor=white)
- ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1.svg?style=square&logo=PostgreSQL&logoColor=white) ![Rds](https://img.shields.io/badge/AWS%20RDS-527fff.svg?style=square&logo=amazonrds&logoColor=white)
- <img src="https://img.shields.io/badge/Docker-%230db7ed.svg?style=square&logo=docker&logoColor=white"> 	![AWS-Lambda](https://img.shields.io/badge/AWS%20Lambda-FF9900.svg?style=square&logo=awslambda&logoColor=white) ![AWS-fargate](https://img.shields.io/badge/AWS%20Fargate-FF9900.svg?style=square&logo=awsfargate&logoColor=white) ![AWS-ec2](https://img.shields.io/badge/AWS%20EC2-FF9900.svg?style=square&logo=amazonec2&logoColor=white) ![AWS ALB](https://img.shields.io/badge/AWS%20ALB-8c4fff.svg?style=square&logo=awselasticloadbalancing&logoColor=white) ![AWS Action](https://img.shields.io/badge/Git%20Action-2088ff.svg?style=square&logo=githubactions&logoColor=white)
- ![GitHub](https://img.shields.io/badge/Github-%23121011.svg?style=square&logo=github&logoColor=white) ![Slack](https://img.shields.io/badge/Slack-4A154B?style=square&logo=slack&logoColor=white) ![IntelliJ IDEA](https://img.shields.io/badge/IntelliJ%20IDEA-000000.svg?style=square&logo=intellij-idea&logoColor=white) ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=square&logo=postman&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-%23000000.svg?style=square&logo=notion&logoColor=white)
- ![Zipkin](https://img.shields.io/badge/Zipkin-black?style=square&logo=Zipkin&logoColor=white) ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=square&logo=Prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=square&logo=Grafana&logoColor=white) ![AWS-cloudwatch](https://img.shields.io/badge/AWS%20CloudWatch-FF4f8b.svg?style=square&logo=amazoncloudwatch&logoColor=white) ![AWS-sns](https://img.shields.io/badge/AWS%20SNS-FF4f8b.svg?style=square&logo=amazonsimpleemailservice&logoColor=white) ![Elastic Cloud](https://img.shields.io/badge/Elastic%20Cloud-005571.svg?style=square&logo=elasticcloud&logoColor=white) ![Kibana](https://img.shields.io/badge/Kibana-005571.svg?style=square&logo=kibana&logoColor=white)

  
<br> <br/>
## 📘 프로젝트 개요
#### 🚚 [프로젝트 노션 바로가기](https://www.notion.so/fffe2b2fe1ba80f38452c705639f1dcc?pvs=4)
### 프로젝트 소개
* 실시간 공연 좌석 예매 서비스입니다. 분산 환경에서 확장성을 고려하여 구성 되어 대규모 트래픽과 동시성 문제에도 안정적인 서비스를 제공합니다.

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
> kafka(트래픽 분산처리) + Redis(sorted set) 을 통한 대기열 순서 관리 및 실시간 순위 조회
### [엘라스틱 스택 활용 로그 추적/관리](https://fir-turkey-016.notion.site/128e2b2fe1ba818898a4e6a3e5fba80c?pvs=4)
> 리소스 최적화를 위해 Filbeat를 통한 로그 관리
### [Eureka 사용 시 Eureka Client 등록 방식](https://fir-turkey-016.notion.site/Eureka-Eureka-Client-128e2b2fe1ba80e49345d46c4f152725?pvs=4)
> Ip 기반 통신을 사용한 Eureka Client 관리
### [Transactional Outbox Pattern을 이용한 결제 완료 메시지 발행](https://fir-turkey-016.notion.site/Transactional-Outbox-Pattern-128e2b2fe1ba801fbe99c4e0577f1873?pvs=4)
> Transactional Outbox 패턴을 적용해 결제 테이블 갱신 트랜잭션 완료와 메시지 발행 간의 데이터 일관성 문제 해결

## 🚨 트러블슈팅
### [대기열 시스템 부하 테스트](https://fir-turkey-016.notion.site/128e2b2fe1ba80bb8e0ae7fd343e213f?pvs=4)
> 대기열 시스템을 적용하기 전과 후 비교시 응답 시간 기준 5배 성능 향상
### [벌크 쿼리](https://fir-turkey-016.notion.site/128e2b2fe1ba80a99b71fa6575a8241d?pvs=4)
> N+1의 쿼리가 발생하는 상황에서 쿼리 성능 개선을 위해 영속성 컨텍스트를 거치지 않는 벌크 쿼리 도입
### [비동기 요청 시 AuditorAware 문제](https://fir-turkey-016.notion.site/AuditorAware-128e2b2fe1ba807cbb17d61724ce592c?pvs=4)
> 비동기 요청 시 HttpServletRequest 객체 활용 불가 문제를 ThreadLocal과 AOP를 통해 효과적으로 해결
### [AWS Fargate에서 Eureka 사용 시 Eureka Client의 Ip 추적 실패 문제](https://fir-turkey-016.notion.site/AWS-Fargate-Eureka-Eureka-client-ip-128e2b2fe1ba80e2b8aded6d1084df67?pvs=4)
> Eureka Client의 등록 IP를 확인 후 직접 Container의 IP를 Eureka에 등록하여 Eureka가 정상적으로 Client의 IP를 호출할 수 있도록 구현

## ERD
![image](https://github.com/user-attachments/assets/02c06a8b-cbc8-4d03-85f0-12fe3334306c)

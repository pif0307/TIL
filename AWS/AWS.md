# AWS(Amazon Web Service)

> 아마존 웹 서비스(Amazon Web Services; AWS)는 아마존닷컴의 클라우드 컴퓨팅 사업부이다.

## 1. 용어
 - `온프레미스(on-premise)`: 데이터센터나 서버실에 서버를 직접 관리하는 방식
 - `클라우드(Cloud)`: 필요한 리소스들을 인터넷을 통해 제공받아 사용한 만큼 비용을 지불하는 방식 (AWS, Azure 등)
 - `Region`: 복수개의 데이터센터의 독립적인 물리적 위치
 - `AZ(Availability Zones)`: 하나의 Region 내에 공간적으로 분리된 전원을 말하며 물리적 보안, 백업 역할을 하는 안전 장치로 운영되는 데이터 센터
 - `EC2(Elastic Compute Cloud)`: 가상 서버(독립된 하나의 컴퓨터를 임대해주는 것)
 - `Instance`: aws에서 제공하는 하나의 컴퓨터 단위

## 2. 클라우드 컴퓨팅
### `IaaS(Infrastructure as a Service)`
 - AWS, 네이버플랫폼 과 같은 인프라스트럭쳐를 제공하는 서비스.

 - 가상 서버 또는 스토리지, 가상 네트워크 등의 리소스를 서비스 형태로 제공한다.

 - 사용자는 물리적인 하드웨어를 직접 관리할 필요가 없으며, 직접적으로 서비스 이용을 통해 컴퓨터 리소스를 사용 할 수 있다. (AWS, 마이크로소프트(MS) 애저, IBM 소프트레이어 등의 업체들이 있다.)

 - 클라우드 IT의 기본 구성 요소 (네트워킹, 컴퓨터, 데이터 스토리지 공간)

### `PaaS(Platform as a Service)`

 - DB 또는 Application 서버 등의 이미 미들웨어를 제공한다.

 - 하드웨어/OS/미들웨어 에 대한 관리는 서비스 제공자가 하며, 사용자는 제공된 미들웨어만 사용 할 수 있다.

 - 주로 개발 환경과 관련한 서비스를 제공한다.(OS, DB, WAS, JDK)

 - 기본 인프라 (ex. 하드웨어와 운영 체제)를 관리할 필요 없이 애플리케이션을 실행할 수 있게 해준다.

### `SaaS(Software as a Service)`

 - 소프트웨어 또는 애플리케이션의 기능만 제공합니다. 네이버클라우드, 웹 메일, ERP 등과 같은 형태의 서비스를 사용자에게 제공한다.

## 3. EC2 (Amazon Elastic Compute Cloud)
 - 크기조정 가능한 컴퓨팅 파워 (가상인스턴스의 크기가 고정X)

 - 컴퓨팅 리소스 완전제어 (인스턴스는 고객이 관리, 제어성을 고객에게 제공)

 - 새로운 서버 인스턴스 확보 및 부팅 시간을 단축

 - 실제로 사용한 용량만큼만 지불

 - 컴퓨팅 요구사항의 변화에 따라 컴퓨팅 파워를 조정가능

 - Linux 또는 Windows 선택 가능 (2개의 OS만 지원한다고 한다)

 - 안정성을 위해 여러 AWS 리전과 가용 영역에 걸쳐 배포

# 참고 문헌
 - [AWS 기초 용어 및 개념](https://easy-h.tistory.com/16)
 - [AWS 기초 (공식 문서)](https://aws.amazon.com/ko/getting-started/fundamentals-core-concepts/)
 - [갓대희의 작은공간](https://goddaehee.tistory.com/174)
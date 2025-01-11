## Backend

1. 클라우드 -aws
2. docker + react native + 플랫폼/ 서비스
3. 데이터 분석 및 ml   
5. spring framework
6. db, 네트워크, 보안 x 
7. node js 등 다양한 framework을 이용한 백엔드 개발
8. 서비스를 기획부터 배포까지 전과정에 참여
9. rest api
    


## Docker

**Docker란? **

컨테이너화 기술을 사용하여 앱을 개발, 배포할 수 있게 해주는 오픈소스 플랫폼 (컨테이너화 = 앱과 그 종속성을 컨테이너에 패키징하는 과정)

-> 앱이 실행되는 환경에 제한받지 않고 일관되게 실행됨. (어느 환경에서나 동일하게 실행됨.)

[일관성, 호환성 ↑]

1. 이미지
-> 이미지는 앱, 실행에 필요한 파일 시스템과 라이브러리를 포함한 템플릿

2. 컨테이너
-> 이미지를 실행한 인스턴스

Docker Hub = 도커의 중앙화된 리포지터리 (다른 이미지들이 있어 이를 사용할 수 있음.)

***CI( 지속적 통합)/CD (지속적 배포) 의 프로세스를 간소화하고 자동화하는데 크게 기여함.***

<ins>* 소프트웨어 개발의 효율성과 안전성을 업그레이드 시킴으로서 더 빨리 시장에 출시될 수 있도록 함.</ins>

**Docker vs VM**
- Docker는 필요한 애플리케이션과 그 property만을 담고있어 가벼운 빠름 (시작 시간이 짧고 리소스 사용이 적음) (호스트 OS의 커널을 이용.)
- VM은 전체 게스트 운영체계를 담아 무겁고 리소스 사용이 많음. 하지만 더 강력한 격리와 보안

**Dockerfile**
-> 이미지를 생성해내는데 필요한 명령어들이 서술되어 있음 
- docker build를 통해 이미지가 생성되고 명령어들이 실행됨.

**Docker Composer**
- 도커 컨테이너를 실행하고 관리하기 위한 도구. 복잡한 애플리케이션을 <ins>간단한 명령어로 관리 가능.</ins>

**Docker Swarm vs Kubernetes**
-> 컨테이너 오케스트라 서비스 
- Swarm - 설정과 관리가 단순함.
- Kubernetes - 대규모 시스템을 위한 복잡한 배포, 스케일링, 관리 기능 (클러스터 관리, 자동화된 롤아웃/롤백 기능)
- 고급기능 과 더 높은 확장성.


- Docker는 운영체제 수준의 가상화 제공. 각 컨테이너는 호스트 os와 분리됨.
- 하지만 호스트 OS의 커널을 공유해 VM 수준의 완전한 격리는 아님.

**Docker 보안**
- 최소권한 원칙을 사용하여 컨테이너 실행하기
- 신뢰할 수 있는 소스에서 이미지 가져오기
- 정기적으로 이미지와 컨테이너를 업데이트해서 보안 취약점 해결
- 네트워크 분리같은 네트워크 보안 전략 실행
- 이미지의 취약점을 자주 검사하고 런타임에 대한 보안 기준을 세워 강화.

**Docker 파일 확장하는 방법**
- Docker compose에서 scale 명령어를 통해 실행할 수 있다. 
- Docker Swarm 이나 kubernetes의 오케스트라 서비스에서 자동화된 확장 서비스를 사용한다. (컨테이너의 인스턴스 수 조정)

**Docker 데이터 저장**
- 바인드 마운트 나 볼륨을 사용하면 컨테이너 외부에 영구적으로 데이터 저장 가능.


## DevOps

**DevOps** - 개발 방법론
- Development (개발)과 Operation (운영) 합쳐서 만든 말로, 개발-운영 과의 협업 프로세스를 자동화하는 것을 의미한다.
- 애플리케이션의 개발과 개선 속도를 크게 향상시킨다.

**CI/CD**
- continuous integration + continuous deployment을 합친 단어로, 앱 개발 단계를 자동화하는 과정입니다.
  ex) github으로 커밋하고 jenkis가 자동으로 빌드되도록 설계해본 경험.

- ***CI***: 개발자가 작성한 코드를 지속적으로 통합 & 테스트 -> 품질유지

  ex) github을 이용한 코드 버전 관리, main branch와 local branch을 분리하여 충돌 방지
  - postman을 이용한 api test (모듈간의 데이터 교환 테스트)
    
- ***CD***: 변경된 코드를 자동 배포. -> 개발, 테스트, 배포 과정이 통합되며 효율성 ↑ 신속성 ↑
  - ex) 1. Github Actions를 이용한 CI/CD 파이프라인 구축 (코드사항이 자동적으로 배포)
  - 백엔드와 프로트엔드를 docker image로 빌드하고 github container registry에 자동으로 푸시
  - main branch에 커밋된 코드가 새로운 docker image를 생성해 자동으로 업데이트.

    
  Docker file을 이용해 이미지 생성, 그리고 배포 
  - Digital Ocean을 이용해 자동으로 배포. 
 
  **DDD (Domain Driven Design)**
  - 도메인을 중심으로 하여 각 소프트웨어의 연관된 부분을 연결하여 점차 진화하는 개발 방안.

  **TDD (Test Driven Deployment)**
  - 테스트를 만든 후에 테스트를 통과하는 코드를 작성하고 상황에게 맞게 리팩토링하는 방식. (테스트 주도 개발 방식)
  - 레드/그린 사이클: 레드 - 실패하는 테스트를 먼저 작성, 그린 - 테스트를 통과하는 코드를 작성, 리팩토링 - 가독성 좋게 바꾸기

  **Monolithic Architecture vs Microservice Architecture**
  - Monolithic = 하나의 통합된 패키지로 개발하는 방식.
  - Microservice = 하나 하나 개별로 개발하며 확장하는 방식. (개별의 개발 방식) ->해당 부분만 수정, 확장 가능.


## Rest API

**REST**
- 프로트 엔드 및 외부 시스템과 통합할 수 있는 앱을 개발하는 아키텍쳐 스타일 (HTTP 프로토콜을 기반으로 함)

- **API** = 앱이 데이터를 교환하고 통신할 수 있도록 하는 프로그래밍 인터페이스

**Restful API**
- Rest 원칙을 따르는 API로, 모든 데이터를 URI(Uniform resource identifer) 로 처리


## Java

**Call by Value vs Call by Reference**

- Call by value = 값을 복사해서 저장하는 방식
- 장점: 원래의 값을 건드리지 않고 바꿀 수 있다.
- 단점: 값을 복사해서 받기 때문에 메모리에 부담이 된다.

- Call by Reference = 값의 주소를 받는 방식
- 장점: 복사하지 않기 때문에 빠르다.
- 단점: 값을 바꾸면 원래의 값도 바뀐다.

- **CORS**: HTTPS header를 사용하며 브라우저간에 허락을 구하고 거절하는 매커니즘.
- 브라우저에서 cross-origin 요청을 안전하게 할 수 있는 매커니즘.
- **cross origin**: 3개 中 1개라도 다른 경우
- protocol: http/ https 는 다른 프로토콜 사용.
- domain: 인터넷 주소 <-> IP
- port: 운영체제 통신의 종단점 (인터페이스)

**절차지향 vs 객체지향**
- 절차지향 = 데이터 중심으로 함수를 구현한다. (순차적으로..)
- 객체지향 = 기능을 중심으로 메서드를 구현한다.


컴파일 = java로 쓴 파일을 .class로 변환하는 과정 (byte code) [.java -> .class]


||compiler|interpreter|
|--|--|--|
|과정|한번에 코드를 기계어로 변환하고 실행|프로그램을 실행하는 동안 한줄씩 기계어로 변환하고 실행|
|장점|실행 속도가 빠르다|디버깅과 개발이 쉽다|
|단점|컴파일 시간이 소요된다|실행속도가 느리다|
|Example|C,C++,Java|Python,Ruby, Javascript|

**String vs String Buffer vs String builder**

- String = immutable 객체, 
- String Buffer = mutable 객체,
- String builder = mutable 객체, 

**parameter vs argument**
- parameter = 매개변수 -> 함수를 classify할때 사용되는 값이다 (인풋)
- argument = 인수 -> 함수를 호출시 전달되는 값이다 (인풋)
  

## Git

**버전 관리 시스템**
1. 클라이언트 - 서버 모델
   하나의 중앙서버엥 클라이언트가 데이터를 가져와 작업하고 다시 통합.

2. 분산 모델
   중앙 서버는 존재하지만 개발자들이 그 복사본을 가지고 작업하고 저장하는 형식.
   -> 중앙 모델이 사라져도 데이터 분실이 덜함.

- Git은 버전 관리를 위한 시스템이다. 
- 버전관리는 에러가 생겨 그이전 버전으로 복구해야 할때 필요하다. ( +이전 버전 기능 가져오기)
- 다른 개발자들과 협업을 할때 각자 맡은 파트를 개발하고 합치는 과정에서 원격 저장소의 역할을 한다.

**Git의 장점**
1. 개발자들과 협업할때 합치기 용이하다
2. 데이터 분실시 이전 버전 복구가 가능하다
3. 변동 과정을 체계적으로 관리할 수 있다

**Branch** = 개인의 독립적인 작업영역, 마음대로 소스코드를 변경할 수 있다. (코드를 분리하여 관리하는 개념.)

**f0rk** = 개인 리포지토리에 다른 리포지토리를 가져와서 쓰는 개념

#### Git 운영법
**Git Flow** = git의 브랜치들을 관리할 수 있는 기법
- production, hotfix, feature(develop, feature, release, hot fix, main)브랜치로 구성
- feature = 기능을 만들때 쓰는 브랜치 (*)
- develop  = 다음 출시버전을 개발하는 브랜치 (*)
- release = 이번 출시 버전을 준비하는 브랜치 (배포하기전에 master로 병합한다.)
- hotfix = 출시버전에서 생긴 버그를  관리하는 브랜치
- production = 모든 기능이 개발되면 프로덕션 브런치로 병합한다

**Git Merge**
1. fast forward 방식 - branch에 그대로 옮겨 가는 방식 (new <- master 병합)
2. non-fast forward - 새로운 버전을 만들어 병합한다.

**git reset** = 되돌리기 기법 (git add, commit 이후에 되돌리기)

*<ins>+ 로컬 저장소를 이전 상태로 강제로 되돌려 놓는다.</ins>*

-  reset soft = 변경이력은 삭제되지만 변경 내용은 남아있기에 commit을 하면 바로 올릴 수있다. (***stage 되어있다***)
-  reset hard = 돌아가려는 커밋 이후의 모든 내용은 삭제된다
-  reset mixed = 변경 이력은 삭제되지만 변경 내용은 남아있다. (add . -> commit -> 올리기)

**git revert** - 커밋 내용 되돌리기 (특정 커밋의 내용을 되돌린다)

**git stash** = 현재 작업 사항이 있어 git pull을 하기전 작업사항을 임시 저장해야할 때 사용한다.

**git config** = git의 환경설정을 도와준다

**git clone** = 기존에 있는 저장소를 복제해 새로운 git 저장소를 생성한다 (기존에 있는 원격 저장소를 불러들여 개발을 할 수 있다)

**GIT vs SVN**
- SVN = centralized version control, 중심 서버에 연결해 업로드 가능 (더 자주있는 변경과 업로드에 유리)
- GIT = 이전 버전들이 저장되며 협업에 유리

----

### Rest API
- 서버간의 통신은 Rest API로 동작. 

### 배포 자동화
- 수동 배포과정은 jar 파일로 빌드하고 EC2 배포 서버에 SSH 통신으로 직접 파일을 전달하고 필요한 패키지를 설치.
- Java -> AWS EC2 -> Docker -> Github Actions

### Deployment
- 배포 = 애플리케이션을 서버에 업로드하여 사용자가 접근할 수 있도록 하는 과정.

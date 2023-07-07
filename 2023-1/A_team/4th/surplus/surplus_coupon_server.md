# 이번 스프린트 목적
* 데이터 드리븐
* 스키마 설계
* 기본적인 CRUD에 사용할 DB, 개발 언어, 프레임워트 선정 (미완)
# 활동 일정
|날짜|활동 내역|
|---|---| 
|4월 1일| 데이터베이스 첫걸음 독서(1)
|4월 21일| 데이터베이스 첫 걸음 독서(2) > [ref](https://yongc.tistory.com/category/CS/DataBase)
|4월 30일|[#19 개발에 사용할 웹 개발 언어 선정(아직 진행중)] (https://github.com/couponApiServerEconovation/couponApiServerMtak/issues/19) [#18 개발에 사용할 library, framework 선정(아직 진행 중)](https://github.com/couponApiServerEconovation/couponApiServerMtak/issues/18) [#17 개발에 사용할 데이터베이스 선정(아직 진행 중)] (https://github.com/couponApiServerEconovation/couponApiServerMtak/issues/20)
|5월 6일|[#11 데이터 시퀀스 드리븐](https://github.com/couponApiServerEconovation/couponApiServerMtak/issues/11)
|5월 13일|[#7 테이블 설계(1)](https://github.com/couponApiServerEconovation/couponApiServerMtak/commit/a4e9e8ef445dfc8469b2bfca9e81959a7b515b97#diff-931b1900bef92ae8c491d69eb40219f4e5ab8e2f06702d762afc564627b46661)
|5월 20일|[#7 테이블 설계(2)](https://github.com/couponApiServerEconovation/couponApiServerMtak/commit/4b4ad59c28a22288412facb04978a16e6c513c01#diff-931b1900bef92ae8c491d69eb40219f4e5ab8e2f06702d762afc564627b46661)
# 활동 내역
## 데이터 시퀀스 드리븐
### 🙄그게 뭐죠?
기본적인 시퀀스 다이어그램을 작성했다면 각 연결선(메소드)에 필요한 데이터를 작성하는 단계이다.
### 😎왜 하는거죠?
실제로 DB에 저장되어야 하는 데이터와 프로세스 중간에 휘발되어야 하는 데이터를 구분하기 위해서!
### 기대 효과
1. 스키마 설계를 할 수 있다. 
2. 데이터 드리븐이 가능한 시퀀스인지 검증할 수 있다.
### 산출물
* [시퀀스 다이어그램](https://github.com/couponApiServerEconovation/couponApiServerMtak/commit/4b4ad59c28a22288412facb04978a16e6c513c01?short_path=931b190#diff-931b1900bef92ae8c491d69eb40219f4e5ab8e2f06702d762afc564627b46661)
### 느낀 점
사실 시퀀스를 그리면서 어느정도 매핑 데이터와 로그 데이터의 윤곽을 잡아놓았다. 하지만 데이터 시퀀스 드리븐을 하면서 운영 관점에서 필요한 데이터를 남기기 위해 데이터를 어떻게 드리븐할지 고민하게 되었다. 

## 스키마 설계
### 🙄그게 뭐죠?
데이터를 가공하고 조회하기 쉽게 잘 정리하는 과정이다.
정규화와 역정규화를 오고가는 단계이죠.
### 😎왜 하는거죠?
데이터가 잘 정리되어 있지 않아서 생기는 DB 참조 서비스 시퀀스의 성능 저하를 막고 효율적인 데이터 분석을 위해서죠!
### 기대 효과
* 초기 테이블이 나온다.
### 산출물
* [ERD](https://github.com/couponApiServerEconovation/couponApiServerMtak/commit/4b4ad59c28a22288412facb04978a16e6c513c01?short_path=931b190#diff-931b1900bef92ae8c491d69eb40219f4e5ab8e2f06702d762afc564627b46661)
### 느낀점
도메인 우선으로 테이블을 찢어야할지, 기능 우선으로 테이블을 찢어야할지 고민하는게 어려웠다.
확장 가능한 설계는 그 중간에 있는 것 같다.~~더 어렵다~~
### 흥미로운 이슈
(아직 정리가 덜되었습니다.)

### 놀라운(?) 발견
[mermaid도 ERD 를 지원한다...! (공식문서)](https://mermaid.js.org/syntax/entityRelationshipDiagram.html)
즉 ERD도 문서로 표현할 수 있기 때문에 버전 관리가 가능하다.

## 개발 환경 선정
### 🙄왜 하는거죠?
선택한 기술에 대해 이유를 설명할 수 있어야 한다. 
그리고 선택하지 않은 기술에 대해서도 그 이유를 설명할 수 있어야 한다.
이후 변경이 어려운 지점이기 때문에 러닝 커브 이외에 안정성이라던가, 생산성을 고려한 선택을 해야 한다.

### 기대 효과
* DB에 대해 기본적인 학습을 할 수 있다.
* 웹페이지 제작에 대한 다양하고 기본적인 기술들을 확인할 수 있다.

### 산출물(1차)
하루를 잡고 다음의 레퍼런스를 따라갈 예정이다.
#### framework
* [Django official doc](https://docs.djangoproject.com/en/4.2/intro/tutorial01/)
* Spring은 생략합니다.
* [Express official doc](https://expressjs.com/ko/starter/installing.html)
* [Laravel official doc](https://laravel.com/docs/10.x)
* [Ruby On Rails](https://guides.rubyonrails.org/getting_started.html#hello-rails-bang)
#### RDB
구조 위주의 차이만 간략하게 정리한다.
* MySQL
* PostgreSQL
* MariaDB
* Microsoft SQL Server
* Oracle Database
#### OOP
framework를 하면서 같이 정리한다.

### 느낀점
짧은 기간에 핵심을 맛볼 수 있는 튜토리얼들을 확보하는데 시간을 소요했다. 단순 사용 후기 조사나 훝어보기로 끝내지 않은 이유는, 내가 사용할 기술이 다른 프레임워크나 환경에서는 어떻게 제공이 되는지 확인하는 것이 필요하지 어떤 기술이 절대적으로 좋고 나쁨이 없기 때문이다.


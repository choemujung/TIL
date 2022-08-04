# 라이브러리 살펴보기
## 라이브러리 목록 보기
## 라이브러리가 많은 이유
분명 프로젝트 생성할 때 Spring Web, Thymeleaf 두개만 불러왔는데 왜이렇게 많은 라이브러리가 호출되어있을까? Gradle은 의존성 관리를 하는데 Spring Web, Thymeleaf가 의존하는 다른 라이브러리를 트리 형식으로 쫙 불러온다. 그래서 직접적으로 사용하지는 않지만 최종적으로 필요한 라이브러리는 상당히 늘어나게 된다.
## 각 라이브러리 간단 설명
### 스프링 부트 라이브러리
* spring-boot-starter-web
    * spring-boot-starter-tomcat: 톰캣(웹서버)  
    기존에는 톰캣을 따로 설치하고 자바 파일을 톰캣 환경에 밀어넣는 방식이었다. 하지만 지금은 라이브러리로 관리되고있어서 따로 설치할 필요가 없다.
    * spring-webmvc: 스프링 웹 MVC
* spring-boot-starter-thymeleaf: 타임리프 템플릿 엔진
* spring-boot-starter(공통): 스프링부트 + 스프링 코어 + 로깅
    * spring-boot
        * spring-core
    * spring-boot-starter-logging
        * logback, slf4j - 두개 조합이 스프링 표준
### 테스트 라이브러리
* spring-boot-starter-test
    * junit - 테스트 프레임워크 중 메인
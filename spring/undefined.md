---
description: Chapter 1 && Chapter 2
---

# 스프링 부트

## 스프링 부트의 세 가지 핵심 기능

* 의존성 관리 간소화&#x20;
* 배포 간소화
* 자동 설정

#### 의존성 관리 간소화 - 스타터

* 스프링 부트의 특별한 점은 의존성을 수월하게 관리한다는 점
* 일반적으로 애플리케이션에서 제공하는 모든 기능에는 여러 기본 의존성이 필요
* 심지어 한 특정 버전의 의존성은 다른 의존성의 어떤 특정버전에서만 테스트 되었을 가능성이 있음
* 특정 버전들에서만 테스트된 의존성을 함께 사용할 때 문제가 발생하면, 의존성 꼬임(Dependency Whack-a-Mole) 이 발생
* 스프링 부트와 스타터는 이런 어려움을 해결하기 위해 등장
* 스프링 부트 스타터는 거의 매번 동일한 방식으로 특정 기능을 제공한다는 입증된 전제를 바탕으로 제작된 BOM(Bills of Materials)
* BOM이란, 프로젝트 아티팩트의 정보, 버전과 의존성 관리를 포함한 특수한 POM(빌드 도구에서 의존성을 가져오고 프로젝트 빌드에 사용하는 정보와 프로젝트 구성이 담긴 파일)
* spring-boot-starter-web 같은 단일 스타터를 추가하면, 단일 애플리케이션에 필요한 기능을 모두 제공
* 전반적으로 스프링 부트의 스타터 개념은 의존성을 간소화하고, 애플리케이션에 기능 전체를 추가하는 데 필요한 작업을 줄여주고, 테스트/유지보수/업그레이드에 드는 오버헤드를 크게 줄임

#### 배포 간소화 - 실행 가능한 JAR

* 번거로운 배포 프로세서의 많은 부분을 한 단계로 간소화
* 모든 의존성이 포함된 단일 스프링 부트 JAR은 배포를 용이하게 함
* 모든 의존성을 수집해 배포하는 대신 스프링 부트 플러그인이 모든 의존성을 결과 JAR(output jar)에 압축
* 또한, 빌드 파일에 단일 속성을 설정하면 스프링 부트 빌드 플러그인은 단일 JAR를 완전히 자체적으로 실행 가능한 파일로 만듬

#### 자동 설정 - 스프링 부트의 마법

* 스프링 개발자의 생산성을 향상시키는 가장 강력한 도구

#### 정리

* 프로젝트 생성부터 개발과 유지보수에 용이한 의존성 관리 간소화
* 작업하려는 도메인의 보일러플레이트 코드(boilerplate)를 극적으로 줄이거나 없애주는 자동 설정
* 패키징과 배포를 간편하게 만들어주는 배포 간소화

## 메이븐 vs 그레이들

#### 메이븐

* 빌드 자동화 시스템을 위한 대중적이고 확실한 선택
* 선언형 접근법은 다른 빌드 도구보다 개념이 더 간단
* 컨벤션에 따라 특정한 프로젝트 구조를 생성
* 즉, 메이븐이 만든 프로젝트 구조를 그대로 사용하지 않으면 메이븐을 쓰는 것이 오히려 역효과

#### 그레이들

* JVM 프로젝트를 빌드할 때 널리 사용되는 옵션
* DSL(도메인 특화 언어)로, 최소한의 코드로 유연한 빌드 파일을 생성(build.gradle)
* 변경 사항이 없는 경우 자바 컴파일을 하지 않는 점
* 또한 대규모 프로젝트에서 메이븐보다 훨씩 빠름
* 하지만, 그레이들의 유연함 때문에 프로젝트가 예상대로 동작하지 않을 때 빌드 과정을 수정하고 문제를 해결하는데 시간이 걸림

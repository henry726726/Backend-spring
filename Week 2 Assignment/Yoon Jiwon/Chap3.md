### 3장 스프링 부트 3 구조 이해하기

# 3.1 스프링 부트 3 구조 살펴보기
- 각 계층이 양 옆의 계층과 통신, 필요에 따라 소통-> 프레젠테이션 / 비즈니스 / 퍼시스턴스
- 프레젠테이션 계층: HTTP 요청 받고 비즈니스 계층으로 요청 전송 (컨트롤러)
- 비즈니스 계층: 모든 비즈니스 로직 처리 (서비스)
- 퍼시스턴스 계층: 모든 데이터베이스 관련 로직, DAO 객체 (리포지토리)
- 계층: 개념의 영역 // 실제 구현 영역 -> 컨트롤러, 서비스, 리포지토리

**실제 디렉토리 구성**
- main: 실제 소스 코드, 리소스 파일
    java + resources / templates / static
- test: 프로젝트의 소스 코드 테스트 목적의 코드나 리소스 파일
- build.gradle: 빌드 설정 파일(의존성, 플러그인 설정 등)
- settings.gradle: 빌드할 프로젝트 정보 설정

# 3.3 스프링 부트 요청-응답 과정 한 방에 이해하기
- 포스트맨에서 톰캣에 /test GET 요청 -> 스프링 컨테이너로 이동
- 스프링 부트의 디스패처 서블릿이 URL 분석 후 처리 가능한 컨트롤러 찾음 -> 요청 전달
- 요청 처리할 수 있는 메소드에 요청이 매치됨 -> 비즈니스 계층과 퍼시스턴스 계층을 통해 필요 데이터 가져옴
- 뷰 리졸버가 템플릿 엔진을 통해 데이터 생성
- 결과 return 후 포스트맨에서 확인 가능

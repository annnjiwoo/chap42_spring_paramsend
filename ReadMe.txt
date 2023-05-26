[chap15_spring_04_paramsend 특이사항]

[1] 특징
 1. 정상적인 스프링 프로젝트 시작!
 2. 컨트롤러의 등장 : 컨트롤러 문법 설명
 3. web.xml의 역할과 실행 순서 설명
 4. 빈등록 파일(스프링 컨테이너 환경 설정파일)이 WEB-INF/spring 아래에 위치함.
 5. 스프링 프로젝트로 파라미터 전달하는 방법
 
 [구체적인 실행 순서]
 1. 새 프로젝트 생성후 Build Path 설정 및 pom.xml 설정 
 2. web.xml 변경
  - 기본으로 제공해주는 코드에 인코딩 필터, jsp 직접 접근 불가 기능 추가
  -  
 2. HomeController 파일의 패키지를 com.javalab.spring.controller 변경
  - com.javalab.spring.vo 패키지 생성하고 그 안에 MemberVo 생성
 
 4. servlet-context.xml 변경
  <context:component-scan base-package="com.javalab.spring.controller" />
  
 5. 실행해서 파라미터가 정상적으로 전달되고 받아오는지 확인후 다음 단계로 진행
  - 일반 요청은 화면이 깜빡 거림
  
 6. 서블릿 프로젝트에서는 각각의 서블릿이 사용자의 요청을 처리했다.
  - 스프링에서는 사용자의 모든 요청을 "디스패처서블릿"이라고 하는 객체가 처리함.
  - 디스패처서블릿의 소스코드를 분석할 필요는 없지만 구체적으로 어떻게 작동하는지
       알아야 함.
       
  1) 스프링에서는 컨트롤러라는 클래스에 메소드를 만들고 그 메소드가 요청을 처리함.
         즉, 메소드 하나가 서블릿 한 개와 같은 역할을 함.
  2) 디스패처 서블릿은 요청된 url을 처리할 핸들러(메소드) 정보를 갖고 있는 HandlerMapping
         을 통해서 처리기(핸들러 메소드)를 알아낸다.
  
 7. 어플리케이션 실행후 로그에서 RequestMappingHandlerMapping 통해서
  - url과 핸들러가 매핑되는 로그 설명필요.(이미 설명 완료)
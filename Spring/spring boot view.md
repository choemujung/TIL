# 뷰 만들기
## Welcome Page
웰컴페이지는 도메인(localhost:8080)으로 접속하면 나오는 페이지다. ***src\main\resources\static*** 이 위치에 ***index.html***파일을 만들면 스프링이 알아서 인식한다.
## thymleaf
타임리프를 이용해 동적 페이지를 생성할 수 있다. 대략적인 방법은  
1. 컨트롤러를 만든다. 
2. url 맵핑한다.
3. 보여줄 페이지 이름을 String type으로 리턴한다. 
4. html 파일을 resources/templates/에 위치시킨다.  

```java
@Controller //"이 클래스는 컨트롤러다"라고 말하는중
public class HelloController {
    @GetMapping("hello") // 'localhost/8080/hello 접속하면 이거 실행하겠음'이라고 말하는중
    public String hello(Model model) { 
        model.addAttribute("name", "홍길동"); //key - value
        return "hello"; //hello.html 띄워줌
    }
}
```

***resources/templates/hello.html***
```html
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Hello</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
<p th:text="'안녕하세요 제 이름은 ' +  ${name} + '입니다.'" ></p>
</body>
</html>
```
model은 데이터 담고있는 통? 자세한건 아직 모름..ㅎㅎ  
hello.html 파일에서 name을 사용하면 홍길동 써짐. name을 청길동으로 바꾸면 청길동 뜸. 한마디로 html에서 변수 사용하는 거임.

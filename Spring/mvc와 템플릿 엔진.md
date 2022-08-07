# MVC와 템플릿 엔진
MVC: Model, View, Controller
## 템플릿 엔진
서버에서 html파일을 동적으로 만들어서 클라이언트에 응답한다.  

```java
    @GetMapping("hello-mvc")
    public String helloMvc(@RequestParam("name") String name,
                           Model model) {
        model.addAttribute("name", name);
        return "hello-template";
    }
```
name을 http 요청할 때 파라미터로 받는 코드. ***localhost:8080/hello-mvc?name="홍길동"***

```html
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Hello</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
<p th:text="'안녕하세요 제 이름은 ' +  ${name} + '입니다.'" >이 부분은 파일로 열었을 때 표출</p>
</body>
</html>
```
타임리프에서 태그 안에 있는 컨텐츠는 서버 없이 파일만 열었을 때 표출. 없어도 되는데 마크업 작업 할때 종종 쓰임.

http 요청을 보내면 먼저 컨트롤러를 확인함. 컨트롤러에서 매핑하지 않으면 static으로 가서 정적 페이지를 찾음.
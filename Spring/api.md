# API방식
```java
@GetMapping("hello-string")
@ResponseBody
public String helloString(@RequestParam("name") String name) {
    return "hello " + name;
}
```
* ResponseBody: 뷰 리졸버 작동하지 않아서 템플릿 안찾는다. 
* http 바디에 데이터 담아서 응답하도록 함.

```java
@GetMapping("hello-api")
@ResponseBody
public Hello helloApi(@RequestParam("name") String name) {
    Hello hello = new Hello();
    hello.setName(name);
    return hello;
}
static class Hello {
    private String name;

    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```
* 객체 반환하면 객체가 JSON으로 변환됨.
* @ResopnseBody 사용하면 viewResolver 대신에 HttpMessageConverter가 동작.
* 문자열은 StringHttpMessageConverter가 처리.
* 객체는 MappingJackson2HttpMessageConverter가 처리.

***TIP***  
alt + insert 누르면 generate 기능 쓸 수 있는데 여기서 getter setter 자동으로 만들 수 있음.
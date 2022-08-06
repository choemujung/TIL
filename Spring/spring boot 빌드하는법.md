# 빌드하기
1. cmd에서 프로젝트 폴더로 이동
```
cd ~/hello-spring
```
2. gradlew.bat 파일 실행. gradlew 입력하면 실행됨.
```
gradlew
```
3. build 디렉토리 생성되면 build/libs로 이동
```
cd ./build/libs
```
4. 파일 목록 확인
![](./img/jar%ED%8C%8C%EC%9D%BC%ED%99%95%EC%9D%B8.png)
5. 용량 큰거 실행
```
java -jar hello-spring-0.0.1-SNAPSHOT.jar
```
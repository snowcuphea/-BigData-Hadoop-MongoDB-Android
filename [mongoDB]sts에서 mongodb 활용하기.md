maven 프로젝트 하나 만든다. 이름은 mongoTest

패키지명 spring.data.mongoTest

pom.xml 에서 버전 4.2.2수정해준다. 

https://mvnrepository.com/artifact/org.springframework.data/spring-data-mongodb/1.6.0.RELEASE

맨 밑에 dependecny 추가

![image-20200317163235293](images/image-20200317163235293.png)

저장 누르면 Maven Dependencies 에 라이브러리가 추가됨을 확인할 수 있다.

![image-20200317163339371](images/image-20200317163339371.png)



https://blog.naver.com/PostList.nhn?blogId=heaves1&from=postList&categoryNo=189&parentCategoryNo=189

선생님 블로그에서 springdata 파일 다운 받고, 압축 푼다.

spring폴더 전체는 src/main/java에 넣고, view 파일은 Web-INF >views에 다 넣는다. 



appSevlet > servlet-context.xml에서 namespaces만열어준다.

![image-20200317163735249](images/image-20200317163735249.png)



클라이언트 프로그램인 sts가 mongod로 올려놓은 서버에 액세스하기 위해서, 
mongodb의 데이터를 원하는 데이터를 집계해서 화면에 찍는 작업

mongodb의data를 활용해서 input 데이터로 활용하는 등 작업을 할 수 있다.

spring으로 mongodb를 접근 : 관계형데이터베이스가 아니라 새롭게 생긴 db로 접근해야 한다. 
따라서 라이브러리 등록 해야한다. (pom.xml에다가 mvnproject 에서 가져온 소스 넣기),
그리고 등록한 라이브러리를 설정해줘야 한다. (servlet-context.xml namespaces에서 설정)
![image-20200317164227294](images/image-20200317164227294.png)

mongo 항목에 체크해준다.



source화면을 보면, mongo가 추가됨을 확인할 수 있다.

![image-20200317164330324](images/image-20200317164330324.png)



몽고템플릿 클래스를 추가해서, 몽고와 관련된 모든 기능을 사용할 수 있도록 한다.
(전에 웹 sql 에서 mybatis추가해서 mybatis 해당 기능 사용했던 것처럼)



![image-20200317170423765](images/image-20200317170423765.png)

mongod의 listening 부분의 port가 sts에서 설정파일의 port가 된다. 

mongo로 가서 bigdata라는 user를 만든다.

![image-20200317170816418](images/image-20200317170816418.png)

![image-20200317171021161](images/image-20200317171021161.png)

ip, port를 입력해주고, 클래스를 등록해준다.



---

csv파일 저장

![image-20200318092058850](images/image-20200318092058850.png)

![image-20200318092448841](images/image-20200318092448841.png)



### Export

```xml
mongoexport -d mydb -c score -o score.json
```



mydb라는 데이터베이스에 있는 score 컬렉션 export

* `-d` + 데이터베이스명
* -`c`  + 컬렉션명
* `-o` + 만들어질 파일명. 경로를 써주어도 된다. 

![image-20200318092736006](images/image-20200318092736006.png)

![image-20200318092845088](images/image-20200318092845088.png)

![image-20200318092910109](images/image-20200318092910109.png)

json형태로 저장되었다. 





### import

```
mongoimport /d bigdata /c test /type csv /file  test.csv /headerline
```



* `/d` + import 데이터타입
* `/c` + 컬렉션명
* `/type` + import할타입. default는 json이므로 그 외 경우만 적어준다.
* `/file` + import할파일. 경로를 적어주어도 된다.
* `/headerline` : 헤더라인이 있다는 뜻. 맨 윗줄 지우고 import하게 된다.

![image-20200318093802054](images/image-20200318093802054.png)

![image-20200318093926049](images/image-20200318093926049.png)

mongo에서 확인해보니 데이터가 들어와있음을 확인할 수 있다.





STS > mongoTest > spring.data.mongodb.dto > ScoreDTO클래스 생성

이게 하나의 도큐먼트임을 명시하는 `@Documnet`를 해준다. 어노테이션 안에 반드시 컬렉션을 명시해줘야 한다.

![image-20200318095053453](images/image-20200318095053453.png)

![image-20200318100917139](images/image-20200318100917139.png)

필드에 해당하는 변수 다 선언해주고, 셋겟, 생성자, tostring 다 만들어준다.

그리고 `String _id` 를 선언해주는데, 기본키임을 알리는 `@Id` 어노테이션을 추가해준다.



![image-20200318101207098](images/image-20200318101207098.png)

Interface를생성한다.

![image-20200318101835405](images/image-20200318101835405.png)

![image-20200318101955806](images/image-20200318101955806.png)



mongodb로 가서 선생님이 주신 data.txt 복사해서 붙여넣어서 데이터 넣기

![image-20200318102116095](images/image-20200318102116095.png)



indexContoller실행

![image-20200318103420118](images/image-20200318103420118.png)

ScoreMongoDAOImpl, ScoreMongoDAOServiceImpl 을 만들어준다.

![image-20200318111847484](images/image-20200318111847484.png)



### FindAll()

* ScoreMongoServiceImpl

![image-20200318111906287](images/image-20200318111906287.png)

* socreMongoDAOImpl

![image-20200318112603659](images/image-20200318112603659.png)



![image-20200318112500369](images/image-20200318112500369.png)



![image-20200318112530922](images/image-20200318112530922.png)

![image-20200318113610672](images/image-20200318113610672.png)

![image-20200318114342355](images/image-20200318114342355.png)





![image-20200318132403791](images/image-20200318132403791.png)

![image-20200318132522496](images/image-20200318132522496.png)



![image-20200318132637860](images/image-20200318132637860.png)





![image-20200318133811016](images/image-20200318133811016.png)

페이지번호가 있으나, 페이징처리가 된 것은 아니다. 





----



### insert

mongoTemplate은 편리하게 함수를 제공한다. 

![image-20200318132220462](images/image-20200318132220462.png)

![image-20200318132335797](images/image-20200318132335797.png)

![image-20200318132459662](images/image-20200318132459662.png)

![image-20200318133403214](images/image-20200318133403214.png)





jsp 화면



![image-20200318133932027](images/image-20200318133932027.png)

![image-20200318134415287](images/image-20200318134415287.png)

![image-20200318134551003](images/image-20200318134551003.png)



### < multiInsert 결과 >

![image-20200318141716699](images/image-20200318141716699.png)

페이징에서 한 페이지수를 10으로 설정했다.

DAO에서 한 페이지에 해당하는 다큐먼트 수를 설정할 수 있다.

![image-20200318141834399](images/image-20200318141834399.png)





### 

## Read

findById (key,value) 



DAOImpl 에서 Criteria 를 사용한다.

Criteria 클래스는 조건을 걸 때 사용한다. 다양한 메소드를 사용할 수 있다. 

![image-20200318143652026](images/image-20200318143652026.png)

![image-20200318144330634](images/image-20200318144330634.png)















![image-20200318145031717](images/image-20200318145031717.png)

![image-20200318145106981](images/image-20200318145106981.png)









### < 실행결과 >

![image-20200318144629936](images/image-20200318144629936.png)

![image-20200318145203919](images/image-20200318145203919.png)

![image-20200318145215334](images/image-20200318145215334.png)



---

## Find

![image-20200318145253483](images/image-20200318145253483.png)




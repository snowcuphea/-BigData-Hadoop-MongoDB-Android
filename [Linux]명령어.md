

### hostname 변경 방법

![image-20200219134227570](C:/Users/student/Desktop/Linux_note/images/image-20200219134227570.png)

```xml
hostnamectl set-hstname 변경할이름
```



### ls

* 경로의 파일 보기

```
ls /etc/sysconfig
```

 와 같이 특정 경로 써주면 해당 경로의 모든 파일을 보여준다.  



숨김파일이나 숨김폴더는 앞에`.` 을 붙이면 된다.

* 숨김 파일 포함 하는 명령어

```
ls -a
```



* 파일과 그에 대한 정보를 자세히 보여줌

```
ls -l
```



* 특정 확장자 목록

```
ls *.확장자명
```



* 섞어서 한번에 쓸 수 있다.

``` 
ls -al
```

(a와 l 동시사용)



----

### cd

* `cd ~` : 홈 디렉토리로 이동
* `cd .. `: 상위 디렉토리로 이동

### mkdir

* `mkdir /폴더명` : 폴더명 이라는 디렉토리 생성

* `mkdir -p 폴더명/하위폴더명/하위하위폴더명` : 계층형 디렉토리 생성 



### touch

* `touch 파일명` : 파일명 이라는 파일 생성

![image-20200219141532109](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200219141532109.png)

### cp

* `cp 복사할대상 붙여넣을대상` : 복사할대상을 붙여넣을대상에 복사함

![image-20200219141521260](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200219141521260.png)

* 





### rm

* `rm 지울대상` : 지울대상을 삭제한다.

  명령어를 치면 지울 것인지에 대한 질문이 나오는데, Yes(or y)하면 지워진다.

![image-20200219141723401](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200219141723401.png)

* `rm -f 지울대상` : 지울 때 확인질문 없이 바로 삭제

* `rmdir 폴더명`  : 폴더를 지운다.

  ![image-20200219142305145](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200219142305145.png)





* `rm -r 디렉토리` :  디렉토리를 지운다. 폴더 깊이만큼 삭제 확인질문이 나온다. 

![image-20200219142805764](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200219142805764.png)



* `rm -rf 디렉토리` : 삭제확인질문없이 바로 디렉토리 이하 수준 삭제 





### mv

* `mv 옮길대상 이동할위치` : 대상을지정하여 새로운 위치로 이동
* `mv 기존파일명 새로운파일명` : 같은 폴더에 있는데 mv를 사용할 경우, 기존파일명이 새로운 파일명으로 이름이 바뀐다. 



### cat



### head

* `head -5 파일명` : 파일의 마지막 5행만 화면에 출력
* `head 파일명` : 텍스트 형식으로 작성된 파일의 앞 10행 or 마지막 10행만 화면에 출력



### more

* `more 파일명` : 텍스트형식으로 작성된 파일을 페이지 단위로 화면에 출력
  * [스페이스바]는 다음, [b]를 누르면 앞페이지로 이동







### 한 번에 여러 파일 넣기 

* ` fs -put *.확장자명 /넣을곳`  : 확장자명으로 된 모든 파일을 넣는다. 

```
/home/hadoop/hadoop-1.2.1/bin/hadoop fs -put *.csv /input
```

ex) *.csv 로 하면 확장자가 .csv인 파일이 input폴더 밑으로 다 모인다. 
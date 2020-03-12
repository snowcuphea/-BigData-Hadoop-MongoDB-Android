## Apache Sqoop



오라클이나 sql에서 만들어진 것을 hadoop으로 옮기는 프로그램





sqoop1 > 1.4.6 버전  > 

![image-20200311162325782](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200311162325782.png)

오른쪽 버튼 누르고 > 링크 주소 복사

터미널 창에 wget 적고 링크 붙여넣기

![image-20200311162425786](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200311162425786.png)

![image-20200312092425752](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312092425752.png)

압축파일을 받은 것을 확인하고, tar명령어를 통해 설치한다.

```
tar -zxvf sqoop-1.4.6bin__hadoop-1.0.0.tar.gz
```

---



선생님 블로그에서 다운받은 패키지를 import 해준다.

![image-20200312093030716](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312093030716.png)

![image-20200312093154976](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312093154976.png)



---

show view 에서 > Database connections > 하단에 추가되면 오른쪽버튼 눌러서 new

![image-20200312094729537](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312094729537.png)





![image-20200312094614763](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312094614763.png)

![image-20200312094639337](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312094639337.png)

![image-20200312094817335](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312094817335.png)



Test Connection눌러서 연결이 제대로 되는지 확인한다.

![image-20200312094852272](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312094852272.png)

![image-20200312095217548](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312095217548.png)

![image-20200312100944154](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312100944154.png)

![image-20200312101117491](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312101117491.png)

order파일도 실행



이후 아파치 톰캣 등록하여 웹페이지 접속 하기





다시 하둡으로

![image-20200312104054938](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312104054938.png)

숨겨져있던 .으로 시작하는 파일들이 보이는데, `.` 이 붙으면 숨김처리가 된다.

중요한 파일들이라 숨김처리 되어있다.



`.bashrc` 는 bash의 설정파일이므로 수정 시 유의해야한다.

![image-20200312105024909](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312105024909.png)

```

```

앞으로 프로그램을 설치하고 연결할 때마다 추가해준다. 

---

설정파일을 실행할 때 쓰는명령어 : `source + 파일명`

![image-20200312105304624](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312105304624.png)

etc profile에서 수정하는게 쉽지만, 일반 계정에서는 건드릴 수 없다.



![image-20200312111116198](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312111116198.png)

로컬에있는 ojdbc6.jar파일을 copy해서 머신의 home > sqoop > lib 에 붙여넣기

![image-20200312111219957](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312111219957.png)

---

![image-20200312111348760](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312111348760.png)

shop 계정으로 로그인하고, sql명령어를 작성할 수 있도록 적어준다. 



http://sqoop.apache.org/docs/1.4.6/SqoopUserGuide.html

스쿱 가이드 페이지

`-target-dir` : output폴더 지정해준다.

`columns` : 컬럼을 지정해서 가져온다. 

`-m` + 숫자: 맵 태스크를 해당 숫자만큼 사용 

![image-20200312113226864](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312113226864.png)

![image-20200312114007698](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312114007698.png)







---

![image-20200312113758490](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312113758490.png)

이렇게 하면 오류떠서 split-by를 해준다.

![image-20200312113825461](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312113825461.png)





![image-20200312113945823](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312113945823.png)

완료!

![image-20200312114038768](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312114038768.png)

맵 두개 사용

---

### 이번엔 hdfs 에서 sql 로 결과파일 전송

sql에서 shop/shop으로 로그인 후 결과를 저장할 table생성

![image-20200312114221106](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312114221106.png)

![image-20200312114809154](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312114809154.png)

![image-20200312114848151](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312114848151.png)



![image-20200312131210726](C:\Users\student\AppData\Roaming\Typora\typora-user-images\image-20200312131210726.png)

data2.sql파일도 실행


etc > sysconfig > network-scripts > ifcfg-ens32

![image-20200224100714260](images/image-20200224100714260.png)

#처리된 부분은 주석이다. 
만약 네트워크가 뜨지 않으면 `dhcp` 부분을 주석처리하고, #해놓은 부분을 풀어서 설정해본다. 

![image-20200224101115770](images/image-20200224101115770.png)

---

외부에서 접속할 수 있도록 core-sites.xml에서 hadoop01대신 ip주소를 넣는다.

![image-20200224101715975](images/image-20200224101715975.png)

![image-20200224101831744](images/image-20200224101831744.png)

hdfs-site.xml에서도 hadoop01, 02머신의 IP로 수정해준다.



mapred-site.xml도 경로를 ip주소로 적어준다.

![image-20200224101944471](images/image-20200224101944471.png)

그리고 property를 하나 더 추가해준다.

특정폴더를 하나 오픈해놓고, 특정폴더에 접근할 수 있도록 설정가능하다. 

/input 하면 input폴더만 접근할 수 있다. 

/를 하면 밑에 보이는 폴더 다 접근가능하다. 

![image-20200224103441770](images/image-20200224103441770.png)

![image-20200224102402082](images/image-20200224102402082.png)

설정파일이 바뀌었기때문에 하둡을 스탑시키고

![image-20200224102513567](images/image-20200224102513567.png)



![image-20200224102702605](images/image-20200224102702605.png)

``` 
scp /home/hadoop/hadoop-1.2.1/conf/* hadoop@hadoop02:/home/hadoop/hadoop-1.2.1/conf/
```

명령어로 수정한 xml 파일을 02,03,04머신에 모두 복사한다. 

그리고 start-all 시킨다..



---

sts 와서 새로운 프로젝트 만든다.

![image-20200224103058337](images/image-20200224103058337.png)

패키지를 복사하면 오류가 뜨는데, 플젝오른쪽버튼 > build path > add external jars > 위에 두 jar파일 넣어야 오류가 사라진다. 

![image-20200224103231262](images/image-20200224103231262.png)



프로젝트 밑에 conf, lib폴더를 만든다. 

---

하둡머신에 있던 jar파일을 sts의 방금만든 lib폴더에 복사해서 붙여넣는다.

![image-20200224103633757](images/image-20200224103633757.png)

![image-20200224103647214](images/image-20200224103647214.png)

또 하둡머신에 있던 conf 의 아까 수정한 3파일을 방금만든sts의 conf파일에 복붙한다. 

![image-20200224103735306](images/image-20200224103735306.png)

![image-20200224103808080](images/image-20200224103808080.png)



그 다음에 F5로 새로고침

![image-20200224103932774](images/image-20200224103932774.png)

ADD jar해준다. 

![image-20200224104055890](images/image-20200224104055890.png)

Add class 해서 conf를 체크해서 추가해준다. 



![image-20200224104215011](images/image-20200224104215011.png)

오류떠있어서 자바 빌드패서 창 들어가서 확인해보자 



build path 창 들어가서 문제가 되는 2개 파일 remove하면 오류 사라진다.

![image-20200224104749255](images/image-20200224104749255.png)



![image-20200224104646254](images/image-20200224104646254.png)

![image-20200224104858459](images/image-20200224104858459.png)

![image-20200224105239935](images/image-20200224105239935.png)

Permission denied : 외부 프로그램으로 하둡에 접속햇을 경우 하둡은 읽기는 되는데, hdfs는 외부에서 쓰기에 대한 권한이 없다. 

따라서 이를 해결하기 위해 권한을 해제해야 한다.

 하둡에서 conf > hdfs-site.xml 로 들어가서 권한 해제하는 코드를 추가해준다.

![image-20200224110808957](images/image-20200224110808957.png)



![image-20200224110936044](images/image-20200224110936044.png)

2,3,4에 카피해준다. 그리고 다시 start-all.sh





![image-20200224111318329](images/image-20200224111318329.png)

sts에서도 추가해준다.



lib밑에 conf 파일 있는데, 연결되어 있어서 여기도 내가 쓴 프로퍼티가 반영되어있다.

![image-20200224111501597](images/image-20200224111501597.png)



이제 다시 run configuration 해서 실행시키자

----

오류가뜬다. 

![image-20200224111700168](images/image-20200224111700168.png)

아무것도 안써줬기 때문에 디폴트로 /user로 들어가고 그 다음은 윈도우 계정으로 들어가게 되어있다. 

경로를 다시 수정해주자 (명령 프롬프트에서)

![image-20200224112950070](images/image-20200224112950070.png)

mywork앞에 `/` 를 써주고, csv파일은 1로시작하는 모든 것 으로 설정했다.

그리고 다시 실행시켜보자



그리고 다시 오류가 뜬다. jar파일로 묶어서 실행해야 하는데 안묶어서 그렇다. 



프로젝트 선택 후 >export > Java의 jar file > 

![image-20200224112253356](images/image-20200224112253356.png)

![image-20200224112406453](images/image-20200224112406453.png)

![image-20200224112420203](images/image-20200224112420203.png)

이렇게 하면 jar파일로 만들 수 있다.

![image-20200224112456377](images/image-20200224112456377.png)

(완성된 export해준 jar파일의 모습)

![image-20200224112742692](images/image-20200224112742692.png)

만들어진 jar파일 오른쪽버튽 눌러서 Add to Build Path해준다. 



이미 파일이 생겼을 수도 있기 때문에 파일명을 바꿔서 다시 실행해본다. 

---

![image-20200224113539747](images/image-20200224113539747.png)

값이 헷갈리지 않도록 mapper에서 연도 값을 볼 수 있게 추가해준다. 

mapred-exam.jar파일 remove시켜주고, 다시 프로젝트 export해서 jar파일로 만든 뒤 add to build path해서 넣어줘야한다. (그렇게 하지 않으면 반영이 안된다. )

실행결과 :
![image-20200224114100363](images/image-20200224114100363.png)



---


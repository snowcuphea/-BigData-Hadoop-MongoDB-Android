

![image-20200314175537449](images/image-20200314175537449.png)

연, 월, 일 설정하여 로그 파일 생성

but, 이렇게 하면 제대로 안나온다. 



![image-20200314095020602](images/image-20200314095020602.png)

얘가 계속 롤링하면서 로그가 추가되고 있으니, 너무 용량이 커지면 쓸모없는 로그기록은 지워준다. 

![image-20200314101315835](images/image-20200314101315835.png)

TimeStamp 오류가 떴기때문에, 해당 문장 추가해주고 다시 inputdata집어넣고 실행해본다..

![image-20200314101718026](images/image-20200314101718026.png)

제대로 나옴을 확인할 수 있다. 



### exec

hdfs3.properties 로 conf 파일 내 properties파일 rename하여 생성한다.

![image-20200314103303439](images/image-20200314103303439.png)

![image-20200314103446989](images/image-20200314103446989.png)



source 에 exec 로 타입을 명시하고, 그에 필요한 shell, command 정보를 작성한다. 



----



이번엔 2번머신을 WAS로 잡는다.

![image-20200314105142161](images/image-20200314105142161.png)



설치 후 홈디렉토리에 압축을 풀어준다.

1번머신의 bashrc 파일을 2번머신으로 복사해준다.

![image-20200314111505727](images/image-20200314111505727.png)

![image-20200314112445915](images/image-20200314112445915.png)

안쓰는거 일단 주석처리하고
새로 경로를 추가해준다. 아파치톰캣 등록 시 사용하는 단어는 CATALINA

작성 뒤 실행시켜준다.

![image-20200314112526188](images/image-20200314112526188.png)





![image-20200314113041388](images/image-20200314113041388.png)

bin에 들어가서 실행시킨다.



톰캣의 기본포트는 8080이다.

8080포트를 가진 것을 조회했을 때 나온다. 

```
netstat -anp | grep 8080
```

![image-20200314113131242](images/image-20200314113131242.png)



2번머신 웹에서 http://127.0.0.1:8080 으로 들어가면 톰캣 화면이 나온다.

2번머신이 WAS로 설정된 것을 확인할 수 있다.



![image-20200314113310011](images/image-20200314113310011.png)



다음은 role을 설정해주어야 한다.



![image-20200314114206535](images/image-20200314114206535.png)





![image-20200314114518123](images/image-20200314114518123.png)

admin이라는 계정을 만들었다. 

manager-gui 라는 role은, 이 페이지에 접속할 수 있는 role이다.

![image-20200314114701971](images/image-20200314114701971.png)

manager app으로 가면, 아이디 비번 치는 창이 나오고 등록한 계정으로 (admin, admin) 접속하면

Manager App 화면이 나온다. 





![image-20200314132310535](images/image-20200314132310535.png)

이걸로 크롬에서 접속해보자. 현재 접속이 안되지만, 접속이 되게 만들어야한다.

![image-20200314132442547](images/image-20200314132442547.png)

![image-20200314132729039](images/image-20200314132729039.png)

아파치톰캣 > webapps>manager >meta-inf > context.xml에서 value부분 주석처리하기

저장하면

![image-20200314132958561](images/image-20200314132958561.png)

접속됨을 확인할 수 있다.



sts가서  meta-inf > context.xml의 ip 바꿔준다.

![image-20200314133413668](images/image-20200314133413668.png)

![image-20200314134143347](images/image-20200314134143347.png)

![image-20200314134201627](images/image-20200314134201627.png)

![image-20200314134231803](images/image-20200314134231803.png)

![image-20200314134303000](images/image-20200314134303000.png)



그 담에 [배치] 누르면 배치된다.

![image-20200314134357506](images/image-20200314134357506.png)

이제, hadoop02 가 서버가 되었다.

웹에서 머신2번의 아이피/배치된프로젝트 사이트로 접속이 가능하다.

![image-20200314134511966](images/image-20200314134511966.png)



머신 2번 > 톰캣 > logs > localhost_access_log 에 로그가 기록된다.

![image-20200314141342066](images/image-20200314141342066.png)

하지만 어느 ip에서 접속했는지 확인할 수 없어서, 그에 따른 기능을 추가해줘야 한다. 
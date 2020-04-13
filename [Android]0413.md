# Google Map 라이브러리 사용





새 프로젝트 생성 : map_location_pro

![image-20200413092137899](images/image-20200413092137899.png)





location, map 패키지 추가

![image-20200413092315774](images/image-20200413092315774.png)



* API발급 사이트에서 발급받기

  https://console.developers.google.com/

![image-20200413093347704](images/image-20200413093347704.png)

![image-20200413093441819](images/image-20200413093441819.png)





![image-20200413093740808](images/image-20200413093740808.png)

![image-20200413093719095](images/image-20200413093719095.png)

![image-20200413093911611](images/image-20200413093911611.png)

![image-20200413093919952](images/image-20200413093919952.png)

![image-20200413093939771](images/image-20200413093939771.png)

![image-20200413093951267](images/image-20200413093951267.png)

![image-20200413094010868](images/image-20200413094010868.png)



패키지명을 등록해야한다. 





Project Structure > dependency 목록을 볼 수 있다. -추후 사용할 예정

![image-20200413094403071](images/image-20200413094403071.png)







![image-20200413094548420](images/image-20200413094548420.png)

![image-20200413094717999](images/image-20200413094717999.png)

![image-20200413094825736](images/image-20200413094825736.png)



* 선생님 블로그에 있는 implementation 복붙해서 gradle에 넣는다.

  ```xml
  implementation 'com.google.android.gms:play-services-maps:17.0.0'
  implementation 'com.google.android.gms:play-services-location:17.0.0'
  ```

  

![image-20200413100629158](images/image-20200413100629158.png)











![image-20200413100755082](images/image-20200413100755082.png)

* 그 다음 Linear로 변경





* xml 에 fragment추가

![image-20200413101151543](images/image-20200413101151543.png)



* manifest에 use permission이랑 meta-data 추가한다.

* value에는 api사이트의 key번호가 들어간다.

![image-20200413101426940](images/image-20200413101426940.png)



* java에서 실행

  ![image-20200413101633385](images/image-20200413101633385.png)

  









### BasicLocationTest 액티비티 추가

![image-20200413102542493](images/image-20200413102542493.png)





![image-20200413103802712](images/image-20200413103802712.png)

* 빨간줄이 뜨는 이유는 권한 등록을 안해줬기 때문이다.

* 매니페스트에 가서 권한 등록 해준다.

![image-20200413104441775](images/image-20200413104441775.png)





* java에서 권한체크 부분 써준다.

![image-20200413104423152](images/image-20200413104423152.png)

![image-20200413111613593](images/image-20200413111613593.png)
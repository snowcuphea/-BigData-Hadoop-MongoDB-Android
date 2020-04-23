# drawable 활용하기

drawable > drawable resource file > 

![image-20200327092318809](images/image-20200327092318809.png)

![image-20200327092407922](images/image-20200327092407922.png)

![image-20200327092812803](images/image-20200327092812803.png)

* 이렇게 만들고, 저장한다.



![image-20200327092905440](images/image-20200327092905440.png)

* 뷰 xml 파일에서 보면 해당 파일이 올라와있는 것을 알 수 있다.





![image-20200327093024786](images/image-20200327093024786.png)

* 매니페스트에서 ViewTestActivity 등록해준다.

* 그리고 Run 해본다.![image-20200327093233810](images/image-20200327093233810.png)

* 내가 만든 그라디언트 xml drawable 파일을 적용시킬수 있다.





---

## 선 테스트



새로운 drawable파일 만든다.

![image-20200327093355881](images/image-20200327093355881.png)

![image-20200327093454312](images/image-20200327093454312.png)

![image-20200327093636772](images/image-20200327093636772.png)



실행

![image-20200327093719553](images/image-20200327093719553.png)





---

## 모양만들기

![image-20200327093753979](images/image-20200327093753979.png)

![image-20200327094022431](images/image-20200327094022431.png)

![image-20200327094040246](images/image-20200327094040246.png)

![image-20200327094109513](images/image-20200327094109513.png)



---

## Corner

![image-20200327094237075](images/image-20200327094237075.png)

![image-20200327094455368](images/image-20200327094455368.png)





---

# Text Layout 텍스트 레이아웃





![image-20200327094900651](images/image-20200327094900651.png)

![image-20200327095118070](images/image-20200327095118070.png)



### 정적 문자열의 관리 => 리소스의 외부화

먼저 TextView 속성을 AppCompat으로 해준다.

![image-20200327101550130](images/image-20200327101550130.png)



* 그리고 리소스를 관리하는 values의 strings에 welcome 을 하나 만든다.

![image-20200327101522671](images/image-20200327101522671.png)



* 만든 텍스트를 파일에 정의한 것을 연결시킨다.

![image-20200327101634161](images/image-20200327101634161.png)

![image-20200327101705415](images/image-20200327101705415.png)

파일에 정의한 텍스트가 나옴을 확인할 수 있다.



* `EditText` : 사용자로부터 값을 입력받을 수 있다.

![image-20200327101906569](images/image-20200327101906569.png)![image-20200327102025099](images/image-20200327102025099.png)

* hint가 나오고, 입력문자열 타입을 number로 했기때문에
  text칸 클릭 시 숫자키패드가 나옴을 확인할 수 있다.



---

* string 파일에 getdata,setdata 이름으로 항목 추가

![image-20200327102234537](images/image-20200327102234537.png)



![image-20200327103254789](images/image-20200327103254789.png)

![image-20200327104227778](images/image-20200327104227778.png)

![image-20200327104433103](images/image-20200327104433103.png)





---

# 실습 : 채팅창 만들기







![image-20200327114444613](images/image-20200327114444613.png)

![image-20200327114321501](images/image-20200327114321501.png)








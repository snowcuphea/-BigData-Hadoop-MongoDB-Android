## ProgressBar

프로그레스바 : 네트워크 연결해서 서비스 돌릴 때 진행상태를 표현한다.

```xml
  <ProgressBar
        android:id="@+id/progress1"
        style="@android:style/Widget.DeviceDefault.ProgressBar.Small"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <ProgressBar
        android:id="@+id/progress2"
        style="@android:style/Widget.DeviceDefault.ProgressBar.Large"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <ProgressBar
        android:id="@+id/progress3"
        style="@android:style/Widget.DeviceDefault.ProgressBar.Horizontal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
```

![image-20200406093626457](images/image-20200406093626457.png)



![image-20200406094758336](images/image-20200406094758336.png)

---



![image-20200406100809886](images/image-20200406100809886.png)

![image-20200406101015553](images/image-20200406101015553.png)



* 이 버튼 3개로 프로그레스바를 설정할 예정

![image-20200406102342804](images/image-20200406102342804.png)

![image-20200406102322266](images/image-20200406102322266.png)







## SeekBar

* SeekBar : 이동하면서 범위나, 진행상황을 설정할 수 있다.

* 선생님 블로그에서 0406폴더 다운받고, advanced 폴더의 SeekBarActivity를 자바 항목에 넣는다. 

![image-20200406094134456](images/image-20200406094134456.png)



* 레이아웃 xml파일이 없기때문에, 새로 만들어준다.
  => seekbar_main.xml 로 만들 것이다.





![image-20200406093909362](images/image-20200406093909362.png)

![image-20200406094335017](images/image-20200406094335017.png)



* 만들고 나서 SeekBarActivity.java와 맞추기 위해 요소를 추가한다.

![image-20200406094445841](images/image-20200406094445841.png)

![image-20200406094511868](images/image-20200406094511868.png)





* 그리고 뷰 화면에서 

![image-20200406094559264](images/image-20200406094559264.png)



* 두 번째 seekbar선택하고, common attribute > style 에 SeekBar.Discrete 선택

  ![image-20200406094700242](images/image-20200406094700242.png)



이렇게 변경된다.



![image-20200406094853884](images/image-20200406094853884.png)



---



* 버튼으로 값 제어하기 

![image-20200406102647692](images/image-20200406102647692.png)



* 버튼 변수를 정의해주고, OnClickListener와 OnSeekBarChangeListener를 implements 해준다. 

![image-20200406103039038](images/image-20200406103039038.png)

* 빨간줄:  unimplement된 메소드들이 있으므로 추가해준다. 



![image-20200406103058376](images/image-20200406103058376.png)



* 리스너와 이벤트를 연결해준다.
* 이 때 리스너는 위에서 implments 해 준 것들이 있기에 this로 작성해주면 된다. 

![image-20200406105146634](images/image-20200406105146634.png)



* 버튼 클릭 시 자동으로 호출되는 메소드 코드 작성
* View : 매개변수로 전달되는 View가 이벤트를 발생시키는 소스객체이다.
  View에서 getId 한 것이 seekBtn1일 경우 처럼 case로 나눠서 작성한다.

![image-20200406110607675](images/image-20200406110607675.png)



* SeekBar의 값이 변경되었을 때 호출되는 메소드 코드 이벤트 작성

  onProgressChanged 메소드를 보면, 매개변수로 seekbar / progress 값 / Boolean타입의 fromUser 가 전달된다. 

![image-20200406104439001](images/image-20200406104439001.png)



---



* 글씨 너무 작아서 Large로 변경
* 기기마다 공통적인 크기로 적용되는 AppCompat으로 설정해준다. (Large)

![image-20200406104545380](images/image-20200406104545380.png)

![image-20200406105434669](images/image-20200406105434669.png)

![image-20200406105513668](images/image-20200406105513668.png)





![image-20200406110712518](images/image-20200406110712518.png)

![image-20200406110756860](images/image-20200406110756860.png)



----





![image-20200406110951603](images/image-20200406110951603.png)



---

## CalendarView

![image-20200406111933218](images/image-20200406111933218.png)

![image-20200406111951764](images/image-20200406111951764.png)

https://developer.android.com/guide
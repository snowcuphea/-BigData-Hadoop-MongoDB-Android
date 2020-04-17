# 내비게이션뷰(NavigationView) 

* 평소엔 숨겨져 있다가, 햄버거 누르면 옆에서 나오는 메뉴

![image-20200417092716595](images/image-20200417092716595.png)



![image-20200417092919955](images/image-20200417092919955.png)





* 그 담에 Project Structure 가서 dependencies에 design 쳐서 support design 적용



* xml에 해당 내용 추가

  ```xml
  <LinearLayout        android:layout_width="match_parent"        android:layout_height="match_parent"        android:orientation="vertical">         <TextView            android:id="@+id/drawertxt"            android:layout_width="match_parent"            android:layout_height="wrap_content"            android:gravity="center"            android:text="Navigation View Test"            android:textSize="30dp"            android:textStyle="bold" />     </LinearLayout>
  ```

  

![image-20200417093340870](images/image-20200417093340870.png)

![image-20200417093534795](images/image-20200417093534795.png)



선생님 블로그에서 사진이랑 navigation_header.xml 파일다운받아서 저장

* navigation_header.xml 

```xml
<?xml version="1.0" encoding="utf-8"?>
<TextView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="250dp"
    android:background="@drawable/lee"
    android:gravity="bottom"
    android:paddingLeft="16dp"
    android:paddingBottom="16dp"
    android:text="Hello Android"
    android:textColor="@android:color/black"
    android:textSize="20dp"
    android:textStyle="bold" />
```



* navigation_header.xml 를 activity_main.xml에 연결

![image-20200417094838065](images/image-20200417094838065.png)



* res폴더에 menu 리소스폴더 만들기

 ![image-20200417094129021](images/image-20200417094129021.png)

![image-20200417094157384](images/image-20200417094157384.png)

![image-20200417094222345](images/image-20200417094222345.png)

![image-20200417094412211](images/image-20200417094412211.png)

![image-20200417094556022](images/image-20200417094556022.png)

![image-20200417094810001](images/image-20200417094810001.png)

![image-20200417101356168](images/image-20200417101356168.png)

![image-20200417101522895](images/image-20200417101522895.png)

실행시켜보니까 튀어나오지는 않는다. 따라서 코드를 추가로 작성해준다.



* `onOptionItemSelected` 메소드를 반드시 구현해야 사용할 수 있다.

![image-20200417101657553](images/image-20200417101657553.png)

![image-20200417101736964](images/image-20200417101736964.png)

* 토글 기능이 작동한다.



아이템 항목을 누르면 반응하도록 리스너를 걸어준다.

![image-20200417102616984](images/image-20200417102616984.png)



* 실행결과

  ![image-20200417102840425](images/image-20200417102840425.png)





![image-20200417111434734](images/image-20200417111434734.png)





## CardView

![image-20200417111803348](images/image-20200417111803348.png)

![image-20200417112439189](images/image-20200417112439189.png)



* card_view 속성 쓰려면 xmlns 에 선언해줘야한다. 

![image-20200417112914993](images/image-20200417112914993.png)

![image-20200417112954345](images/image-20200417112954345.png)

![image-20200417113007988](images/image-20200417113007988.png)





---



라이브러리 gradle(Module)에 추가 : 써클이미지 툴

implementation 'de.hdodenhof:circleimageview:3.0.1'

![image-20200417114343014](images/image-20200417114343014.png)

![image-20200417114353512](images/image-20200417114353512.png)






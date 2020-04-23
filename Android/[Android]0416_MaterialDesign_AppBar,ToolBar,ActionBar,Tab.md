# Material Design

https://developer.android.com/guide/topics/ui/look-and-feel

![image-20200416092203418](images/image-20200416092203418.png)



File > Project Structure > Dependencies > `+` > Library Dependence 선택 >

design 검색 

![image-20200416092313534](images/image-20200416092313534.png)

![image-20200416092415495](images/image-20200416092415495.png)



그 담에 `build.gradle` 가서 빨간 밑줄 뜨는거 설치하고 Sync now 하기



![image-20200416092715391](images/image-20200416092715391.png)



이전에 작업한 support_lib에서 파일을 가져온다.

![image-20200416093151127](images/image-20200416093151127.png)

오류가 나므로, import support_lib.R 부분을 모두 지워준다. 





## Tab

![image-20200416093726477](images/image-20200416093726477.png)

![image-20200416094014101](images/image-20200416094014101.png)

![image-20200416094103497](images/image-20200416094103497.png)

![image-20200416094201471](images/image-20200416094201471.png)







* `tabGravity` 를 조절해 한쪽으로 몰려있거나, 균등하게 item 밀집도 변경 가능

![image-20200416094652220](images/image-20200416094652220.png)



* BottomNavigationView 추가

![image-20200416094953935](images/image-20200416094953935.png)



탭과 Navi 사이에 여백을 주기 위해서 그 사이에 LinearLayout을 하나 추가해준다.

![image-20200416095203416](images/image-20200416095203416.png)

---

res 오른쪽버튼 New Resource Directory

![image-20200416100652387](images/image-20200416100652387.png)

Resource type : menu 선택

![image-20200416100724653](images/image-20200416100724653.png)

![image-20200416100748372](images/image-20200416100748372.png)

![image-20200416100810141](images/image-20200416100810141.png)

![image-20200416100907388](images/image-20200416100907388.png)

![image-20200416101519206](images/image-20200416101519206.png)

![image-20200416101633935](images/image-20200416101633935.png)



이제 만든 메뉴를 tab_test의 Navi메뉴에 연결한다. 

![image-20200416101800331](images/image-20200416101800331.png)

![image-20200416101844655](images/image-20200416101844655.png)





* TabTest.java에서 코드를 작성



* 선언

![image-20200416102348819](images/image-20200416102348819.png)



* `addTab()` : 탭 추가하는 메소드

![image-20200416102428077](images/image-20200416102428077.png)



* 첫 화면 프래그먼트 지정

![image-20200416102539558](images/image-20200416102539558.png)



* 실행화면

  ![image-20200416102636582](images/image-20200416102636582.png)



* `addOnTabSelectedListener` : 탭에 이벤트를 연결한다.

  메소드를 사용하면 자동으로 오버라이딩 된다.

  ![image-20200416102841337](images/image-20200416102841337.png)

탭을 바꿨다가 다시 돌아오면 초기화가 되면 안되니까 저장하는 방식을 구현한다.



* 일단 Tab이 갖고있는 순서를 가져와본다.

![image-20200416103025497](images/image-20200416103025497.png)

화면에서 tab을 순서대로 누른 뒤, 첫번째 탭까지 눌러보면 다음과 같이 순서가 출력된다.

![image-20200416103235151](images/image-20200416103235151.png)

0 1 2 3 인 것을 알 수 있다.

이를 통해 if문으로 조건을 나누고, 탭을 선택하면 지정된 프레그먼트 객체가 show되도록 연결해준다.

![image-20200416103529840](images/image-20200416103529840.png)



* 이번엔 BottomNavi에서 item이 selected 때 발생하는 이벤트를 작성한다.

![image-20200416103714187](images/image-20200416103714187.png)

* bottom_item2 항목을 선택하면, SecondFrag화면이 연결되도록 설계

![image-20200416103838933](images/image-20200416103838933.png)

![image-20200416104306453](images/image-20200416104306453.png)



---



## OptionMenu (...)





![image-20200416104407345](images/image-20200416104407345.png)



얘도 메뉴 아이템이 resource로 관리된다. 

![image-20200416104650803](images/image-20200416104650803.png)



세부 메뉴를 메뉴 항목 밑에 넣어서 만들 수 있다.

![image-20200416105004668](images/image-20200416105004668.png)

![image-20200416110446241](images/image-20200416110446241.png)

![image-20200416110521272](images/image-20200416110521272.png)



* OptionMenu.java 에서 코드 작성

  ![image-20200416111236661](images/image-20200416111236661.png)

  

![image-20200416111253281](images/image-20200416111253281.png)

![image-20200416111306626](images/image-20200416111306626.png)

![image-20200416111318874](images/image-20200416111318874.png)





* 메뉴 연결

![image-20200416111854641](images/image-20200416111854641.png)

![image-20200416111917095](images/image-20200416111917095.png)



### 액션바 제어하기

* 자주 사용하는 것을 액션바에 보이게 함
* 

![image-20200416112721501](images/image-20200416112721501.png)

![image-20200416112749969](images/image-20200416112749969.png)

![image-20200416112826646](images/image-20200416112826646.png)





![image-20200416112917374](images/image-20200416112917374.png)

* always : 항상보이게 한다.
* never : 보이지 않게 한다.
* ifroom : 공간이 있으면 보이게 한다.
* collapseActionView : 접었다펼쳤다 할 때
* withText : 텍스트랑 아이콘 동시에 보여준다.



![image-20200416114613657](images/image-20200416114613657.png)



* java 동작구성

![image-20200416114236262](images/image-20200416114236262.png)

![image-20200416131834887](images/image-20200416131834887.png)

* s라는 문자열을입력하면, s로 시작하는 item들이 걸러진다. => search_item





* 실행결과

![image-20200416132316564](images/image-20200416132316564.png)



![image-20200416132441551](images/image-20200416132441551.png)



![image-20200416133230544](images/image-20200416133230544.png)

![image-20200416133240900](images/image-20200416133240900.png)



* 전체코드

  ```java
  package multi.android.material_design_pro.actionbar;
  
  import androidx.annotation.NonNull;
  import androidx.appcompat.app.AppCompatActivity;
  
  import android.os.Bundle;
  import android.util.Log;
  import android.view.Menu;
  import android.view.MenuInflater;
  import android.view.MenuItem;
  import android.widget.ArrayAdapter;
  import android.widget.ListView;
  import androidx.appcompat.widget.SearchView;
  import android.widget.TextView;
  
  import multi.android.material_design_pro.R;
  
  public class ActionBarTest extends AppCompatActivity {
  
      TextView result;
      TextView result2;
      ListView listview;
      String[] datalist = {"java","servlet","jsp","html","android","spring",
      "spart","sqoop","spart","sqoop","spart","sqoop","spart","sqoop"};
  
      @Override
      protected void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.activity_action_bar_test);
          result = findViewById(R.id.result);
          result2 = findViewById(R.id.result2);
          listview = findViewById(R.id.listview);
          ArrayAdapter<String> myadapter = new ArrayAdapter<String>(this,
                  android.R.layout.simple_list_item_1,
                  android.R.id.text1,
                  datalist);
  
          listview.setAdapter(myadapter);
  
          //리스트뷰 안의 검색기능이 가능하도록 설정
          listview.setTextFilterEnabled(true);
      }
  
      @Override
      public boolean onCreateOptionsMenu(Menu menu) {
          MenuInflater inflater = getMenuInflater();
          inflater.inflate(R.menu.actionbar_menu,menu);
  
          //검색뷰가 셋팅되어 있는 메뉴아이템을 추출
          MenuItem search_item = menu.findItem(R.id.search);
          //액션뷰로 설정되어 있는 뷰를 추출한다.
          SearchView searchView = (SearchView)search_item.getActionView();
          //SearchView에 안내문구 등록
          searchView.setQueryHint("검색어를 입력하세요");
          //searchView에 이벤트 연결하기
          searchView.setOnQueryTextListener(new SearchView.OnQueryTextListener() {
              //키패드의 엔터키를 누르면 호출되는 메소드
              @Override
              public boolean onQueryTextSubmit(String query) {
                  result.setText(query);
                  return true;
              }
              //searchView의 텍스트가 변경될때 호출
              @Override
              public boolean onQueryTextChange(String newText) {
                  result2.setText(newText);
                  //전달되는 입력하는 문자열을 이용하여 리스트뷰에서 필터링
                  listview.setFilterText(newText);
                  if(newText.length()==0){ //전달되는게 없으면 clear
                      listview.clearTextFilter();
                  }
                  return true;
              }
          });
  
          //search_item에 이벤트 연결
          search_item.setOnActionExpandListener(new MenuItem.OnActionExpandListener() {
              @Override
              public boolean onMenuItemActionExpand(MenuItem item) {
                  result.setText("메뉴가 펼쳐짐");
                  return true;
              }
              @Override
              public boolean onMenuItemActionCollapse(MenuItem item) {
                  result.setText("메뉴가 접혀짐");
                  return true;
              }
          });
          return true;
      }
      //액션바의 아이콘, 메뉴가 선택될때
      public boolean onOptionsItemSelected(@NonNull MenuItem item) {
          Log.d("menu",item.getItemId()+"");
          int itemid = item.getItemId();
          String msg= "";
          switch (itemid){
              case R.id.search:
                  msg="첫 번째 메뉴 선택";
                  break;
              case R.id.option_1:
                  msg="즐겨찾기";
                  break;
          }
          result2.setText(msg);
  
          return super.onOptionsItemSelected(item);
      }
  }
  ```

Appbar : ex. 유튜브의 재생되던 동영상이 뒤로가기 하면 조그맣게 바 형태로 줄어드는 것

## ToolBar



![image-20200416133518893](images/image-20200416133518893.png)

![image-20200416133836845](images/image-20200416133836845.png)

![image-20200416134005470](images/image-20200416134005470.png)

![image-20200416134041453](images/image-20200416134041453.png)



* 액션바와 툴바의 차이점 : 액션바는 디폴트로 제공되는 것을 사용했다면, 툴바는 find해서 사용해야 한다. 또한 직접 만든 디자인을 연결해서 사용할 수 있다.

* 실행결과 : 마치 actionbar처럼 toolbar를 만들었다.

![image-20200416134551431](images/image-20200416134551431.png)

![image-20200416134604386](images/image-20200416134604386.png)





![image-20200416135007281](images/image-20200416135007281.png)



* 실행결과 : 액션바와 차이가 없는 것처럼 느껴진다.

![image-20200416134939716](images/image-20200416134939716.png)







* ActionBarNavi

![image-20200416142302005](images/image-20200416142302005.png)

![image-20200416142330382](images/image-20200416142330382.png)

![image-20200416142217483](images/image-20200416142217483.png)

![image-20200416142244797](images/image-20200416142244797.png)







### AppBar



![image-20200416143016083](images/image-20200416143016083.png)

![image-20200416143233038](images/image-20200416143233038.png)

![image-20200416143339501](images/image-20200416143339501.png)

위아래로 당기거나 밀 수 있다.

![image-20200416143425780](images/image-20200416143425780.png)

아까 주석처리한 두 문장을 주석해제 하면, 기존에 있던 맨 위 바는 사라진다.

![image-20200416143610425](images/image-20200416143610425.png)

기존에있던거 CoordinatorLayout 빼고 다 지운담에 appbarLayout 추가할 때 collapsing Toolbar선택하면 끝까지 밀당할 수 잇다.



삭제하고 image Background로 다시 만든다.

![image-20200416143755408](images/image-20200416143755408.png)



소스코드 와서

![image-20200416143932952](images/image-20200416143932952.png)

* 이 때, Toolbar import는 `androidx` 이다. 다른 것을 선택하면, 오류가 뜨니 주의할 것!

![image-20200416144050296](images/image-20200416144050296.png)









![image-20200416144310404](images/image-20200416144310404.png)

![image-20200416144443157](images/image-20200416144443157.png)

![image-20200416144630807](images/image-20200416144630807.png)

![image-20200416144646116](images/image-20200416144646116.png)

![image-20200416144844245](images/image-20200416144844245.png)



----



![image-20200416150401802](images/image-20200416150401802.png)

![image-20200416150734317](images/image-20200416150734317.png)

![image-20200416151944427](images/image-20200416151944427.png)

![image-20200416152003432](images/image-20200416152003432.png)

![image-20200416152019052](images/image-20200416152019052.png)





![image-20200416152334992](images/image-20200416152334992.png)

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.coordinatorlayout.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"


    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <com.google.android.material.appbar.AppBarLayout
        android:id="@+id/appbar"

        android:layout_height="192dp"
        android:layout_width="match_parent">

        <com.google.android.material.appbar.CollapsingToolbarLayout
            android:id="@+id/toolbar_layout"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:contentScrim="?attr/colorPrimary"
            app:layout_scrollFlags="scroll|exitUntilCollapsed"

            app:layout_scrollInterpolator="@android:anim/decelerate_interpolator"
            app:toolbarId="@+id/toolbar">

            <ImageView
                android:id="@+id/app_bar_image"
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:scaleType="centerCrop"

                android:src="@android:drawable/sym_def_app_icon"
                app:layout_collapseMode="parallax" />

            <androidx.appcompat.widget.Toolbar
                android:id="@+id/toolbar"
                android:layout_width="match_parent"
                android:layout_height="?attr/actionBarSize"></androidx.appcompat.widget.Toolbar>
        </com.google.android.material.appbar.CollapsingToolbarLayout>
    </com.google.android.material.appbar.AppBarLayout>

    <androidx.core.widget.NestedScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"


        android:fillViewport="true"
        app:layout_behavior="com.google.android.material.appbar.AppBarLayout$ScrollingViewBehavior">

        <ListView
            android:id="@+id/mylistview"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />
    </androidx.core.widget.NestedScrollView>

    <com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/fab"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom|end"
        android:layout_margin="16dp"
        android:src="@android:drawable/ic_input_add" />"

</androidx.coordinatorlayout.widget.CoordinatorLayout>
```





```java
package multi.android.material_design_pro.appbar;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;
import androidx.appcompat.widget.Toolbar;

import android.content.DialogInterface;
import android.graphics.Color;
import android.os.Bundle;
import android.view.Gravity;
import android.view.LayoutInflater;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.EditText;
import android.widget.ImageView;
import android.widget.ListView;


import com.google.android.material.appbar.CollapsingToolbarLayout;
import com.google.android.material.floatingactionbutton.FloatingActionButton;

import java.util.ArrayList;

import multi.android.material_design_pro.R;

public class AppbarTest extends AppCompatActivity {

    Toolbar toolbar;
    ImageView app_bar_image;
    CollapsingToolbarLayout toolbarLayout;
    FloatingActionButton fab;
    ListView listView;
    ArrayList<String> datalist = new ArrayList<String>();

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_appbar_test);
        toolbar = findViewById(R.id.toolbar);
        app_bar_image = findViewById(R.id.app_bar_image);
        toolbarLayout = findViewById(R.id.toolbar_layout);
        fab = findViewById(R.id.fab);
        listView = findViewById(R.id.mylistview);

        //앱바 이미지 변경
        app_bar_image.setImageResource(R.drawable.lee);

        //1. Appbar에 텍스트 추가, 변경
        toolbar.setTitle("툴바입니다.");
        toolbarLayout.setCollapsedTitleTextColor(Color.CYAN);
        toolbarLayout.setExpandedTitleColor(Color.WHITE);

        toolbarLayout.setCollapsedTitleGravity(Gravity.CENTER);
        toolbarLayout.setExpandedTitleGravity(Gravity.RIGHT+Gravity.TOP);//오른쪽 위. 상수라서 +로 연결

        ArrayAdapter<String> adapter = new ArrayAdapter<String>(this,
                android.R.layout.simple_list_item_1,
                android.R.id.text1,
                datalist);
        listView.setAdapter(adapter);

        //FloatingActionButton을 눌렀을 때 대화상자가 뜨고 입력한 데이터가 리스트뷰에 추가되도록 구현
        fab.setOnClickListener(new View.OnClickListener(){


            @Override
            public void onClick(View v) {
                AlertDialog.Builder builder =
                        new AlertDialog.Builder(AppbarTest.this);
                //AlertDialog의 타이틀을 정의
                builder.setTitle("데이터입력");

                //AlertDialog에 보여질 화면을 inflate
                LayoutInflater inflater = getLayoutInflater();
                View dialogView = inflater.inflate(R.layout.input, null);//뷰를 따로 만들어 작업

                //AlertDialog에 추가할 버튼을 정의
                builder.setPositiveButton("확인", new DialogListener());
                builder.setNegativeButton("취소",new DialogListener());
                //AlertDialog에 화면 설정. 붙이기
                builder.setView(dialogView);
                builder.show();

            }
        });



    }

    class DialogListener implements DialogInterface.OnClickListener{

        @Override
        public void onClick(DialogInterface dialog, int which) {
            //AlrtDialog에서입력하는 내용을 ListView에 추가하기
            AlertDialog inputAlert = (AlertDialog)dialog;
            EditText input = inputAlert.findViewById(R.id.input);
            String data = input.getText().toString();
            datalist.add(data);

            //ArrayList에 데이터를 추가한 후 adapter가 갖고 있는 데이터를 업데이트
            //=> Adapter에게 데이터가 변경되었음을 알려주는 작업
            ArrayAdapter<String> adapter = (ArrayAdapter<String>)listView.getAdapter();
            adapter.notifyDataSetChanged();
        }
    }
}
```





내가 다이얼로그에 작성한 텍스트가 노출됨

![image-20200416160349537](images/image-20200416160349537.png)







---

### TabTest2

![image-20200416160449816](images/image-20200416160449816.png)



* ChildFragment라는 Fragment 파일을 만든다.

![image-20200416171656371](images/image-20200416171656371.png)



Activity랑 통신할 수 있게끔

* TabTest2.java

![image-20200416171411930](images/image-20200416171411930.png)

![image-20200416171509442](images/image-20200416171509442.png)



* fillViewPoint를 반드시 true로 걸어줘야 내용을 볼 수 있다.

![image-20200416164343127](images/image-20200416164343127.png)



* 실행 결과

  ![image-20200416171715475](images/image-20200416171715475.png)

![image-20200416171733043](images/image-20200416171733043.png)
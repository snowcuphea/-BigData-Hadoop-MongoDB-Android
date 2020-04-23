

`Alt+shift+enter` : import 단축키

![image-20200324151910138](images/image-20200324151910138.png)

this를 치면 앞에 context : 가 붙ㄴ즌데, 

context자리에 this가 전달되었다는 뜻이다.

![image-20200324152056897](images/image-20200324152056897.png)

버튼 클릭 시 Toast효과 길게 보여준다.

![image-20200324152159075](images/image-20200324152159075.png)

![image-20200324152209369](images/image-20200324152209369.png)

onclick을 클릭해 목록을 보면, 내가 작성한 myclickmethod가 있음을 확인할 수 있다. 내가만든 메소드를 선택하고, 저장한 뒤 실행해보자.

![image-20200324152348038](images/image-20200324152348038.png)

OK 버튼을 누르니 내가 작성한 메소드의 동작이 수행된다.





## Log.d 활용

![image-20200324161304515](images/image-20200324161304515.png)



sysout은 잘 안보인다. 따라서 `Log.d` 함수를활용한다.

저렇게 작성 후 실행하고, logcat 화면을 본다.

logcat 화면에 내가 설정해 준 tag 이름을 치면, 메세지를 확인할 수 있다.

![image-20200324161402218](image-20200324161402218.png)







![image-20200324162155784](images/image-20200324162155784.png)



![](images/image-20200324162122021.png)

이렇게 총 5개의 메소드를 오버라이드 한다ㅏ.



메소드를 오버라이드 한 뒤, 각 메소드에 Log.d 코드를작성해준다. 

![image-20200324162723584](images/image-20200324162723584.png)



실행하면

![image-20200324162750466](images/image-20200324162750466.png)

log를 보면 onCreate -> onStart -> onResume 메소드가 호출되었다.

![image-20200324162901554](images/image-20200324162901554.png)

얘를 누르면, 

![image-20200324162922922](images/image-20200324162922922.png)

onPause -> onStop이 실행되었다.

화면 중지하고다시 들어오면 , onStop -> onResume()

![image-20200324163259953](images/image-20200324163259953.png)

종료 시 onPause->onStop->onDestroy
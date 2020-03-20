![image-20200318170356716](images/image-20200318170356716.png)

![image-20200318170535996](images/image-20200318170535996.png)

![image-20200318170550342](images/image-20200318170550342.png)

![image-20200318170603920](images/image-20200318170603920.png)

![image-20200318170617450](images/image-20200318170617450.png)





https://rstudio.com/products/rstudio/download/

R을 편리하게 쓸 수 있도록, Rstudio라는 프로그램을 사용한다. 

설치할 때 한글이나 어느 특수문자나 공백이 들어가서는 안된다.(경로 포함)

![image-20200319093441100](images/image-20200319093441100.png)

program files 하면 공백이 있으므로, 내가 별도로 지정한 폴더에 설치를 한다. 

![image-20200319093649126](images/image-20200319093649126.png)

![image-20200319093702986](images/image-20200319093702986.png)

![image-20200319093718433](images/image-20200319093718433.png)



R 스튜디오 설치

![image-20200319094515325](images/image-20200319094515325.png)

R이 설치된 곳과 동일한 경로를 설정해준다. 



RStudio를 실행할 때에는 항상 관리자권한으로 실행될 수 있도록 설정한다.

![image-20200319094857495](images/image-20200319094857495.png)



RStudio 아이콘 >속성 > 

![image-20200319095102924](images/image-20200319095102924.png)

![image-20200319095132864](images/image-20200319095132864.png)

---

R 스튜디오 실행



![image-20200319100445477](images/image-20200319100445477.png)



상단 Tools > Global Options > Appearnace 에서 폰트나 테마를 변경할 수 있다.



![image-20200319100719253](images/image-20200319100719253.png)



![image-20200319100905933](images/image-20200319100905933.png)

실행을 한줄한줄 하는것이 불편해서, 키보드 단축키를 이용해서 실행한다.

ctrl + 엔터 하면 실행시킬 수 있다.

* `ctrl + enter `: 실행

* `ctrl +L ` : 콘솔 로그 삭제

![image-20200319101316629](images/image-20200319101316629.png)



![image-20200319101753859](images/image-20200319101753859.png)

* `?` 를 치고 print를 적은 뒤 실행시키면, help 탭에 정보가 나온다.
* `ctrl + 숫자1,2` : 현재 활성화된 창이 바뀐다. 



File > new Project > New directory > new project > 

![image-20200319102112996](images/image-20200319102112996.png)

![image-20200319102337102](images/image-20200319102337102.png)

![image-20200319102344612](images/image-20200319102344612.png)

![image-20200319102508704](images/image-20200319102508704.png)

![image-20200319103134799](images/image-20200319103134799.png)

![image-20200319103242192](images/image-20200319103242192.png)

![image-20200319103259647](images/image-20200319103259647.png)





![image-20200319103429494](images/image-20200319103429494.png)

전체선택(`shift+home키` ) 후 `shift+"` 하면

![image-20200319103523386](images/image-20200319103523386.png)



* `alt+ -` : 변수대입 (<-) 단축키



* class

![image-20200319104623247](images/image-20200319104623247.png)

![image-20200319104637176](images/image-20200319104637176.png)



----





## Vector



![image-20200319110841104](images/image-20200319110841104.png)

![image-20200319110851279](images/image-20200319110851279.png)



![image-20200319111113724](images/image-20200319111113724.png)

![image-20200319111127768](images/image-20200319111127768.png)





`c()` : combine. 여러 개의 변수를 넣는다.

![image-20200319111651637](images/image-20200319111651637.png)

오류가 난 상황. '+' 기호가 나오고 빠져나가는방법은, 오류를 수정해주거나 또는 콘솔창 아무데나 클릭하고 esc 누르기

![image-20200319111835485](images/image-20200319111835485.png)



---

![image-20200319130002483](images/image-20200319130002483.png)

![image-20200319130107817](images/image-20200319130107817.png)





![image-20200319130130230](images/image-20200319130130230.png)

![image-20200319130156989](images/image-20200319130156989.png)





![image-20200319130221485](images/image-20200319130221485.png)

![image-20200319130253705](images/image-20200319130253705.png)



## matrix

![image-20200319131630097](images/image-20200319131630097.png)

![image-20200319131558800](images/image-20200319131558800.png)

![image-20200319132001157](images/image-20200319132001157.png)

![image-20200319132102492](images/image-20200319132102492.png)

![image-20200319132127909](images/image-20200319132127909.png)



![image-20200319132225466](images/image-20200319132225466.png)



![image-20200319132559230](images/image-20200319132559230.png)

![image-20200319133300012](images/image-20200319133300012.png)

![image-20200319133331378](images/image-20200319133331378.png)



컬럼, 로우에 이름 표시

![image-20200319133632417](images/image-20200319133632417.png)

![image-20200319133659955](images/image-20200319133659955.png)



* 행, 열 바꾸기
* `저장할matrix변수 <- t(기존Matrix명)` 

![image-20200319150903060](images/image-20200319150903060.png)







## dataframe



### 1. Matrix를 dataframe으로 변환



```R
만들 변수명 <- data.frame(행렬명)
```

![image-20200319143146507](images/image-20200319143146507.png)

![image-20200319143201256](images/image-20200319143201256.png)



* 타입 변경

![image-20200319143949584](images/image-20200319143949584.png)

![image-20200319144004838](images/image-20200319144004838.png)



![image-20200319144026784](images/image-20200319144026784.png)

![image-20200319144044369](images/image-20200319144044369.png)

![image-20200319144105861](images/image-20200319144105861.png)



* 열 추가

![image-20200319144233098](images/image-20200319144233098.png)

![image-20200319144255047](images/image-20200319144255047.png)



* matrix로 변환

![image-20200319144306679](images/image-20200319144306679.png)

![image-20200319144316045](images/image-20200319144316045.png)



### 2. 벡터를 여러 개 만들어서 dataframe을 작성 

![image-20200319144649343](images/image-20200319144649343.png)

![image-20200319144702457](images/image-20200319144702457.png)

![image-20200319144812438](images/image-20200319144812438.png)

![image-20200319144819778](images/image-20200319144819778.png)



### 3. dataframe을 직접 정의

![image-20200319145110965](images/image-20200319145110965.png)

![image-20200319145013069](images/image-20200319145013069.png)



* 행, 열 바꾸기

![image-20200319151025028](images/image-20200319151025028.png)

![image-20200319151039562](images/image-20200319151039562.png)







## 제어구문

###  if

* 자바와 사용법 같다.

![image-20200319153809520](images/image-20200319153809520.png)

![image-20200319153820015](images/image-20200319153820015.png)



### for

![image-20200319154103170](images/image-20200319154103170.png)



![image-20200319154919010](images/image-20200319154919010.png)

![image-20200319154930251](images/image-20200319154930251.png)



## 파일 입출력

* 읽기

  ```
  변수명 <-read.csv("csv파일명")
  ```

![image-20200319161938552](images/image-20200319161938552.png)

![image-20200319162034546](images/image-20200319162034546.png)



* 쓰기

  ```
  write.csv(데이터변수명,file="생성할파일명")
  ```

![image-20200319162058339](images/image-20200319162058339.png)







---

## 실습

csv_exam.csv를 읽어서 데이터를 수정한 후 csv_exam_result.csv로 저장하기

- science가 80이상인 데이터를 추출
- 추출된 데이터에 mytotal과 myavg컬럼을 추가
- mytotal: 모든 과목의 총점
- myavg: 모든 과목의 평균

![image-20200319171906105](images/image-20200319171906105.png)

![image-20200319171917084](images/image-20200319171917084.png)



선생님 답안

`as.numeric(매개변수)` : 숫자데이터가 아닐 경우, 괄호 안 매개변수를 숫자형으로 바꿈

![image-20200320093610573](images/image-20200320093610573.png)



----

## 





## 
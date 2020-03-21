## Apply_Test : Apply는 반복작업을 할 수 있다.

data(package="MASS") 하면 R내부의 샘플데이터셋을 볼 수 있다.

![image-20200321132400939](images/image-20200321132400939.png)

![image-20200321132334872](images/image-20200321132334872.png)



Boston이라는 샘플데이터를 확인해보았다.

![image-20200321132646248](images/image-20200321132646248.png)

![image-20200321132650819](images/image-20200321132650819.png)



![image-20200321132728993](images/image-20200321132728993.png)



이렇게 데이터를 추출해서 변수에 저장할 수 있다.

![image-20200321132839699](images/image-20200321132839699.png)

![image-20200321132850760](images/image-20200321132850760.png)





* 반복작업을 할 때 사용할 수 있도록 함수를 지원

* 속성에서 MARGIN:1 =>행방향, 2:열방향

  df[,"total"] <- apply(x=내가만들어놓은데이터셋.데이터프래임 )])

행방향으로 total, vg이라는 컬럼에 합계와 평균이가 생김을 확인할 수 있다.

![image-20200321133520797](images/image-20200321133520797.png)

![image-20200321133533664](images/image-20200321133533664.png)

이번엔 열방향으로 구한다.

![image-20200321133556340](images/image-20200321133556340.png)

![image-20200321133607806](images/image-20200321133607806.png)



*  round : 소수점 이하 5번째자리에서 반올림

![image-20200321133701003](images/image-20200321133701003.png)

![image-20200321133713129](images/image-20200321133713129.png)



* sapply : apply의 margin속성을 2로 정의

![image-20200321133830487](images/image-20200321133830487.png)

![image-20200321133840468](images/image-20200321133840468.png)



![image-20200321133946274](images/image-20200321133946274.png)

![image-20200321133934574](images/image-20200321133934574.png)













## Filter : 데이터 정제, 이상데이터 잘라내기



dplyr 패키지는 문자열이나 데이터를 정제하는 데 필요한 기능이 많이 들어있다.

![image-20200321134548240](images/image-20200321134548240.png)

![image-20200321134830209](images/image-20200321134830209.png)



* 조건을 만족하는 데이터 출력

  ![image-20200321135022810](images/image-20200321135022810.png)

![image-20200321135033243](images/image-20200321135033243.png)

![image-20200321135055134](images/image-20200321135055134.png)

![image-20200321135100592](images/image-20200321135100592.png)

![image-20200321140800290](images/image-20200321140800290.png)

위와 같이 다양한 조건연산을 수행할 수 있다.



R에서 지원되는 연산자 중에서, `%` 를 붙여야 하는 연산자들이 있다.

* `%in` 

![image-20200321140825340](images/image-20200321140825340.png)

![image-20200321140845665](images/image-20200321140845665.png)

![image-20200321141014139](images/image-20200321141014139.png)

이렇게 해도 결과가 같다. 열의 개수가 나온다. 

![image-20200321141110889](images/image-20200321141110889.png)

![image-20200321141117299](images/image-20200321141117299.png)







![image-20200321141144943](images/image-20200321141144943.png)

![image-20200321141152468](images/image-20200321141152468.png)



* `ctrl + shift + m` : 자동으로 `%>%` 나온다.

```R
조건 %>% 조건 %>% 조건 %>% 조건 %>% 조건 %>%
```



![image-20200321142533900](images/image-20200321142533900.png)

![image-20200321142541721](images/image-20200321142541721.png)

* select 

![image-20200321143103051](images/image-20200321143103051.png)



* arrange 

![image-20200321142804290](images/image-20200321142804290.png)

![image-20200321142832987](images/image-20200321142832987.png)





![image-20200321143400426](images/image-20200321143400426.png)

![image-20200321143354400](images/image-20200321143354400.png)



![image-20200321143717563](images/image-20200321143717563.png)

![image-20200321143724442](images/image-20200321143724442.png)



* mutate

**![image-20200321143845697](images/image-20200321143845697.png)**

![image-20200321143852373](images/image-20200321143852373.png)



![image-20200321143930937](images/image-20200321143930937.png)

![image-20200321143937725](images/image-20200321143937725.png)



* group by, summarise (그룹과 요약)

**![image-20200321144342490](images/image-20200321144342490.png)**

![image-20200321144410926](images/image-20200321144410926.png)



* 데이터 병합 : left_join, right_join

![image-20200321144817989](images/image-20200321144817989.png)

![image-20200321144836290](images/image-20200321144836290.png)







* 데이터셋을 만들 때, Factor로 만들지 않기 위해 속성을 추가할 수 있다.

```R
stringAsFactors = F
```



![image-20200321145216004](images/image-20200321145216004.png)

![image-20200321145228798](images/image-20200321145228798.png)



![image-20200321145247960](images/image-20200321145247960.png)

Factor가 아닌 chr로 저장됨을 확인할 수 있다. 



* `bind_rows`

![image-20200321151123016](images/image-20200321151123016.png)

![image-20200321151129349](images/image-20200321151129349.png)





* ### `str_sub(수정할변수명, end= 잘라낼글자수)` 

```R
#필요없는 문자열을 잘라내기 : end = 3 : 뒤에서 3개를 잘라내기 
url_val <- str_sub(url_val, end= -3)
```

![image-20200321174907386](images/image-20200321174907386.png)





---

### p.150 실습

![image-20200321153605471](images/image-20200321153605471.png)

![image-20200321153653119](images/image-20200321153653119.png)



![image-20200321153612180](images/image-20200321153612180.png)

![image-20200321153711408](images/image-20200321153711408.png)





![image-20200321153623919](images/image-20200321153623919.png)

![image-20200321153732184](images/image-20200321153732184.png)





![image-20200321153634991](images/image-20200321153634991.png)

![image-20200321153753304](images/image-20200321153753304.png)









## Crawl : 웹페이지에서 데이터를 추출(csv저장)



### 정규표현식

![image-20200321162123456](images/image-20200321162123456.png)

![image-20200321162132771](images/image-20200321162132771.png)



* ### 전방탐색 `(?=)` 

![image-20200321162139462](images/image-20200321162139462.png)

![image-20200321162148447](images/image-20200321162148447.png)



![image-20200321162155869](images/image-20200321162155869.png)

![image-20200321162201401](images/image-20200321162201401.png)



($는 의미를 갖고있기때문에, 문자열로 인식시키려면 \\를 두번 앞에 적어준다.)

![image-20200321162207951](images/image-20200321162207951.png)

![image-20200321162213181](images/image-20200321162213181.png)





* ### 후방탐색 `(?<=)`

![image-20200321162429986](images/image-20200321162429986.png)

![image-20200321162436285](images/image-20200321162436285.png)





---

### `paste`

* `paste()` : 벡터를 연결ㄹ해서 하나의 문자열로 생성

```R
str <- c("java","hadoop","R","mongodb")
paste(str,collapse=" ")
#collapse 뒤에 뭘 기준으로 연결할 것인지 적어준다.
```



* `paste0( , )` : 여러 개를 연결하는 것.

```R
paste0(mytext,mytext2)
```

![image-20200321162825636](images/image-20200321162825636.png)



* `gsub("이전문자열","변경될문자열",대상문자열이담긴변수)` : 문자열 변경

```R
data <- gsub("u","U",mytext)

```

![image-20200321163057441](images/image-20200321163057441.png)

mytext의 소문자 "u"가 모두 "U"로 변경되었다.



* `str_trim(문자열이나 변수)` : 공백 제거

```R
str_trim(data)
```

![image-20200321163208422](images/image-20200321163208422.png)

![image-20200321163217137](images/image-20200321163217137.png)



---



mongolite 패키지 설치

![image-20200321163900396](images/image-20200321163900396.png)

url 하나 변수에 저장하고, `readLines`로 읽어내기

![image-20200321164454087](images/image-20200321164454087.png)

url <- "https://www.clien.net/service/group/community?$od=T31&po=0"

여러 가지 정보 확인테스트

![image-20200321164502664](images/image-20200321164502664.png)

![image-20200321164526896](images/image-20200321164526896.png)

![image-20200321165124924](images/image-20200321165124924.png)

![image-20200321165155067](images/image-20200321165155067.png)

여기 추출할 예정 (class가 "subject_fixed" 인 것에 포함된 글들 )



### 조건에 맞는 데이터를 필터링 ex. 공백부분은 제거

* #조건에 만족하는 데이터를 필터링
  #문자열에 패턴을 적용해서 일치여부를 T/F로 리턴



### 데이터 필터링 : title 뽑기

* str_detect(url_data,"subject_fixed")

![image-20200321171152370](images/image-20200321171152370.png)

* `str_detect()` : 

```R
url_data[str_detect(url_data,"subject_fixed")]
```

![image-20200321171425296](images/image-20200321171425296.png)

![image-20200321171210222](images/image-20200321171210222.png)

![image-20200321171938379](images/image-20200321171938379.png)



![image-20200321172205196](images/image-20200321172205196.png)



![image-20200321172252157](images/image-20200321172252157.png)

![image-20200321172227862](images/image-20200321172227862.png)

---

### 데이터 필터링 : 조회 수 뽑기

![image-20200321172946997](images/image-20200321172946997.png)

![image-20200321172959406](images/image-20200321172959406.png)

![image-20200321173054136](images/image-20200321173054136.png)





---

### 데이터 필터링 : url 뽑기

![image-20200321173802092](images/image-20200321173802092.png)



아까 뽑아놓은 subject_fixed 자료의 윗 윗 윗 줄이므로, subject_fixed 로 구한 값을활용해본다.  (윗윗줄 같지만, 사실은 공백때문에 3줄 위다. 이것은 따로 알아낼 방법은 없고 테스트해봐야 한다. )



![image-20200321173927139](images/image-20200321173927139.png)

![image-20200321173934202](images/image-20200321173934202.png)

* `which` : true 인 위치 값만 뽑아낸다. 

![image-20200321174041429](images/image-20200321174041429.png)

![image-20200321174046232](images/image-20200321174046232.png)

여기에다가 `-3` 를 해주면, 각 윗윗줄 값에 해당하는 값이 나올 것이다.

![image-20200321174224996](images/image-20200321174224996.png)

![image-20200321174218672](images/image-20200321174218672.png)



이 값대로 나오도록 변수에 저장해보자

![image-20200321174315348](images/image-20200321174315348.png)

![image-20200321174341744](images/image-20200321174341744.png)

myurl 을 보니, url부분이 나옴을 확인할 수 있다.



여기서 정규표현식을 통해 url만 추출한다.

![image-20200321174709461](images/image-20200321174709461.png)

![image-20200321174829601](images/image-20200321174829601.png)



그 다음은,뒤에 쓸데없는 문자를 지워주고 url 앞에 www같은 것을 붙여서 도메인처럼 보이게 해야한다.



* `str_sub(수정할변수명, end= 잘라낼글자수)` 

```R
#필요없는 문자열을 잘라내기 : end = 3 : 뒤에서 3개를 잘라내기 
url_val <- str_sub(url_val, end= -3)
```

![image-20200321174907386](images/image-20200321174907386.png)

![image-20200321174917536](images/image-20200321174917536.png)

제대로 출력됨을 확인할 수 있다.



지금까지 구한 정보들을 col들로 취합해 csv파일로 생성한다.

#### 컬럼들 합치기 : `변수명 <- cbind(컬럼1,컬럼2,컬럼3)`

![image-20200321175340525](images/image-20200321175340525.png)

![image-20200321175254035](images/image-20200321175254035.png)



그런데..

![image-20200321175635784](images/image-20200321175635784.png)

길이를 확인해보니, hit가 공지사항의 조회수 1건까지 합쳐져서 31개가 나와버렸다.

이런 점들을 주의해서 작업하도록 한다. 



#### 데이터 뽑을 때 키워드 추출하는 방법

![image-20200321175803659](images/image-20200321175803659.png)

Copy Selector :     #div_content > div.list_content > div:nth-child(4) > div.list_hit



![image-20200321175827536](images/image-20200321175827536.png)

Copy XPath :    //*[@id="div_content"]/div[6]/div[4]/div[4]


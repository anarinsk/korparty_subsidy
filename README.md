# korparty_subsidy

[Jun Sok Huhh](mailto:anarinsk@gmail.com)

#  분석 목적 

* 이 분석은 선관위에 올라온 [자료](https://t.co/JgDId3DCN1)를 바탕으로 만들어 졌습니다. 
* 저는 선거 지원금 제도에 대해서 아는 바가 거의 없습니다. 잘못 처리된 부분이 있거나 오해가 있으면 알려주시면 수정하도록 하겠습니다. 
* 이하는 반말로 전개됩니다. 

# 분석 내용 

[read_EDA.ipynb](https://github.com/anarinsk/korparty_subsidy/blob/master/read_EDA.ipynb)

# 코드 해설 

코드가 몹시 간략함으로 자세한 해설은 생략한다. 

1. python: 선관위 엑셀 자료를 시트 단위로 뜯어내서 tidy로 만든다. 
2.  R: ggplot2로 시각화 한다. 

## What is Tidied 

* 정리된 데이터는 4 컬럼으로 구성되어 있다. 
	1. year: 연도 
	2.  type: 지원금 종류 
	3.  party: 정당 
	4. subsidy: 지원액 
* 정당을 좌/우/중도로 나누어 보는 것이 목적이었기 때문에 2001년부터 기록된 정당을 분류할 필요가 있다. 
	* 내부에서 `DF_info`라는 pandas 테이블을 하나 만들었다. 한글 위키에 기반해 만든 자료이고, 혹시 잘못 분류한 내용이 있다면 알아서 고쳐 쓰시라. 

## python + R 

* 원래 python으로 쭉 그릴까 했다. 그런데,  matplotlib이나 seaborn 모두 R의 ggplot2에 비하면 뭔가 살짝 부족하고 불편하고 했다. 
* 그래서 `rpy2` 라이브러리를 설치해  R을 불러와 ggplot2로 시각화만 완성했다. 

# 몇 가지 사족 

* 제발 엑셀로 문서 만드시는 분들은 장식 좀 하지 마라! 엑셀은 계산이나 쿼리를 위한 도구지 비주얼 툴이 아니다. 
	* [이 아티클](https://www.tandfonline.com/doi/full/10.1080/00031305.2017.1375989) 숙독을 권장한다. 
* 어떤 레코드를 넣을 때 앞에 어떻게 표기되어 있는지 확인하시고 넣으시라.
	* 장식하신다고 "정당 보조금"을 엑셀에서 줄을 바꿔서 "정    당 \n 보  조  금"이라고 넣으시면 대략 좌절... 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM4NDA3MzAxNywtNjU0Mzk1NDI3LC04MD
I0Nzg4LDkzNDMyOTMxM119
-->

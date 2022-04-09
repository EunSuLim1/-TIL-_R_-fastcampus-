# -TIL-_R_-fastcampus-
fastcampus 강의 : 데이터분석 패키지중.

1. Select 
원하는 컬럼 불러오기

예시

'''
R
info %>% 
  select(cust, state)'''
  
컬럼이름이 길다면, 컬럼 번호로 불러올수 있음

'''R
info %>%
  select(3,4)'''
  
컬럼의 이름 일부분으로 불러오기

'a' 로 시작하는 컬럼
select(stats_with('a'))
'b'로 시작하는 컬럼
select(end_withs('b'))
'c'가 포함된 컬럼
select(contain('t'))



2. 데이터 그룹, 집계
Group_by(컬럼명) 데이터 값을 묶어줌
Surmmarise(새로운 컬럼명 = 집계함수(컬럼명)) 그룹핑한 값에서 sum, max, min, n(row 개수), 등 요약값을 구해서 데이터를 파악함

# 2-1 Group_by 그룹핑

ord %>%
  filter(cd %in% c(''25601','25602')) %>%
  select(cd, catg1,catg1) %>%
  group_by(cd) %>%
  summarise(sum_amt = sum(amt), n = n(), agv_amt = avg(amt))
  
 ## cd 컬럼에서 '25601'또는'25602'를 필터해라(filter) -> cd, catg1, catg1 컬럼을 불러와라(select) -> cd 컬럼의 값을 그룹핑하고 (group_by) ->  amt의 합계: sum(amt)를 sum_amt 컬럼명으로 만들어라...등등
  

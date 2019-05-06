# R-code-for-finance
R code for finance <br>
주식, 재무표, 데이터를 위해 만든 repo입니다. 


# 2019.05.06 UPDATE
1. 중국상장기업목록이 업로드 되었습니다.
- 전 중국종목의 간략한 기업정보와 종목코드를 제공합니다 <br>

# 2019.04.28 UPDATE
1. 중국상장기업 기업정보가 업로드 되었습니다.
- 중국상장기업의 기본재무정보, 뉴스 및 공시, 주가정보를 제공합니다 <br>
- 이용방법은 아래 '코드이용방법'을 참고하시기 바랍니다 <br>

# 2019.04.19 UPDATE
1. 마감시황 업데이트 되었습니다.
- 금/은 시세란에 오류가 걸려 뜨지 않던 에러를 "이용할 수 없음"으로 대체하였습니다 <br>

2. 한국기업정보코드가 업데이트 되었습니다.
- 주가차트에 기업명이 뜨도록 수정하였습니다 <br>
- 기업정보에 기존에 없었던 "뉴스 및 공시" 란을 추가하였습니다.<br>
  ㄴ 최대 5개의 뉴스 및 공시가 뜨도록 추가하였습니다.<br>

# 2019.04.12 UPDATE
1. 마감시황 업데이트 되었습니다.
- DATE에러로 인해 마감시황이 뜨지 않던 에러를 해결하였습니다 <br>
- 마감시황 상단에 국제주요뉴스 및 한국주요뉴스의 헤드라인이 뜨도록 수정하였습니다<br> 
  ㄴ 비교적 마감시황이 늦게 올라와 불편을 조금 더 해소하고자 헤드라인을 추가하였습니다.<br>

# 2019.01.03 UPDATE
1. 마감시황 업데이트 되었습니다.
- 2019년 이후 외국시장의 시황이 뜨지 않던 문제를 해결하였습니다.<br>
- 금, 은 시황의 path가 바뀌어 시황이 뜨지 않던 문제를 해결하였습니다. <br>

#현재 홍콩재무제표는 사용이 불가한 상태입니다. 하루 빨리 수정하도록 하겠습니다 <br>

# 코드 이용방법
- 중국상장기업목록은 중국 본토 내 상장되어 있는 전 기업의 간단한 정보를 제공합니다. <br>
- function화 시켜 SHSZ_table()로 작동하고, csv파일로 저장하고 싶으면 SHSZ_table(save_csv_file=TRUE)를 입력하시면 됩니다 <br>
- 시간이 오래걸리므로 sheet만 참고하고 싶으시면 https://docs.google.com/spreadsheets/d/1AxvMtxLIJUWyfXUgM_LLo5XV5Bj7ODqcu6JMEtBelE4/edit?usp=sharing 를 보시면 됩니다.

- 중국상장기업 기업정보는 중국 A주에 상장되어있는 기업의 정보를 제공합니다. 이용방법 : 예)cn_get_st('000002') <br>
- A주종목을 대상으로 하였으므로 "2" 혹은 "9"로 시작하는 B주 종목코드는 실행이 불가합니다 <br>

- 마감시황은 현재 미국, 중국, 일본, 대만, 한국, WTI, 금/은 시황을 제공하며, 일 거래 그래프도 함께 제공됩니다. 마감시황에서 뜨는 plot과 가격, 가격변동(chg)은 실시간 value를 제공하며, 미국과 WTI를 제외한 나머지 시황은 오후5시에 제공됩니다.(사이트의 사정에 따라 시황이 뜨는 시간이 다를 수 있습니다.) <br>

- 홍콩상장기업 재무제표와 중국상장기업 제무제표는 홍콩재무제표, 중국재무제표를 나타냅니다. <br>

- 홍콩상장기업 재무제표와 중국상장기업 재무제표 내 주식코드 테이블은 그냥 참고용이지, function과는 독립적이므로 원치 않으신 분들은 function만 import해도 됩니다. <br>

- 중국상장기업 재무제표 이용방법 : cn_fs('코드번호') ex) cn_fs('000002') <br>

- KRX종목 테이블 사용법 : 콘솔창에 krx_stock_table()을 치면 전 종목이 테이블 형태로 띄어 집니다. krx_stock_table(save_csv_file = TRUE)을 입력하실 경우, 전 종목이 띄어짐과 동시에 csv파일로 기본 디렉토리에 저장됩니다(파일명:KRX__테이블.csv)
krx_stock_table('kospi')를 입력하실 경우, kospi종목만, krx_stock_table('kosdaq')을 입력하실경우 kosdaq종목만, krx_stock_table('konex')를 입력하실 경우, konex종목만 띄우도록 수정하였습니다. 시장 명 뒤에 TRUE를 넣을 경우 csv파일로 저장됩니다, 예) krx_stock_table('kospi',TRUE)

- k-score는 알트만의 z-core를 본 떠 만든 한국형 모델 k-score입니다. 상장되어 있는 전 종목에 이 모델을 적용시키는 코드이며, 한눈에 기업의 부실정도를 측정가능하도록 하는 모델입니다.<br>
reference: <br>
[1] https://m.blog.naver.com/PostView.nhn?blogId=haan79&logNo=10158008764&proxyReferer=https%3A%2F%2Fwww.google.co.kr%2F<br>
[2] https://finata.blog.me/221191125946

- 한국상장기업 기업정보는 한국 상장기업에 대한 기본 정보를 제공합니다. 코드이용방법 : kr_get_st('6자리코드') 예) kr_get_st('005930')<br>


# E-commerce CRM 전략: 배송 지연 VIP 리텐션 방어 프로젝트
데이터 분석을 활용해 배송 운영 리스크를 마케팅 기회로 전환 -> 예상 ROI 3.85배 회복 캠페인 제안

## 프로젝트 배경 및 문제 정의
본 프로젝트는 
- 데이터셋: Olist 이커머스 공개 데이터 (약 10만 건의 주문 데이터)
- 문제 상황: 배송 지연이 발생할 때 단순히 리뷰 점수만 낮아지는 것이 아니라, 가장 가치 있는 고객층인 VIP의 재구매율(Retention)이 하락하는 현상 포착
- 목표: 지연 경험 VIP를 위한 개인화 오퍼를 설계하고, 캠페인 집행 시의 경제적 타당성(ROI)을 검토

## 핵심 데이터 인사이트 (시각화 정리)
# 배송 지연이 리텐션에 미치는 치명적 영향
<img width="609" height="548" alt="on-time vs delayed" src="https://github.com/user-attachments/assets/deb44134-8681-464d-bff7-994b4f1b7909" />
인사이트: 정시 배송 시 22.72%였던 VIP 재구매율이 지연 발생 시 21.51%로 약 1.21%p 하락함을 확인하였다.
의미: VIP 집단의 미세한 이탈은 장기적으로 거대한 LTV(고객 생애 가치) 손실을 야기한다.

# 지연 일수와 리뷰 점수의 상관관계
<img width="826" height="470" alt="review score by delivery delay days" src="https://github.com/user-attachments/assets/adf109d1-27b6-43e6-8cec-24f0858036d3" />
인사이트: 배송 지연이 시작되는 0일(정시)을 기점으로 리뷰 점수가 급격히 하락하며, 5일 이상 지연 시 평균 점수가 2.0점 이하로 추락하였다.

# 집중 관리 카테고리 식별
<img width="1140" height="684" alt="top 10 critical categories for vips" src="https://github.com/user-attachments/assets/ae9a021e-b404-4bc7-9147-f1587ae447f7" />
인사이트: bed_bath_table, health_beauty 등 고단가 및 반복 구매가 잦은 카테고리에서 지연 영향이 가장 큼을 확인하여 우선순위 타겟 설정

## CRM 액션 플랜: Recovery Campaign
# 시나리오별 ROI 시뮬레이션

캠페인 비용 대비 방어 매출을 계산하여 가장 효율적인 'Base' 시나리오를 채택하였다.
| 시나리오 | 쿠폰 단가 | 예상 전환율 | 예상 비용 | 방어 매출 | ROI |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Conservative** | 10 BRL | 15.0% | 14,410 BRL | 62,394.85 BRL | 4.33배 |
| **Base (채택)** | **15 BRL** | **20.0%** | **21,615.00 BRL** | **83,193.13 BRL** | **3.85배** |
| **Aggressive** | 20 BRL | 25.0% | 28,820.00 BRL | 103,991.41 BRL | 3.61배 |

# 개인화 메시지 설계 (Targeting List)
# 지연 심각도(Risk Level)와 구매 카테고리를 결합한 1:1 개인화 오퍼 생성.

- Critical (7일 이상 지연): VIP 20% 특별 할인권 발송

- Warning (0~7일 지연): 감사 10% 쿠폰 발송

## 사용 기술 및 방법론
Language: Python

Segmentation: RFM (Recency, Frequency, Monetary) Scoring

Analysis: Pandas, Matplotlib, Seaborn

Impact Metric: RFM Customer Segmentation(고가치 고객군 정의),

Causality Analysis(배송 지연과 리텐션 간의 인과관계 규명),

Prescriptive Analytics(ROI 시뮬레이션을 통한 실행 가능한 전략(Action Plan) 도출)

## Author
김승우

GitHub: https://github.com/SeungwooKim525  

# E-commerce CRM 전략: 배송 지연 VIP 리텐션 방어 프로젝트
데이터 분석을 활용해 배송 운영 리스크를 마케팅 기회로 전환 -> 예상 ROI 3.85배 회복 캠페인 제안

## 프로젝트 배경 및 문제 정의
### 데이터셋
- Olist 이커머스 공개 데이터 (약 10만 건의 주문 데이터) 사용

### 문제정의
배송 지연 → 고객 경험 악화 → 고가치 고객(VIP) 이탈으로 이어지는 구조적 손실을 정량화하고, 이를 방어하기 위한 데이터 기반 CRM 전략을 수립

- 배송 지연 현황: 전체 주문 중 약 7.3%에서 배송 지연 발생 (평균 리뷰 점수 4.2 → 2.2로 급락)

- VIP 리텐션 충격: RFM 기반 상위 고객군(VIP) 분석 결과, 지연 경험 시 재구매율이 22.72%에서 21.51%로 1.21%p 감소 (기존 대비 약 5.3% 하락)

- CRM 개입의 필요성: 배송 인프라 개선은 장기적 과제이나, 당장 발생하는 VIP 고객 생애 가치(LTV) 손실을 방어하기 위해 즉각적인 마케팅적 보상(Retention Campaign)이 필수적이다.

# 핵심적인 데이터 인사이트 (시각화 정리)
## 배송 지연이 리텐션에 미치는 치명적 영향
<img width="609" height="548" alt="on-time vs delayed" src="https://github.com/user-attachments/assets/deb44134-8681-464d-bff7-994b4f1b7909" />

인사이트: 정시 배송 시 22.72%였던 VIP 재구매율이 지연 발생 시 21.51%로 약 1.21%p 하락함을 확인하였다.
의미: 단 1.21%p의 차이지만, 구매 단가가 높은 VIP 구간에서는 연간 수천만 원 규모의 잠재적 매출 손실로 이어질 수 있는 유의미한 수치

## 지연 일수와 리뷰 점수의 상관관계
<img width="826" height="470" alt="review score by delivery delay days" src="https://github.com/user-attachments/assets/adf109d1-27b6-43e6-8cec-24f0858036d3" />

인사이트: 배송 지연이 시작되는 0일(정시)을 기점으로 리뷰 점수가 급격히 하락하며, 5일 이상 지연 시 평균 점수가 2.0점 이하로 추락하였다.

## 집중 관리 카테고리 식별
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

Base 시나리오 선택 이유
1. 효율과 규모의 균형 : Conservative 대비 전환율을 5%p 높이면서도, 3.85배라는 높은 수익성을 유지
2. 한계 효용 고려 : Aggressive 시나리오는 매출 방어 규모는 크지만, 쿠폰 비용 증가폭 대비 전환율 상승이 완만해져 마케팅 효율(ROI)이 급격히 감소
3. 리스크 관리 : 15 BRL 수준의 오퍼는 브랜드 이미지를 훼손하지 않으면서도 고객의 부정적 경험을 상쇄할 수 있는 가장 적정한 '심리적 보상 지점'으로 판단됨

# 개인화 메시지 설계 (Targeting List)
# 지연 심각도(Risk Level)와 구매 카테고리를 결합한 1:1 개인화 오퍼 생성.

Critical (7일 이상 지연)
[Category] 지연 사과: VIP 20% 특별 할인권 발송

Warning (0~7일 지연)
[Category] 지연 안내: 감사 10% 쿠폰 발송

# 예시
- **[Critical]** `[bed_bath_table] 지연 사과: VIP 고객님께 진심으로 사과드리며, 20% 특별 할인권이 발송되었습니다.`
- **[Warning]** `[health_beauty] 지연 안내: 배송 지연에 대한 감사의 마음을 담아 10% 쿠폰을 보내드립니다.`

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

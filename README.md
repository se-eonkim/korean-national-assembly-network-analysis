# 20대 / 21대 국회 공동발의 네트워크 분석을 통한 초당적 협력 요인 분석   
*Research Report | Kyung Hee University, 2024*

> 📊 [발표자료 보기](./20%EB%8C%80%2C21%EA%B0%9C%20%EA%B5%AD%ED%9A%8C%20%EA%B3%B5%EB%8F%99%EB%B0%9C%EC%9D%98%20%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%20%EB%B6%84%EC%84%9D_%EB%B0%9C%ED%91%9C%EC%9E%90%EB%A3%8C.pdf)  
> 📄 [보고서 보기](./20%EB%8C%80%2C21%EB%8C%80%20%EA%B5%AD%ED%9A%8C%20%EA%B3%B5%EB%8F%99%EB%B0%9C%EC%9D%98%20%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%20%EB%B6%84%EC%84%9D_%EB%B3%B4%EA%B3%A0%EC%84%9C.pdf)
---

## Overview

대한민국 성인 90%가 정치 갈등을 심각하다고 평가한다.  
21대 국회에서 여야가 함께 발의한 법안은 전체의 **5.7%** — 17대의 55.8%에서 급감했다.

이 연구는 20대/21대 국회 공동발의 데이터를 기반으로  
의원 간 협력 구조를 directed weighted network로 모델링하고,  
**macro(시기·소관위원회)와 micro(노드) 두 관점**에서 초당적 협력 요인을 분석한다.

---

## Research Questions

국회의 *초당적 협력을 이끌어내는 주요 요인은 어떤 것이 있을까?
* 초당적 협력 : 특정 정당의 정치적 입장을 초월하여 여러 정당이 함께 협력하는 것

1. 20대 vs 21대 국회, 협력 구조는 어떻게 달라졌는가?
2. 바른미래당 창당이 초당적 협력에 미친 영향은?
3. 소관위원회별로 초당적 협력의 양상이 다른가?
4. 초당적 협력을 이끄는 핵심 노드는 누구인가?

---

## Network Model

- **Node** — 법안 발의에 참여한 국회의원
- **Edge** — Directed + Weighted  
  공동 발의자 → 대표 발의자 (지지 방향)  
  가중치 = 공동 발의 횟수

<img width="466" height="167" alt="image" src="https://github.com/user-attachments/assets/10d8596e-3dbc-42cd-98c4-2f92db1d79fe" />
<img width="464" height="168" alt="image" src="https://github.com/user-attachments/assets/24376f40-0b92-4655-871e-746604fc975e" />
<img width="464" height="170" alt="image" src="https://github.com/user-attachments/assets/241bc5dc-14ad-4467-a8b4-1dfe519d7bc3" />


---

## Metrics

**1. 최대 modularity 대비 정규화 지표 (직접 설계)**  
시기별 네트워크 특성이 달라 기존 modularity 직접 비교 불가 판단  
→ 최대 modularity로 정규화해 정당 속성의 상대적 영향력 측정

**2. 정당별 혼합성 지수**  
동일 정당 내 협력 vs 타 정당 협력 비율

**3. 정당 간 협력 지수**  
Fowler(2006) 의원 간 협력 지수를 정당 단위로 확장

**4. Shannon Entropy × Betweenness Centrality**  
Shannon Entropy로 의원 단위 협력 다양성 정량화  
→ Betweenness Centrality와 2축 조합으로 허브 노드 유형화
<img width="463" height="170" alt="image" src="https://github.com/user-attachments/assets/987c7cf8-35d6-4bb3-82b6-50b941b59abf" />


---

## Key Findings

**1. 제3지대 정당의 역할 (Macro)**  
바른미래당 창당 후 modularity 비율 0.9944 → 0.9255 감소.  
거대 양당 사이 균형 잡힌 매개 역할 수행 (혼합성 지수 0.3494).  
단, 내부 결속력 부족으로 지속 가능성 확보 실패.

**2. 소관위원회별 초당적 협력 (Macro)**  
정보위원회·여성가족위원회·문화체육관광위원회  
→ 20대/21대 공통으로 낮은 modularity 비율 (초당적 협력 활발).  
정무위원회(금융·경제) → 높은 modularity (당파적 구조).

**3. 초당적 허브 노드 (Micro)**  
Betweenness Centrality 高 + Shannon Entropy 高  
→ 정쟁과 거리를 둔 생활밀착형 법안 중심 의원들이 핵심 역할.

**4. 경력과 초당적 협력 (Micro)**  
5선·6선 중진 의원의 초당적 협력도가  
초선·재선보다 오히려 낮게 나타남.

---

## Limitations

정량적 지표가 실제 정치 행위를 완벽히 반영하지 못하는 한계 존재.  
초당적 협력 촉진 노드로 평가된 의원이  
실제 탄핵 투표에서 다른 행보를 보인 사례 확인  
— 지표와 실제 정치 맥락 간의 괴리.

---

## Tech Stack
- Python, NetworkX, Pandas, Matplotlib
- Data: 열린국회정보 공개포털 OPEN API (20대/21대 공동발의 법안 전수)

---

## Team
소셜네트워크과학 기말 프로젝트 4조  
김상원 · 김세언 · 김형민 (경희대학교, 2024)

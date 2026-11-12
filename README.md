<p align="center">
  <img src="assets/profile-banner.png" alt="Uree1229 · Backend &amp; Data Engineering" width="100%">
</p>

<p align="center">Python으로 데이터 조회 API를 만들고, 페이지 경계와 네트워크 장애에서 데이터 정합성을 검증합니다.</p>

### Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?logo=python&amp;logoColor=white&amp;style=flat-square" alt="Python" height="25">
  <img src="https://img.shields.io/badge/FastAPI-007D73?logo=fastapi&amp;logoColor=white&amp;style=flat-square" alt="FastAPI" height="25">
  <img src="https://img.shields.io/badge/SQLite-0B668E?logo=sqlite&amp;logoColor=white&amp;style=flat-square" alt="SQLite" height="25">
  <br>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&amp;logoColor=171717&amp;style=flat-square" alt="JavaScript" height="25">
  <img src="https://img.shields.io/badge/C-00599C?logo=c&amp;logoColor=white&amp;style=flat-square" alt="C" height="25">
  <img src="https://img.shields.io/badge/C%23-512BD4?style=flat-square" alt="C#" height="25">
  <img src="https://img.shields.io/badge/Linux-FCC624?logo=linux&amp;logoColor=171717&amp;style=flat-square" alt="Linux" height="25">
  <img src="https://img.shields.io/badge/Git-BD3F2A?logo=git&amp;logoColor=white&amp;style=flat-square" alt="Git" height="25">
</p>



## SSAL.gg · 뉴스 이슈 탐색 서비스

여러 매체의 뉴스를 모아 이슈들을 스토리라인으로 묶고, 이슈들을 지도에 연결하고, 보도가 이어진 순서를 타임라인으로 보여줍니다. 

Live Trends에서는 여러 날 이어진 이슈를 찾을 수 있습니다.

<p>
  <a href="https://ssalgg.whitekw.com/live-trends"><img src="https://img.shields.io/badge/Live%20Trends-007D73?style=flat" alt="Live Trends" height="26"></a>
  <a href="https://ssalgg.whitekw.com/issue-map"><img src="https://img.shields.io/badge/Issue%20Map-5946AB?style=flat" alt="이슈 지도" height="26"></a>
  <a href="https://ssalgg.whitekw.com/project-history"><img src="https://img.shields.io/badge/Project%20History-42557A?style=flat" alt="변경 기록" height="26"></a>
</p>

## 다른 프로젝트

### 응급환자 이송 지원 시스템

응급환자 접수, 병원 문의, 목적지 확정, 이송 진행 상황 공유를 지원하는 팀 프로젝트입니다.  
[저장소](https://github.com/Uree1229/emergency-care-system) · [응답 유실 테스트](https://github.com/Uree1229/emergency-care-system/blob/2eaf757/test_patient_workflow_dev1_http.py#L395-L407)

### Linux CPU Load Balancing

CPU 사용 제한을 풀었을 때 한 CPU에 몰렸던 작업을 여러 CPU로 더 빨리 분산하는 방법을 비교한 Linux 커널 실험입니다.  
[커널 패치와 벤치마크](https://github.com/Uree1229/improve-loadbalancing)

### Blind-Match · 의료 유사도 검색

나이와 혈압 같은 환자 특성을 입력하면 가상 환자 기록에서 비슷한 사례를 찾아주는 의료 검색 프로토타입입니다.  
[참고 논문](https://arxiv.org/abs/2408.06167v2)

<details>
<summary>검색 설계와 입력 검증 보기</summary>

- **평문 검색** · 가상 환자 기록 200건을 사용합니다. 나이, 혈압, 콜레스테롤, 심박수의 스케일을 조정하고 L2 정규화합니다. 벡터 내적으로 코사인 유사도를 구해 선택한 K(3·5·10)만큼 반환합니다.
- **암호화 검색 설계** · 원본 수치는 의료기관 내부에 두고, 검색 서버는 CKKS로 암호화된 특징 벡터를 HE-C³로 비교하도록 설계했습니다. 암호문 연산과 복호화는 후속 연동 범위입니다.
- **입력 검증** · `NaN`, 나이 121세, `K=4`, 정규화 전 영벡터에 대해 HTTP `422` 응답을 확인했습니다.

</details>

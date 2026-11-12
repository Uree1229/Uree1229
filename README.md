# Uree1229 · Backend & Data

Python으로 데이터 조회 API를 개발합니다. 검색·정렬·페이지네이션의 경계 조건과, 네트워크 장애 후에도 데이터가 일관되게 남는지 테스트합니다.

## SSAL.gg · 뉴스 이슈 탐색 서비스

최신순 목록에서는 며칠째 이어진 이슈를 찾기 어려웠습니다. Live Trends에 **기간 내 실제 관측일 수** 기준 정렬과 여러 날 관측된 이슈를 고르는 필터를 추가했습니다.

- **구현** · 전체 후보를 필터링하고 정렬한 뒤 50개씩 반환했습니다. 다음 페이지에도 같은 검색·정렬·필터 조건을 적용했습니다.
- **검증** · 60건으로 테스트해 기본 목록의 59·60번째 항목이 정렬 후 첫 페이지 상단에 올라오고, 다음 페이지 10건과 중복되지 않는지 확인했습니다.

[Live Trends](https://ssalgg.whitekw.com/live-trends) · [이슈 지도](https://ssalgg.whitekw.com/issue-map) · [프로젝트 기록 · 11월 8일](https://ssalgg.whitekw.com/project-history)

[![SSAL.gg 이슈 지도](assets/ssal-issue-map.png)](https://ssalgg.whitekw.com/issue-map)

## 다른 프로젝트

### Blind-Match · 의료 유사 사례 검색 프로토타입

가상 환자 기록 **200건**으로 평문 코사인 유사도 Top-K 검색을 구현했습니다. 허용 범위를 벗어난 수치와 잘못된 K에 HTTP 422가 반환되는지 검증했습니다. 원본 수치를 의료기관 내부에 두고 암호화한 벡터로 비교하는 경로는 CKKS와 HE-C³를 적용하도록 설계했습니다.

[참고 논문 · Blind-Match (CIKM 2024)](https://arxiv.org/abs/2408.06167v2)

### 응급환자 이송 지원 시스템 · 환자 등록 재시도

등록은 완료됐지만 응답이 유실되면 앱이 같은 요청을 다시 보낼 수 있습니다. **전송 식별자로 기존 환자 ID를 찾고**, 서버가 서명한 최초 접수 내용만 재시도에서 복원하도록 검증을 보강했습니다.

등록 직후 `URLError`를 주입해 환자 기록과 병원 문의 워크플로가 각각 1건만 남는지 확인했습니다. 별도 테스트에서는 같은 요청을 다시 보내도 기존 환자 ID가 반환되는지 확인했습니다.

[재시도 검증 PR #26](https://github.com/Uree1229/emergency-care-system/pull/26) · [응답 유실 테스트](https://github.com/Uree1229/emergency-care-system/blob/2eaf757/test_patient_workflow_dev1_http.py#L395-L407) · [동일 ID 반환 테스트](https://github.com/Uree1229/emergency-care-system/blob/2eaf757/test_patient_workflow_dev1_http.py#L293-L305)

### Linux CPU Load Balancing

CPU affinity 제한이 풀린 뒤 작업이 다시 분산되는 경로를 분석하고, Linux 5.4 스케줄러 패치 후보를 C 벤치마크로 비교했습니다.

[커널 패치와 벤치마크](https://github.com/Uree1229/improve-loadbalancing)

## 기술 스택

- **Backend** · Python, FastAPI, HTTP API, SQLite
- **Frontend** · JavaScript, Jinja2
- **검증** · HTTP 회귀 테스트, 운영 API 및 브라우저 검증

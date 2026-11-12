# SSAL.gg

여러 매체의 뉴스를 모아 **관련 이슈와 과거 보도**를 함께 탐색할 수 있는 서비스입니다.

[이슈 지도 ↗](https://ssalgg.whitekw.com/issue-map) · [실시간 트렌드 ↗](https://ssalgg.whitekw.com/live-trends) · [뉴스 검색 ↗](https://ssalgg.whitekw.com/search) · [프로젝트 기록 ↗](https://ssalgg.whitekw.com/project-history)

[![SSAL.gg 이슈 지도에서 기사와 이슈가 연결된 화면](assets/ssal-issue-map.png)](https://ssalgg.whitekw.com/issue-map)

### 개발한 기능

- **이슈 지도** · 공통 맥락을 바탕으로 관련 이슈를 잇는 로직을 개선했습니다.
- **아카이브 검색** · 이전에 수집한 기사까지 검색할 수 있도록 검색 범위를 확장했습니다.

---

## 다른 프로젝트

### Blind-Match · 암호화된 의료 유사도 검색

Blind-Match 논문의 **HE-C³**를 분석하고, CKKS로 암호화한 환자 특징 벡터에서 유사 사례를 찾는 흐름을 설계하고 있습니다.

<details>
<summary>검색 흐름 보기</summary>

```mermaid
flowchart LR
    query["암호화된 질의 벡터"] --> match["1:N 유사도 계산"]
    match --> result["점수 복호화 후 Top-K 선택"]
    classDef step fill:#191C33,stroke:#A78BFA,color:#F5F3FF,stroke-width:1px
    class query,match,result step
```

</details>

[참고 논문 · Blind-Match (CIKM 2024) ↗](https://arxiv.org/abs/2408.06167v2)

### 캡스톤 · 응급환자 이송 지원

환자 등록부터 병원 도착까지 이어지는 팀 프로젝트입니다. 등록 응답이 유실된 뒤 재시도해도 같은 환자 ID가 반환되고 환자 레코드가 하나만 남는지 합성 데이터로 검증했습니다.

[프로젝트 저장소 ↗](https://github.com/Uree1229/emergency-care-system)

### Load Balancing · Linux CPU 스케줄러

Linux 5.4에서 CPU affinity 제한이 풀린 뒤 작업이 다시 분산되는 경로를 분석하고, 스케줄러 패치 후보를 벤치마크로 비교했습니다.

[패치와 벤치마크 ↗](https://github.com/Uree1229/improve-loadbalancing)

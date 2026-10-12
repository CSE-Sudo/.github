<div align="center">

<img src="https://raw.githubusercontent.com/CSE-Sudo/on-care/main/docs/assets/oncare-banner.png" alt="On-Care" width="900"/>

<br/><br/>

<h3>PT 회원의 식단·운동 기록을 트레이너의 코칭으로 잇습니다.</h3>

<sub>On-Care turns the days between personal training sessions into coaching a trainer can actually see.</sub>

<br/>

[소개](https://cse-sudo.github.io/on-care/) &nbsp;·&nbsp; [데모 영상](https://youtu.be/C4ivM_dlAww?si=8iOWmOpSxcpQmlU3) &nbsp;·&nbsp; [소스 코드](https://github.com/CSE-Sudo/on-care)

</div>

<br/>

## Why

PT의 성과는 주 1~2회의 대면 세션이 아니라 세션과 세션 사이에서 갈립니다. 헬스장 신규 회원의 63%가 3개월 안에 운동을 그만두고([Sperandei et al., 2016](https://pubmed.ncbi.nlm.nih.gov/26874647/)), 그 사이를 붙잡아 줄 트레이너의 관리는 개인 메신저에 흩어져 기록으로 남지 않습니다.

On-Care 는 회원의 기록을 정리해 트레이너에게 전달하고, 트레이너의 코칭을 다시 회원에게 돌려보냅니다. 트레이너를 AI로 대체하지 않고, 트레이너의 관리를 세션 밖으로 확장합니다.

## Product

| | 대상 | 하는 일 |
| --- | --- | --- |
| **회원 앱** | PT 회원 | 사진 한 장으로 식단을 기록하고, 배정받은 루틴을 수행하며, 본인 기록에 근거한 AI 코치의 답을 받습니다. |
| **트레이너 웹** | 트레이너 | 담당 회원의 식단·운동을 날짜별 리포트로 확인하고, 루틴을 배정하고, 기록 옆에서 1:1로 코칭합니다. |
| **백엔드** | 공통 | 두 클라이언트가 하나의 API와 데이터베이스를 공유하며 권한으로 구분됩니다. |

<div align="center">
<img src="https://raw.githubusercontent.com/CSE-Sudo/on-care/main/docs/assets/diagram-service-loop.svg" alt="회원의 기록이 트레이너에게 전달되고 코칭이 회원에게 돌아오는 흐름" width="100%"/>
</div>

## Engineering

Flutter 로 만든 두 클라이언트와 FastAPI 백엔드, PostgreSQL(pgvector)로 구성됩니다. 식단 인식은 Vision AI의 추정값을 식약처 공공 영양성분 DB로 보정하고, AI 코치는 공개 가이드라인 원문과 회원 본인의 기록을 검색해 답하는 RAG 구조입니다. 백엔드는 AWS ECS, 배포는 GitHub Actions 로 자동화되어 있습니다.

문제 정의의 근거와 아키텍처, 로컬 실행 방법은 [**on-care**](https://github.com/CSE-Sudo/on-care) 저장소에 있습니다.

## Team

<div align="center">

| 최지수 | 박서연 | 신수빈 |
| :---: | :---: | :---: |
| <a href="https://github.com/aJISUa"><img src="https://github.com/aJISUa.png" alt="최지수" width="100"></a> | <a href="https://github.com/seoyeon0516"><img src="https://github.com/seoyeon0516.png" alt="박서연" width="100"></a> | <a href="https://github.com/subin21cc"><img src="https://github.com/subin21cc.png" alt="신수빈" width="100"></a> |
| [@aJISUa](https://github.com/aJISUa) | [@seoyeon0516](https://github.com/seoyeon0516) | [@subin21cc](https://github.com/subin21cc) |

<br/>

<sub>2026 이화여자대학교 캡스톤디자인 Team 02 Sudo · 지도교수 황의원 교수님 (컴퓨터공학전공)</sub>
</div>

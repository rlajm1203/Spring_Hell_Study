안녕! 오랜만입니다 커피요정 개발자 이서현입니다 ㅎㅎ 이번 3주차 과제는 2주차 과제보다는 어렵지 않게 난이도를 조정했습니다.

이번 3주차 과제의 목표는 다양한 도메인에 대해 Aggregate하는 과정을 익혀보겠습니다.

Aggregate란, 여러 도메인을 하나로 합치는 과정을 의미합니다. 이 과정에서 일관되고 클린한 구조로 코드를 작성하지 않으면 극악의 지옥을 맛보게 됩니다. 오늘 여러분은 다양한 자료구조들을 활용해 아래 과제를 도전하며 자료구조를 활용하는 노하우를 익혀보도록 하겠습니다.

# 1번 문제

서비스를 개발하다보면 모니터링 서비스도 중요하지만 회원들의 정보를 통계를 내서 가공해 보는 화면이 필요할 때가 많습니다. 이를 어드민 페이지라고 합니다.

어드민 페이지의 성격은 우선순위는 낮지만 기존에 있는 정보를 이용해 최대한 빠르게 구현해서 보여줘야 한다는 특징이 있습니다. 구현된 어드민 페이지는 개발자나 관리자의 만족도를 직접적으로 높이는데 크게 기여합니다.

더불어 웹/앱 호환성을 제공하는 데이터 제공은 중요합니다. 앱 서버의 특징은 웹 서버와는 다르게 화면(컴포넌트)단위로 데이터를 전송해야 하면 프론트 친구들이 좋아한다는 특징이 있습니다. (궁금하신 분들은 Http Capture라는 앱을 깔아서 앱에서 패킷을 뜯어보세용)

때문에 아래 요구사항을 빠르게 구현하고 어드민 페이지를 구현해보도록 합시다.


아래 페이지는 신입모집 어드민 페이지입니다.
<img width="1062" alt="image" src="https://github.com/JNU-econovation/Spring_Hell_Study/assets/54030889/9cc9bc92-923d-4649-bb92-ac914f4f6ab5">

하나의 API 요청에 모든 데이터를 담을 수 있도록 구성해봅시다.

요구사항

- (현 지원 기수의) 지원자 누적 합계
- 희망 분야 합계  (1순위 / 2순위)분리
- 소속 학과 합계
- 지원 경로 통계
- 면접 희망시간
    - 위 면접 희망 시간은 인당 여러개를 선택할 수 있습니다. (3월 19일 3시, 4시, 5시)
    - 특정 날짜에 대한 명시는 하지 않으며 다음과 같은 데이터형을 따릅니다,.

  `“desiredTime” : {{0,1}, {0,2}, {0,4}}` 이런식으로 각각의 좌표를 표현하시면 됩니다.

    - 화면의 표시 시간은 front에 처리를 위임합니다.
    - desiredTime에 해당하는 userId List를 매핑시켜서 어드민 페이지에 포함하시면 됩니다.
    - (0,1) → 4명, (2,5) → 2명, (3,4) → 0명 이런식으로 매핑시켜 API에 명시하세요.

모든 합계 요구사항은 모두 내림차순으로 데이터를 제공합니다.

관리자는 기본적으로 모든 데이터를 **생성/조회/수정/삭제**가 가능하고, 일반 회원은 아래의 정보를 **검색**만 할 수 있습니다.

# 2번 문제

각 DB를 여러번 조회하는 과정에서 기존에 의미없는 요청 순서에서 지연 문제가 발생했습니다.

- 데이터에 의존 관계가 없는데 조회 요청에 순서 때문에, API 지연이 발생했습니다

위 문제를 개선하세요.

## 3번 문제

위 구현 과제를 추상화 하세요.

# 4번 문제

위 문제를 해결하면서 해결한 과정을 정리하여 pdf로 제출하시길 바랍니다.

제출지 : ymecca730135@gmail.com

### 마감시간 : 2024:05:11/21:30
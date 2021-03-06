---
lab:
  title: '랩 1: 데이터 모델링'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 9edefbdf214d5a0f2e0693ffdf024dfc05c032c5
ms.sourcegitcommit: dbffa13e13419f5b9aadc894eb95fd16215b2ebf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2022
ms.locfileid: "146458365"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>모듈 2: Microsoft Dataverse 소개

# <a name="scenario"></a>시나리오

Bellows College는 캠퍼스 내에 여러 건물이 있는 교육 기관입니다. 캠퍼스 방문은 현재 종이에 기록되어 있습니다. 이 정보는 일관되게 수집되지 않으며, 전체 캠퍼스 방문 데이터를 수집하고 분석할 방법이 없습니다.

캠퍼스 관리부는 건물 액세스가 보안 요원에 의해 제어되고, 모든 방문이 반드시 호스트에 의해 사전 등록 및 기록되는 현대화된 방문자 등록 시스템을 원합니다.

이 과정 전반에 걸쳐 벨로즈 칼리지 관리 및 보안 담당자가 캠퍼스 내 건물에 대한 액세스를 관리하고 제어할 수 있도록 애플리케이션을 빌드하고 자동화를 수행합니다.

이 랩에서는 환경에 액세스하고 Microsoft Dataverse 데이터베이스를 만들고 변경 내용을 추적하는 솔루션을 만듭니다. 또한 다음 요구 사항을 지원하는 데이터 모델을 만듭니다.

-   R1 – 예약된 캠퍼스 방문에 대한 정보 추적

-   R2 - 방문자를 식별하고 추적하기 위한 기본 정보 기록

-   R3 – 방문의 일정, 기록 및 관리

마지막으로 샘플 데이터를 Microsoft Dataverse로 가져옵니다.

# <a name="high-level-lab-steps"></a>고급 랩 단계

학습 환경을 준비하려면 다음을 수행합니다.

* 솔루션 및 게시자 만들기
* 애플리케이션 요구 사항을 충족하는 새 구성 요소와 기존 구성 요소를 모두 추가합니다. 메타데이터에 대한 설명(테이블 및 관계)은 [데이터 모델 문서](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png)를 참조하세요. CTRL 키를 누른 상태로 클릭하거나 링크를 마우스 오른쪽 단추로 클릭하여 새 창에서 데이터 모델 문서를 열 수 있습니다.
* 방문 테이블 만들기
* Excel 스프레드시트를 사용하여 방문 데이터 가져오기

## <a name="prerequisites"></a>필수 조건:

-   **모듈 0 랩 0 - 랩 환경 검증** 완료

## <a name="things-to-consider-before-you-begin"></a>시작하기 전에 고려해야 할 사항:

-   명명 규칙 - 신중하게 이름을 입력합니다.

# <a name="exercise-1-create-new-table"></a>연습 \#1: 새 테이블 만들기

**목표:** 이 연습에서는 새 사용자 지정 방문 테이블을 만듭니다. 

## <a name="task--1-create-visit-table-and-columns"></a>작업 \# 1: 방문 테이블 및 열 만들기

**방문** 테이블은 방문자, 각 방문의 예약된 시간 및 실제 시간을 포함한 캠퍼스 방문 정보를 포함합니다.

방문 체크인 과정에서 방문자가 쉽게 입력하고 해석할 수 있는 고유한 번호를 각 방문에 할당하려 합니다.

>   방문 시간은 항상 건물의 위치에서 로컬이고 다른 표준 시간대에서 볼 때 변경되지 않아야 하기 때문에 **표준 시간대 독립** 동작을 사용하여 날짜 및 시간 정보를 기록합니다.

1. 아직 로그인하지 않은 경우 [https://make.powerapps.com](https://make.powerapps.com/)에 로그인합니다.

2. 아직 선택되지 않은 경우 오른쪽 상단에 있는 **[내 이니셜] 연습** 환경을 선택합니다.

3. 왼쪽의 탐색을 사용하여 Dataverse를 확장하고 테이블을 선택합니다.

4. **새 테이블** 을 클릭합니다.

5. **표시 이름** 에 **방문** 을 입력합니다.

6. **저장** 을 클릭합니다. 이렇게 하면 백그라운드에서 테이블 프로비전을 시작하는 동시에 다른 열을 추가할 수 있습니다.

7. 테이블을 만든 후 **스키마** 섹션 아래에서 **열** 을 선택합니다. 

8. **새 열** 을 선택하고 다음과 같이 구성합니다. 

    - **표시 이름** 에 대해 **예약된 시작** 을 입력합니다.

    - **데이터 형식** 에 대해 **날짜 및 시간** 을 선택합니다.

    - **필수** 에서 **필요한 비즈니스** 를 선택합니다.

    - **고급 옵션** 섹션을 펼칩니다.

    - **동작** 에서 **표준 시간대 독립** 을 선택합니다.

    - **저장** 을 클릭합니다.

9. 예약된 끝 열 만들기 

    - **열 추가** 를 클릭합니다.

    - **표시 이름** 에 대해 **예약된 끝** 을 입력합니다.

    - **데이터 형식** 에 대해 **날짜 및 시간** 을 선택합니다.

    - **필수** 에서 **필요한 비즈니스** 를 선택합니다.

    - **고급 옵션** 섹션을 펼칩니다.

    - **동작** 에서 **표준 시간대 독립** 을 선택합니다.

    - **저장** 을 클릭합니다.

10. 실제 시작 열 만들기

    - **열 추가** 를 클릭합니다.

    - **표시 이름** 에 대해 **실제 시작** 을 입력합니다.

    - **데이터 형식** 에 대해 **날짜 및 시간** 을 선택합니다.

    - **필수** 에서 **선택 사항** 으로 둡니다.

    - **고급 옵션** 섹션을 펼칩니다.

    - **동작** 에서 **표준 시간대 독립** 을 선택합니다.

    - **저장** 을 클릭합니다.

11. 실제 끝 열 만들기

    - **열 추가** 를 클릭합니다.

    - **표시 이름** 에 대해 **실제 종료** 를 입력합니다.

    - **데이터 형식** 에 대해 **날짜 및 시간** 을 선택합니다.

    - **필수** 에서 **선택 사항** 으로 둡니다.

    - **고급 옵션** 섹션을 펼칩니다.

    - **동작** 에서 **표준 시간대 독립** 을 선택합니다.

    - **저장** 을 클릭합니다.

12. 코드 열 만들기

    - **열 추가** 를 클릭합니다.

    - **표시 이름** 에 **코드** 를 입력합니다.

    - **데이터 유형** 에 대한 **일련 번호** 를 선택합니다.

    - **일련 번호 유형** 에 **날짜 접두사 번호** 를 선택합니다.

    - **저장** 을 클릭합니다.

13. 방문자 조회 열 만들기

    - **열 추가** 를 클릭합니다.

    - **표시 이름** 에 대한 **방문자** 를 입력합니다.

    - **데이터 형식** 에 대해 **조회** 를 선택합니다.

    - **관련 테이블** 에 대한 **연락처** 를 선택합니다.

    - **고급 옵션** 섹션을 펼칩니다.

    - **관계 이름** 에 **visitor_id** 를 입력합니다.

    - **저장** 을 클릭합니다.

 

연습 #2: 데이터 가져오기

**목표:** 이 연습에서는 샘플 데이터를 Dataverse 데이터베이스로 가져옵니다.

작업 #1: Visits.xls 파일을 가져옵니다.

이 작업에서는 Excel 파일에서 방문 데이터를 가져옵니다.

1. 바탕 화면에 **Visits.xls** 파일이 저장되어 있어야 합니다. 그렇지 않으면 [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx)를 다운로드합니다.

2. 아직 로그인 하지 않은 경우 [https://make.powerapps.com](https://make.powerapps.com/)에 로그인합니다.

3. 아직 선택되지 않은 경우 오른쪽 상단에 있는 **[내 이니셜] 연습** 환경을 선택합니다.

4. 왼쪽의 탐색을 사용하여 **Dataverse** 를 확장하고 테이블을 선택합니다.

화면에 데이터 > 테이블로 표시할 수 있습니다.

5. 이전 연습에서 만든 **방문** 테이블을 찾아 엽니다.

6. 상단의 메뉴를 사용하여 **가져오기** 옆에 있는 드롭다운 화살표를 선택하고 **Excel에서 데이터 가져오기** 를 선택합니다.

7. 표시되는 메뉴에서 **업로드** 단추를 선택합니다.

8. 이전에 다운로드한 **Visits.xls** 파일을 찾아 선택합니다. (참고: 파일 업로드에 1~2분 정도 소요될 수 있습니다. 매핑 에러가 있다는 메시지가 나와도 걱정하지 마세요. 다음에 수정할 것입니다.)

9. **열 매핑** 을 선택합니다.

10. 아래에 설명된 대로 열을 매핑합니다.

| 방문 Db 열| 원본 값 |
| - |
| 실제 종료| 실제 종료 |
| 실제 시작| 실제 시작 |
| 코드| 코드 |
| 속성| 속성 |
| 예약된 종료| 예약된 종료 |
| Scheduled Start| 예약된 시작 |


11. 나머지 필드는 모두 **설정 안 함** 상태로 둡니다.

12. 화면의 오른쪽 위 모서리에서 **변경 내용 저장** 을 선택합니다.

13. **데이터 가져오기** 화면에서 매핑 상태가 “매핑이 완료됨”인지 확인합니다.

14. 오른쪽 위 모서리에서 **가져오기** 를 선택하여 데이터 가져오기를 완료합니다.

**참고:** 데이터를 테이블로 가져오는 데 몇 분이 걸릴 수 있습니다. 몇 가지 에러가 표시되더라도 정상이며 과정의 나머지 부분에 영향을 미치지 않으므로 걱정하지 마세요.

작업 #2: 데이터 가져오기 확인

1. 데이터를 가져온 후 화면 왼쪽의 탐색을 사용하여 **방문** 테이블을 다시 선택합니다.

2. 가져온 데이터가 **방문 열 및 데이터** 섹션 아래에 표시되는지 확인합니다. 

축하합니다. 성공적으로 새 테이블을 만들고 데이터를 가져왔습니다.

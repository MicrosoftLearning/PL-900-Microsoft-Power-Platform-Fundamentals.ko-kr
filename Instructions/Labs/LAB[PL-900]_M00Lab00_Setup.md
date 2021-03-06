---
lab:
  title: '랩: 랩 환경 유효성 검사'
  module: 'Module 0: Course introduction'
ms.openlocfilehash: e69074549dddd4494db53a9ccb9ebfb3ae198d48
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424705"
---
# <a name="module-0-course-introduction"></a>모듈 0: 과정 소개

## <a name="scenario"></a>시나리오

Bellows College는 캠퍼스 내에 여러 건물이 있는 교육 기관입니다. 캠퍼스 방문자는 현재 종이 저널에 기록되어 있습니다. 이 정보는 일관되게 수집되지 않으며, 전체 캠퍼스 방문 데이터를 수집하고 분석할 방법이 없습니다.

캠퍼스 관리부는 건물 액세스가 보안 요원에 의해 제어되고, 모든 방문이 반드시 호스트에 의해 사전 등록 및 기록되는 현대화된 방문자 등록 시스템을 원합니다.

이 과정 전반에 걸쳐 벨로즈 칼리지 관리 및 보안 담당자가 캠퍼스 내 건물에 대한 액세스를 관리하고 제어할 수 있도록 애플리케이션을 빌드하고 자동화를 수행합니다.

이 모듈 0 랩에서는 Power Platform 평가판 테넌트를 취득하여 Power Platform 관리 센터에 액세스합니다. 그런 다음 관리 센터에서 대부분의  작업을 수행할 **연습** 환경을 만듭니다.

## <a name="exercise-1--setup"></a>연습 1 – 설정

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>작업 1 - Microsoft Power Platform 평가판 테넌트 획득

1.  공인 랩 주최자로부터 **Microsoft 365 자격 증명** 을 복사합니다.

2.  <https://powerapps.microsoft.com>으로 이동하여 **평가판 시작** 을 클릭합니다.

3.  **시작하기** 아래의 **업무용 메일 주소 입력** 이라고 쓰여 있는 텍스트 상자에 Microsoft 365 자격 증명의 이메일 주소를 입력합니다.

4.  Microsoft에 기존 계정이 있다는 프롬프트가 표시됩니다. **로그인** 을 선택합니다.

5.  공인 랩 주최자가 제공하는 암호를 입력하고 로그인합니다.

6.  **예** 를 선택하여 로그인 상태를 유지합니다.

7.  계정 정보를 완료하고 **시작** 을 선택하여 Microsoft Power Platform 평가판에 등록합니다.

### <a name="task-2--create-environment"></a>작업 \#2 – 환경 만들기

1.  메시지가 표시되면 <https://admin.powerplatform.microsoft.com>에 액세스하여 Microsoft 365 자격 증명으로 로그인합니다.

2.  **환경** 을 선택하고 **+새로 만들기** 를 클릭합니다.

    1.  **이름** 에는 **[사용자 이름 이니셜] 연습** 을 입력합니다. (예: AJ 연습)

    2.  **유형** 에서는 **평가판** 을 선택합니다(평가판(구독 기반) 옵션은 선택하지 마세요).

    3.  **이 환경에 대한 데이터베이스 만들기** 토글을 **예** 로 변경합니다.

    4.  다른 선택 항목은 모두 기본값으로 두고 **다음** 을 클릭합니다.

    5.  다음 탭에서는 모든 선택 항목을 기본값으로 두고 **저장** 을 클릭합니다.

3.  이제 **연습** 환경이 환경 목록에 표시됩니다.

>   환경을 프로비전하는 데 몇 분 정도 걸릴 수 있습니다. 필요한 경우 페이지를 새로 고칩니다.

---
lab:
  title: '랩 0: 랩 환경 유효성 검사'
  module: 'Module 0: Course introduction'
---

# <a name="lab-0-validate-lab-environment"></a>랩 0: 랩 환경 유효성 검사

## <a name="scenario"></a>시나리오

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

캠퍼스 관리부는 건물 액세스가 보안 요원에 의해 제어되고, 모든 방문이 반드시 호스트에 의해 사전 등록 및 기록되는 현대화된 방문자 등록 시스템을 원합니다.

이 과정 전반에 걸쳐 벨로즈 칼리지 관리 및 보안 담당자가 캠퍼스 내 건물에 대한 액세스를 관리하고 제어할 수 있도록 애플리케이션을 빌드하고 자동화를 수행합니다.

In this Module 0 lab, you will acquire a Power Platform trial and access the Power Platform admin center. In the admin center, you will then create a <bpt id="p1">**</bpt>Practice<ept id="p1">**</ept> environment that you will perform the majority of your lab work in.

## <a name="exercise-1--setup"></a>연습 1 – 설정

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>작업 \#1 - Microsoft Power Platform 평가판 테넌트 획득

1. 공인 랩 주최자로부터 **Microsoft 365 자격 증명**을 복사합니다.

1. <https://powerapps.microsoft.com>으로 이동하여 **평가판 시작**을 클릭합니다.

1. **시작하기** 아래의 **업무용 메일 주소 입력**이라고 쓰여 있는 텍스트 상자에 Microsoft 365 자격 증명의 이메일 주소를 입력하고 **다음**을 클릭합니다.

1. If you see a prompt that you have an existing account with Microsoft. Select <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept>.

1. 공인 랩 주최자가 제공하는 암호를 입력하고 로그인합니다.

1. **예**를 선택하여 로그인 상태를 유지합니다.

1. 국가를 변경하지 마세요.

1. **전화 번호**에 01234567890을 입력합니다.

1. 계정 정보를 완료하고 **시작**을 선택하여 Microsoft Power Platform 평가판에 등록합니다.

1. 확인 화면에서 **시작**을 클릭합니다.

1. 연락처 세부 정보를 입력하라는 메시지가 표시되면 **X**를 클릭하여 팝업 창을 닫습니다.

### <a name="task-2--create-environment"></a>작업 \#2 – 환경 만들기

1. <https://admin.powerplatform.microsoft.com>으로 이동하여 액세스하여 메시지가 표시되면 Microsoft 365 자격 증명으로 로그인합니다.

1. 시작 팝업이 표시되면 **시작**을 클릭합니다.

1. **환경**을 선택하고 **+ 새로 만들기**를 클릭합니다.

    1. **이름**에 **[내 이니셜] Practice**(예: AJ Practice)를 입력합니다.

    1. **유형**에 **평가판**을 선택합니다. (평가판(구독 기반) 옵션은 선택하지 마세요).

    1. **이 환경에 대한 데이터베이스 만들기** 토글을 **예**로 변경합니다.

    1. 다른 선택 항목은 모두 기본값으로 두고 **다음**을 클릭합니다.

    1. 다음 탭에서 모든 선택 항목을 기본값으로 두고 **저장**을 클릭합니다.

1. 이제 **연습** 환경이 환경 목록에 표시됩니다.

> Your environment may take a few minutes to provision. Refresh the page if needed.

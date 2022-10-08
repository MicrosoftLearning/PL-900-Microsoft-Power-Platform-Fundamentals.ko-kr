---
lab:
  title: '랩 4: 자동화된 솔루션 빌드 방법'
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>랩 4: 자동화된 솔루션 빌드 방법

## <a name="scenario"></a>시나리오

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

캠퍼스 관리부는 건물 액세스가 보안 요원에 의해 제어되고, 모든 방문이 반드시 호스트에 의해 사전 등록 및 기록되는 현대화된 방문자 등록 시스템을 원합니다.

이 과정 전반에 걸쳐 벨로즈 칼리지 관리 및 보안 담당자가 캠퍼스 내 건물에 대한 액세스를 관리하고 제어할 수 있도록 애플리케이션을 빌드하고 자동화를 수행합니다.

이 랩에서는 방문이 예약될 때 방문자에게 이메일을 보낼 Power Automate 흐름을 만듭니다.

## <a name="high-level-lab-steps"></a>고급 랩 단계

프로젝트 완료를 위해 구현해야 하는 요구 사항은 다음과 같습니다.

- 방문이 예약된 경우 연락처에 전자 메일을 통해 알림을 받아야 합니다.

## <a name="prerequisites"></a>필수 조건

- **모듈 0 랩 0 - 랩 환경 검증** 완료
- **모듈 2 랩 1 - 데이터 모델링** 완료
- **모듈 2 랩 3 - 모델 기반 앱을 빌드하는 방법** 완료
- 개인 메일 주소가 채워져 만든 John Do 연락처

## <a name="exercise-1-create-visit-notification-flow"></a>연습 1: 방문 알림 흐름 만들기

<bpt id="p1">**</bpt>Objective:<ept id="p1">**</ept> In this exercise, you will create a Power Automate flow that implements the requirement. The visitor should be sent an email that includes the unique code assigned to the visit when a visit is created.

### <a name="task-1-create-a-flow"></a>작업 \#1: 흐름 만들기

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  아직 선택되지 않은 경우 오른쪽 상단에 있는 **[내 이니셜] 연습** 환경을 선택합니다.

3.  왼쪽 탐색 영역에서 **흐름**을 선택합니다.

4.  메시지가 표시되면 **시작**을 선택합니다.

5.  **새 흐름**을 클릭하고 **자동화된 클라우드 흐름**을 선택합니다.

6.  **흐름 이름**에 "방문 알림"을 입력합니다.

7.  **흐름의 트리거 선택**에서 **Dataverse**를 검색합니다.

8.  **행을 추가, 수정 또는 삭제할 때** 트리거를 선택한 다음 **만들기**를 클릭합니다.

9.  흐름에 대한 트리거 조건을 채웁니다.

    1.  **변경 유형**에 대해 **추가됨**을 선택합니다.

    2.  **테이블 이름**에 대해 **방문**을 선택합니다.

    3.  **범위**에 대한 **조직** 선택

    4.  On the trigger step, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>. Rename this trigger <bpt id="p1">**</bpt>"When a visit is added"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>작업 \#2: 방문자 행을 가져오는 단계 만들기

1.  Bellows College는 캠퍼스 내에 여러 건물이 있는 교육 기관입니다.

2.  **Dataverse**를 검색합니다.

3.  **ID 기준으로 행 가져오기** 작업을 선택합니다.

4.  **연락처**를 **테이블 이름**으로 선택합니다.

5.  캠퍼스 방문자는 현재 종이 저널에 기록되어 있습니다.

6.  이 정보는 일관되게 수집되지 않으며, 전체 캠퍼스 방문 데이터를 수집하고 분석할 방법이 없습니다.

7.  On this action, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>.
        Rename this action <bpt id="p1">**</bpt>"Get the Visitor"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>작업 \#3: 방문자에게 메일을 보내는 단계 만들기

1.  Click <bpt id="p1">**</bpt>+ New step<ept id="p1">**</ept>. This is the step that will send an email to the visitor.

2.  메일을 검색하고 **Office 365 Outlook** 커넥터를 선택한 다음 **이메일 보내기(V2)** 작업을 선택합니다.

3.  이 작업을 사용하기 위한 사용 약관을 수락하라는 메시지가 표시되면 **수락**을 클릭합니다.

4.  **받는 사람** 필드 아래에서 **동적 콘텐츠 추가**를 선택합니다. 
    
5.  동적 콘텐츠 목록에서 **메일**을 선택합니다.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  **벨로즈 대학 예약 방문**을 **제목** 필드에 입력합니다.

7.  **전자 메일 본문**에 다음 텍스트를 입력합니다.

>   Dynamic content needs to be placed where fields are named in brackets. It is recommended to copy &amp; paste all text first and then add dynamic content in the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Highlight the <bpt id="p1">**</bpt>{First Name}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>First Name<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>Get the Visitor<ept id="p2">**</ept> step.

9.  Highlight the <bpt id="p1">**</bpt>{Scheduled Start}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled Start<ept id="p1">**</ept> field <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

10.  Highlight the <bpt id="p1">**</bpt>{Scheduled End}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled End<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

11.  **저장**을 클릭합니다.

Leave this flow tab open for the next task. You flow should look approximately like the following:

![흐름 단계의 예입니다.](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>작업 \#4: 흐름의 유효성 검사 및 테스트

1.  브라우저에서 새 탭을 열고 <https://make.powerapps.com>으로 이동합니다.

2.  아직 선택되지 않은 경우 오른쪽 상단에 있는 **[내 이니셜] 연습** 환경을 선택합니다.

3.  **앱**을 클릭하여 앞서 만든 **Bellows Campus Management** 모델 기반 앱을 선택합니다.

3.  이 브라우저 탭을 열어 두고 흐름이 있는 이전 탭으로 다시 이동합니다.

4.  On the command bar, click <bpt id="p1">**</bpt>Test<ept id="p1">**</ept>. Select <bpt id="p1">**</bpt>Manually<ept id="p1">**</ept> and then click <bpt id="p2">**</bpt>Test<ept id="p2">**</ept>.

5.  모델 기반 앱이 열려 있는 브라우저 탭으로 이동합니다. 

6.  왼쪽의 탐색 영역에서 **방문**을 선택합니다.

6. **+ 새로 만들기** 단추를 눌러 새 **방문** 레코드를 추가합니다.

7. 다음과 같이 방문 레코드를 완성합니다.

    -   **이름:** 테스트 방문

    -   **방문자:** John Doe

    -   **예약된 시작:** 내일 오전 8:00

    -   **예약된 종료:** 내일 오전 9:00

8. **저장 후 닫기** 단추를 선택합니다.

9. Navigate to the browser tab with your flow test running. After a short delay, you should see the flow running. This is where you can catch any issues in the flow or confirm that it ran successfully.

After a short delay, you should see an email in your inbox, since you populated John Doe's email as your personal email. Note that it may go to your Junk Email folder.

## <a name="challenges"></a>과제

- Play around with the formatting on the email. How can you make it more professional looking?
---
lab:
  title: '보너스 랩: Copilot을 사용하여 캔버스 앱 빌드'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# 보너스 랩: Copilot을 사용하여 캔버스 앱 빌드

**WWL 테넌트 - 사용 약관** 강사 진행 교육에서 사용할 수 있도록 제공되는 테넌트는 해당 강사 진행 교육의 실습 랩 지원용으로 제공되는 것이므로 테넌트를 실습 랩 외부에서 공유하거나 사용해서는 안 됩니다. 이 과정에서 사용되는 테넌트는 평가판 테넌트이며 클래스가 종료된 후 사용하거나 액세스할 수 없으며 확장판에서도 사용할 수 없습니다. 테넌트를 유료 구독으로 변환해서는 안 됩니다. 이 과정의 일부로 얻은 테넌트는 Microsoft Corporation의 재산으로 유지되며 언제든지 액세스 권한을 획득하고 다시 소유할 수 있는 권리를 보유합니다. 

## 시나리오

Bellows College는 캠퍼스 내에 여러 건물이 있는 교육 기관입니다. 캠퍼스 방문자는 현재 종이 저널에 기록되어 있습니다. 이 정보는 일관되게 수집되지 않으며, 전체 캠퍼스 방문 데이터를 수집하고 분석할 방법이 없습니다.

캠퍼스 관리부는 건물 액세스가 보안 요원에 의해 제어되고, 모든 방문이 반드시 호스트에 의해 사전 등록 및 기록되는 현대화된 방문자 등록 시스템을 원합니다.

이 랩에서는 Copilot을 사용하여 방문 기록을 위한 캔버스 애플리케이션을 새로 만듭니다. 

## 랩 단계 요약

아래 개요에 따라 캔버스 앱을 디자인합니다.

- 빌드할 앱 설명

- Copilot을 사용하여 지원 테이블 구조 수정

 ## 필수 조건

- **모듈 1 랩 0 - 랩 환경 검증** 완료

## 연습 1: Copilot을 사용하여 대학 방문 신청서를 작성합니다.

**목표:** 이 연습에서는 캠퍼스 방문 테이블에 연결하여 캔버스 앱을 만듭니다.

### 작업 \#1: 초기 애플리케이션 만들기

1. https://make.powerapps.com 로 이동합니다.

2. 다시 인증이 필요할 수 있습니다. 필요한 경우 **로그인**을 선택하고 지침을 따릅니다.

3. 아직 선택하지 않은 경우 오른쪽 상단에서 **Dev One** 환경을 선택합니다.

4. **만들려는 애플리케이션 설명** 상자에 다음 텍스트를 입력합니다. 대학 캠퍼스 방문을 기록하는 애플리케이션을 만듭니다. 

5. **이동** 단추를 선택합니다.

Copilot이 애플리케이션을 지원하는 테이블 구조를 빌드하기 시작합니다. 

> **중요:** 생성형 AI를 사용하는 경우 항상 동일한 정확한 결과가 출력되지는 않습니다. 내 테이블이 다른 학생용 테이블과 정확히 일치하지 않을 수 있습니다. 

6. **변경할 내용 설명** 상자에 다음 텍스트를 입력합니다. 시작 시간과 종료 시간의 두 열을 추가합니다. 두 필드 모두 날짜 및 시간 필드여야 합니다.  

7. **Go** 단추를 선택하거나 **Enter** 키를 누릅니다. 

8. 테이블 옆을 스크롤하여 **시작 시간**과 **종료 시간** 열이 생성되었는지 확인합니다. 

방문자의 방문 시작/종료 시간을 기록하기 때문에 추가적인 방문 날짜 필드는 더 이상 필요 없습니다. 

9. **방문 날짜** 필드나 이에 해당하는 다른 필드를 찾아 **변경 내용 설명 상자**에서 방문 날짜 필드 삭제라는 텍스트를 입력합니다. 

10. **이동** 단추를 선택합니다. 

11. **시작 시간**과 **종료 시간** 이외에 나타날 수 있는 다른 데이터 필드를 제거합니다. 

처음에는 텍스트 데이터 형식으로 지정된 **목적** 필드 등의 필드가 추가됩니다. Copilot에서 이를 드롭다운(선택) 메뉴로 변경하도록 할 예정입니다. 

12. **변경 내용 설명 상자**에 다음 텍스트를 입력합니다. 다음 옵션을 사용하여 목적 필드를 선택 메뉴로 변경합니다. 캠퍼스 투어, 경력 박람회, 교수 면담, 학생 상담, 기타. 

13. **이동** 단추를 선택합니다. 

14. 건물 번호도 캡처할 것이므로 **변경 내용 설명 상자**에 다음과 같이 입력합니다. 건물 열을 추가합니다. 

15. **이동** 단추를 선택합니다. 

16. 현재 테이블에 만족하면 **앱 만들기** 버튼을 선택합니다. 

17. 필요한 경우, **Power Apps Studio 시작** 화면에서 **다시 보지 않기**를 선택하고 **건너뛰기** 단추를 선택합니다. 

![방금 만든 앱의 스크린샷](media/bonus-lab-copilot-01.png)

축하합니다, Copilot을 이용해 새 앱을 만들었습니다. 

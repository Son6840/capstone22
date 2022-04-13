# capstone22

<b>팀명 : 스윗프트 <br>
<b>이름 : 손상배 (팀장 : 기획,개발) <br>
<b>졸업작품 소개 사이트 : https://son6840.github.io/SweeftCapstone/ <br>
<b>포트폴리오 소개 사이트 : <br>

## [졸업작품 소개]

### -작품명 :  <b> Bbetter  <br>
### -개발환경 
      MacOS
  <br>

### -작품소개
      삶의 질 향상을 위한 어플리케이션
  <br>

### -작품의 특징
      주요 기능으로는 캘린더, 목표설정, 오늘의 뉴스, 타이머가 있다
      크롤링을 이용하여 뉴스를 출력
  <br>
  
## [개발 일지]
      
  ### 22년 04월 13일

테이블뷰 데이터 소스 객체는 UITableViewDataSource 프로토콜을 채택합니다.

데이터 소스는 테이블 뷰를 생성하고 수정하는데 필요한 정보를 테이블뷰 객체에 제공합니다.

데이터 소스는 데이터 모델의 델리게이트로, 테이블뷰의 시각적 모양에 대한 최소한의 정보를 제공합니다.

UITableView 객체에 섹션의 수와 행의 수를 알려주며, 행의 삽입, 삭제 및 재정렬하는 기능을 선택적으로 구현할 수 있습니다.

UITableViewDataSource 프로토콜의 주요 메서드는 아래와 같습니다. 이 중 @required로 선언된 두 가지 메서드는 UITableViewDataSource 프로토콜을 채택한 타입에 필수로 구현해야 합니다.

 @required 
 // 특정 위치에 표시할 셀을 요청하는 메서드
 func tableView(UITableView, cellForRowAt: IndexPath) 
 
 // 각 섹션에 표시할 행의 개수를 묻는 메서드
 func tableView(UITableView, numberOfRowsInSection: Int)
 
 @optional
 // 테이블뷰의 총 섹션 개수를 묻는 메서드
 func numberOfSections(in: UITableView)
 
 // 특정 섹션의 헤더 혹은 푸터 타이틀을 묻는 메서드
 func tableView(UITableView, titleForHeaderInSection: Int)
 func tableView(UITableView, titleForFooterInSection: Int)
 
 // 특정 위치의 행을 삭제 또는 추가 요청하는 메서드
 func tableView(UITableView, commit: UITableViewCellEditingStyle, forRowAt: IndexPath)
 
 // 특정 위치의 행이 편집 가능한지 묻는 메서드
 func tableView(UITableView, canEditRowAt: IndexPath)

 // 특정 위치의 행을 재정렬 할 수 있는지 묻는 메서드
 func tableView(UITableView, canMoveRowAt: IndexPath)
 
 // 특정 위치의 행을 다른 위치로 옮기는 메서드
 func tableView(UITableView, moveRowAt: IndexPath, to: IndexPath)

델리게이트

테이블뷰 델리게이트 객체는 UITableViewDelegate 프로토콜을 채택합니다.

델리게이트는 테이블뷰의 시각적인 부분 수정, 행의 선택 관리, 액세서리뷰 지원 그리고 테이블뷰의 개별 행 편집을 도와줍니다.

델리게이트 메서드를 활용하면 테이블뷰의 세세한 부분을 조정할 수있습니다.

UITableViewDelegate 프로토콜의 주요 메서드는 아래와 같습니다. 이 중 필수로 구현해야 하는 메서드는 없습니다.

// 특정 위치 행의 높이를 묻는 메서드
 func tableView(UITableView, heightForRowAt: IndexPath)
 // 특정 위치 행의 들여쓰기 수준을 묻는 메서드
 func tableView(UITableView, indentationLevelForRowAt: IndexPath)

 // 지정된 행이 선택되었음을 알리는 메서드
 func tableView(UITableView, didSelectRowAt: IndexPath)

 // 지정된 행의 선택이 해제되었음을 알리는 메서드
 func tableView(UITableView, didDeselectRowAt: IndexPath)

 // 특정 섹션의 헤더뷰 또는 푸터뷰를 요청하는 메서드
 func tableView(UITableView, viewForHeaderInSection: Int)
 func tableView(UITableView, viewForFooterInSection: Int)

 // 특정 섹션의 헤더뷰 또는 푸터뷰의 높이를 물어보는 메서드
 func tableView(UITableView, heightForHeaderInSection: Int)
 func tableView(UITableView, heightForFooterInSection: Int)

 // 테이블뷰가 편집모드에 들어갔음을 알리는 메서드
 func tableView(UITableView, willBeginEditingRowAt: IndexPath)

 // 테이블뷰가 편집모드에서 빠져나왔음을 알리는 메서드
 func tableView(UITableView, didEndEditingRowAt: IndexPath?)
      
  ### 22년 04월 06일
      기획서 마무리 및 프로젝트 생성
      깃크라켄을 사용한 브랜치 생성
      xcode 를 사용해 탭바 
      구성 및 레이아웃 
      
  
  ### 22년 3얼 30일
      부트스트랩을 이용해 소개 페이지를 제작
      
  ### 22년 3월 23일
      화면 기획 및 유효성검사를 실시
      

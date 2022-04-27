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
      
  ### 22년 04월 27일
      
   ## Userdefault 
      
swift안에 있는 float, Int, double, Bool, URL 등 기본적으로 제공하는 자료구조와 NSData, NSString, NSNumber NS관련 자료구조 또한 저장이 가능해서 활용성이 높다.

 

파일 참조 유지
파일 시스템의 위치를 지정하는 파일 URL을 기본 자료구조를 저장할 때 사용하는 함수 대신에 bookmarkData

(option:includingResourceValuesForKeys:relateTo) 메서드를 사용하여 NSURL 북마크 데이터를 생성하여 파일 URL에 대한 데이터가 손실되지 않게 도와준다.

 

UserDefaults 값 변경에 대한 알림
Default Notification Center을 통해 UserDefaults 값이 변경될 때마다 알림을 받을 수 있어서 관리하기 편하다.

 

사용하기
UserDefaults 클래스는 Foundation 프레임워크 안에 내장된 클래스이기 때문에 먼저 Foundation을 가져온다.

 

UserDefaults.standard
공유된 기본값 객체를 반환하는 함수이다.

import Foundation
print(UserDefaults.standard)

//<NSUserDefaults: 0x121e13450>
현재는 입력한 값이 하나도 없기 때문에 NSUserDefaults 값만 출력이 된다.

 

set(Any?, forKey: String)
set 명령어를 통해 UserDefaults 데이터베이스에 등록을 할 수 있다. 기본적인 형식이 Dictionary 구조이기 때문에 앞쪽에 value값을 넣고 forKey에는 key값을 지정해야한다. 데이터가 존재하는지 확인하기 위해서는 해당 값의 형식에 따라 object, url, array, dictionary, string, stringArray, data, bool, integer, float, double 등을 호출하고 해당 값의 키를 forKey 파라미터에 입력을 하면 된다. value값이 String인 경우 값이 없을 수도 있는 경우가 있기 때문에 해당 값들을 사용할려면 ??나 guard 문을 사용하여 없을 때를 대비하는 것이 좋다. 기존의 사용하던 key의 value값을 바꿀 때도 set을 통해 똑같은 key값을 입력하면 변경이 가능하다.

 ``` swift
import Foundation
print(UserDefaults.standard)
UserDefaults.standard.set("Daesiker", forKey: "name")
UserDefaults.standard.set(27, forKey: "age")
UserDefaults.standard.set(4.1, forKey: "grade")
print(UserDefaults.standard.string(forKey: "name") ?? "no name")
print(UserDefaults.standard.integer(forKey: "age"))
print(UserDefaults.standard.double(forKey: "grade"))

//<NSUserDefaults: 0x126613450>
//Daesiker
//27
//4.1
 

removeObject(forKey: String)
해당 키에 데이터가 존재하면 삭제해주는 메서드이다. 여기서 주의할 점은 Bool, Int, Float, Double 타입의 value들은 해당 키가 없으면 기본값을 반환해준다. Bool은 false가 기본값이고 Int, Float, Double은 0을 반환한다.
```
``` swift
import Foundation
print(UserDefaults.standard)
UserDefaults.standard.set("Daesiker", forKey: "name")
UserDefaults.standard.set(27, forKey: "age")
UserDefaults.standard.set(4.1, forKey: "grade")
print(UserDefaults.standard.string(forKey: "name") ?? "no name")
print(UserDefaults.standard.integer(forKey: "age"))
print(UserDefaults.standard.double(forKey: "grade"))

UserDefaults.standard.removeObject(forKey: "age")

print(UserDefaults.standard.string(forKey: "name") ?? "no name")
print(UserDefaults.standard.integer(forKey: "age"))
print(UserDefaults.standard.double(forKey: "grade"))
/*

<NSUserDefaults: 0x126613450>
Daesiker
27
4.1
Daesiker
0
4.1
*/
      ```
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
      

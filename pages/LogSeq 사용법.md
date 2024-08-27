# Download
collapsed:: true
	- https://logseq.com/downloads
	- 다운로드 받은 후, 모든 메모를 저장할 로컬 폴더 지정 필요
- # 누구를 위한 툴인가
	- 절대 모두에게 최고의 툴은 아니다
		- ==폴더 구조가 없기 때문에== 익숙하지 않아 오히려 비효율적일 수 있습니다.
	- 그럼 무엇이 장점인데?
		- 사내에서 사용할 수 있는 몇 안되는 ==마크다운 & 아웃라이너== 방식의 메모툴입니다.
		- 대충 써도 ==알아서 잘 정리==해주고, 특정 조건에 따라 ==메모들을 필터링==할 줄 압니다.
- # 무엇을 쓸 것인가
	- ## page
		- 저희가 직접 정한 제목으로 메모장 생성
		- ctrl+K > Create page
		- `[[페이지 제목]]`
			- [[test]] 페이지간 연결 링크가 자동 생성됨
	- ## journal
		- 매일 날짜를 제목으로 페이지 자동 생성
		- 왼쪽 메뉴바 > journals
		- [[Aug 27th, 2024]]
	- ## page vs journal
		- ### page
			- 소속이 명확한 정보
			- 양이 많아서 정리가 필요한 정보
		- ### journal
			- 소속이 애매한 정보
			- 매우 짧은 내용의 정보
			- 회의록, 잡다한 생각, TODO
		- ### 예시
			-
- # 어떻게 폴더 없이 정리할 것인가.
	- #+BEGIN_CAUTION
	  page: 모든 페이지 제목을 외워요?
	  journal: 언제 기록했는지 전부 외워요?
	  #+END_CAUTION
	- ## subpage
		- 특정 page 아래에 속하는 페이지
			- page의 hierarchy에 상하관계가 정리됨
		- `[[페이지 제목]]/[[서브 제목]]`
		- [[test/subtest]]
	- ## tag
		- block에 대해 단순 tagging: #tag_block
		- page에 대해 property로 tagging: [[tagging]]
	- ## subpage vs tag
		- ### subpage
			- page간 hierarchy가 명확한 경우
				- project > subproject
		- ### tag
			- 특정 그룹으로 페이지들을 묶을 수 있는 경우
				- meetings, projects, subprojects, tips
			- tag는 ==page 혹은 block의 property== 입니다. ==filtering할 때== 아주 유용합니다.
				- page filtering
					- {{query (page-tags [[tag_page]])}}
					  query-sort-by:: block
					  query-table:: true
					  query-sort-desc:: true
					  query-properties:: [:page]
				- block filtering
					- query-table:: false
					  #+BEGIN_QUERY
					  { :title "filter all blocks with #tag_black"
					    :query [:find (pull ?b [*])
					            :where [?b :block/content ?content]
					                   [(clojure.string/includes? ?content "#tag_block")]]
					  }
					  #+END_QUERY
- # 어떻게 작성하는가
	- ## MarkDown
		- # 제목 1
		- ## 제목 2
		- ### 제목 3
		- **굵게**
		- *기울임체*
		- ==하이라이트==
		- `inline code`
		- ```kotlin
		  // outline code
		  println("Hello, World!")
		  ```
		- [Google](https://www.google.com)
		- 암기하지 않아도 `/` 사용하면 확인 가능
	- ## 아웃라이어
		- 프로젝트 A
			- 작업 1
				- 세부 작업 1
				- 세부 작업 2
			- 작업 2
		- 프로젝트 B
- # example use
	- #+BEGIN_TIP
	  가장 많이 사용하는 tag들은 즐겨찾기에 넣어두기
	  #+END_TIP
	- projects
	- subprojects
	- meetings
- # useful commands
	- code block
	- quote
	- templates
	- todo
	- embed page or block
- # plug-ins
	- calendar
	- tags
	- code copy
	- icon
	- emoji picker
	- todo
- # Tips
	- github sync
	- wiki 복사 붙여넣기
- # References
	- [50 LOGSEQ TIPS: Beginner to Expert in 6 Minutes | Tutorial | ROAM Research Alternative Free Version](https://youtu.be/r_tcDooayOo?si=ehNzeqnsK9VLgRP3)
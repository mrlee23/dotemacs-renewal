## .emacs.d/documents/
### 개요
---
#### 설명
이맥스를 이용해 관리하는 문서의 기본 디렉토리이다.

#### 특징
기존 운영체제의 유저 기본 디렉토리 개념을 가져와 사용한다.

유닉스 체제를 예로 들면,

`/home/username/` 은 홈 디렉토리이고, 이맥스에서 이와 동일한 개념으로 이맥스 홈 디렉토리는 `.emacs.d/` 가 된다.

그리고 `~/Documents` 와 같이 `.emacs.d/documents` 가 문서 관리 기본 디렉토리이다.

#### 특징 요약

`/home/username/` => `/home/username/.emacs.d/`

`/home/username/Documents` => `/home/username/.emacs.d/documents/`

#### 디렉토리 설명
---
#### [diary/]
일지, 일기장 등등을 저장하는 디렉토리이다.

프로젝트 관련 일지와 느낀점, 하루의 일기 등등이 들어가 있다.

**요소**

* 일기

* 꿈일기

* 프로젝트 일지

* 하루 로그

#### [project/]
각종 프로젝트 관련 문서를 저장하는 디렉토리이다.

문서와 더불어 소스코드 역시 저장할 수 있다.

**<요소>**

* TriangleFramework
* DailyLanguage

#### [references/]
프로그래밍 명령어, 각종 참조 자료 등등이 들어가 있는 곳이다.

**<요소>**



<!-- 내부 링크 -->
<!-- 상대 경로 정보 -->
<!-- 상위 디렉토리 정보 -->
[caches/]: ../caches
[packages/]: ../packages
[documents/]: ../documents
[settings/]: ../settings

<!-- 상위 파일 정보 -->
[../README.md]: ../README.md
[init.el]: ../init.el
[search.sh]: ../serach.sh
[load-packages.el]: ../packages/load-packages.el

<!-- 현재 디렉토리 정보 -->


<!-- 현재 파일 정보 -->
[README.md]: README.md

<!-- 하위 디렉토리 정보 -->
[diary/]: diary
[project/]: project
[references/]: references

<!-- 하위 파일 정보 -->

<!-- 외부 링크 -->

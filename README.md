## .emacs.d/
### 개요
---
이맥스의 최상위 디렉토리이다.

유닉스 체제의 디렉토리 관리와 비슷하게 작동한다.

이맥스를 실행하면 가장 먼저 불러오는 init.el이 포함되어 있다.

### 사용법

### 디렉토리 설명
---
#### [caches/]
이맥스를 실행하는 동안 이맥스의 각종 모드들이 자동으로 생성하는 캐시파일들이
저장되는 곳이다.

#### [documents/]
맥 OS의 /User/username/Documents 와 같은 개념으로, 사용자의 모든 문서를 이맥스
내에서 관리하기 위해 만들어진 디렉토리이다.

주로 org 모드를 사용한다.

#### [packages/]
각종 외부 패키지 관리를 위한 디렉토리이다.

#### [settings/]
이맥스의 개인 설정 파일이 들어가 있는 곳으로써, 모든 이맥스 관련 설정은 이
디렉토리에 있다.

각종 기본 설정(default), 키맵 설정(keymap) 등등..

### 파일 설명
---
#### [init.el]
이맥스를 실행하면 가장 처음 불러오는 파일이다.

**_시퀀스_**
1. [packages/] 디렉토리 내의 패키지 관리 툴의 기본 디렉토리를 `load-path` 에 추가한다.

2. 기본 디렉토리 관련 변수를 설정한다.

3. [settings.el] 파일을 로드하고 시퀀스를 끝낸다.

#### [search.sh]
**.emacs.d/**내의 파일을 검색하기 위한 쉘 스크립트 명령어이다.
아직은 기능이 약하다.
추후 추가할 기능 (옵션)

**-i**
* .gitignore를 참조해 검색에서 제외시킬 디렉토리 혹은 파일을 설정한다.

**-r regexp**
* regexp를 사용해서 검색에 사용할 수 있다.


[caches/]: caches/
[documents/]: documents/
[packages/]: packages/
[settings/]: settings/

[init.el]: init.el
[search.sh]: search.sh

[settings.el]: settings/settings.el

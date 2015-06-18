## .emacs.d/packages/
### 개요
---
이맥스에 바인딩 되는 외부 패키지를 관리하기 위한 디렉토리이다.

여기에 있는 모든 디렉토리는 가장 처음 [init.el] 에서 파일이 로딩된다.

자세한건 해당 [../README.md] 참조.

### 사용법
---
* [init.el] 에 위치시킬 것.

`
(add-to-list 'load-path "~/.emacs.d/packages")
(require 'load-packages)
`

### 디렉토리 설명
---
#### [cask/]
[Cask] 로 관리되는 외부 패키지들의 기본 디렉토리이다.

#### [elpa/]
이맥스의 기본 패키지 관리 플러그인의 기본 디렉토리이다.

[melpa] 의 패키지들도 이 안에서 관리된다.

#### [github/]
다른 프로그램의 도움 없이 수동으로 패키지를 관리하는 기본 디렉토리이다.

[Github] 로 부터 패키지 소스를 다운받는다.

터미널 명령어로 `$ git clone` 를 사용하여 패키지 소스를 다운받을 수 있다.

### 파일 설명
---
#### [CHANGELOG.md]
[cask/] , [elpa/] , [github/] 에 패키지가 추가되거나 업데이트 혹은 삭제될 때 마크다운 형식으로 기록된다.

로그 순서는 최근 - 과거 순으로 내림차순이다.

#### [load-packages.el]
자동으로 관리되는 [cask/] , [elpa/] 의 기본 경로 관련 설정과 더불어 수동으로 관리하는 [github/] 의 패키지를 로드한다.

또한 `(require 'package)` 와 같은 이맥스 내장 `package` 의 설정 역시 이 파일에서 이루어진다.

사용법에서 기술한 것과 같이 이 파일을 로드하면 [packages] 의 모든 패키지 디렉토리가 이맥스 세션의 `'load-path` 에 추가된다.

그리고 언제든지 `(require 'package-name)` 을 통해 해당 패키지를 불러올 수 있다.

<!-- 내부 링크 -->
<!-- 상대 경로 정보 -->
<!-- 상위 디렉토리 정보 -->
[packages]: ../packages

<!-- 상위 파일 정보 -->
[init.el]: ../init.el
[../README.md]: ../README.md

<!-- 현재 디렉토리 정보 -->
[cask/]: cask
[elpa/]: elpa
[github/]: github

<!-- 현재 파일 정보 -->
[CHANGELOG.md]: CHANGELOG.md
[load-packages.el]: load-packages.el

<!-- 하위 디렉토리 정보 -->

<!-- 하위 파일 정보 -->

<!-- 외부 링크 -->
[Cask]: https://github.com/cask/cask
[Melpa]: http://melpa.org
[Github]: http://www.github.com

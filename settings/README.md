## .emacs.d/settings
### 개요
---
이맥스의 설정 파일이 위치해 있는 디렉토리이다.

[../init.el] 을 제외한 모든 설정파일은 여기에 위치한다.

[../init.el] 로부터 [settings.el] 파일이 가장 처음 불려진다.

* .el 파일이 로딩되는 순서
	1. [settings.el]
	* [../init.el] 파일이 로딩하는 첫번째 파일이다.
	* 이 파일은 [settings/] 내의 .el 파일을 논리적 순서에 맞게 로딩한다.
	2. [first-settings.el]
	* [settings.el] 에서 [settings/] 디렉토리 내의 [default/default.el] , [keymap/keymap.el] 등이 실행되기 전에 먼저 실행된다.
	3. [last-settings.el]
	* [settings/] 내에 존재하는 디렉토리 파일들이 모두 실행된 후 실행된다.
	4. [customize-settings.el]
	* 이맥스에서 `customize` 를 이용해 설정된 것으로써 최종적으로 [settings.el] 에서 로딩된다.
	* [last-settings.el] 의 다음 순서로 로딩된다.

### 상세
---
현재 디렉토리 [settings/] 는 이맥스 설정의 메인 디렉토리로 볼 수 있다.

[../init.el] 은 이맥스의 시작시 메인 디렉토리로 리다이렉션 하는 역할을 한다.

[../packages/] 역시 소스코드를 담고 있는 소스 저장 창고이다.

[../init.el] 에서는 [../packages/] 관리까지만 하고 그 다음 단계의 설정은 [settings.el] 로 넘겨주기 때문에 [../packages/] 내의 패키지들은 이맥스 내장 패키지 처럼 작동하게 되어있다.

* 논리적인 로딩 순서
	1. 

### 디렉토리 설명
---
#### [data/]

#### [default/]

#### [keymap/]

#### [lib/]

#### [plugin/]

#### [syntax/]

#### [test/]

#### [var/]

### 파일 설명
---
#### [README.md]

#### [CHANGELOG.md]

#### [ERRORLOG.md]

#### [TODO.org]

#### [settings.el]

#### [first-settings.el]

#### [last-settings.el]

#### [customize-settings.el]

#### [simple-settings.el]


<!-- 상위 디렉토리 정보 -->
[../caches/]: (../caches)
[../packages/]: (../packages)
[../documents/]: (../documents)

<!-- 상위 파일 정보 -->
[../README.md]: (../README.md)
[../init.el]: (../init.el)
[../search.sh]: (../serach.sh)

<!-- 현재 디렉토리 정보 -->
[settings/]: (./)
[data/]: (data)
[default/]: (default)
[keymap/]: (keymap)
[lib/]: (lib)
[plugin/]: (plugin)
[syntax/]: (syntax)
[test/]: (test)
[var/]: (var)

<!-- 현재 파일 정보 -->
[CHANGELOG.md]: (CHANGELOG.md)
[ERRORLOG.md]: (ERRORLOG.md)
[TODO.org]: (TODO.org)
[settings.el]: (settings.el)
[first-settings.el]: (first-settings.el)
[last-settings.el]: (last-settings.el)
[customize-settings.el]: (customize-settings.el)

<!-- 하위 디렉토리 정보 -->

<!-- 하위 파일 정보 -->
[data/data.el]: (data/data.el)
[data/README.md]: (data/README.md)
[default/default.el]: (default/default.el)
[default/README.md]: (default/README.md)
[keymap/keymap.el]: (keymap/keymap.el)
[keymap/README.md]: (keymap/README.md)
[lib/lib.el]: (lib/lib.el)
[lib/README.md]: (lib/README.md)
[plugin/plugin.el]: (plugin/plugin.el)
[plugin/README.md]: (plugin/README.md)
[syntax/syntax.el]: (syntax/syntax.el)
[syntax/README.md]: (syntax/README.md)
[test/test.el]: (test/test.el)
[test/README.md]: (test/README.md)
[var/var.el]: (var/var.el)
[var/README.md]: (var/README.md)
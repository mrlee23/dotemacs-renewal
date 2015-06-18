## .emacs.d/settings/
### 개요
---
#### 설명
이맥스의 설정 파일이 위치해 있는 디렉토리이다.

[init.el] 을 제외한 모든 설정파일은 여기에 위치한다.

[../init.el] 로부터 [settings.el] 파일이 가장 처음 불려진다.

#### 파일이 로딩되는 순서
1. [settings.el]
   * [init.el] 파일이 로딩하는 첫번째 파일이다.
   * 이 파일은 [settings/] 내의 .el 파일을 논리적 순서에 맞게 로딩한다.
2. [first-settings.el]
   * [settings.el] 에서 [settings/] 디렉토리 내의 [default/default.el] , [keymap/keymap.el] 등이 실행되기 전에 먼저 실행된다.
3. [last-settings.el]
   * [settings/] 내에 존재하는 디렉토리 파일들이 모두 실행된 후 실행된다.
4. [customize-settings.el]
   * 이맥스에서 `customize` 를 이용해 설정된 것으로써 최종적으로 [settings.el] 에서 로딩된다.
   * [last-settings.el] 의 다음 순서로 로딩된다.

### 상세 기능 동작
---
#### 설명
현재 디렉토리 [settings/] 는 이맥스 설정의 메인 디렉토리로 볼 수 있다.

[init.el] 은 이맥스의 시작시 메인 디렉토리로 리다이렉션 하는 역할을 한다.

[packages/] 역시 소스코드를 담고 있는 소스 저장 창고이다.

[init.el] 에서는 [packages/] 관리까지만 하고 그 다음 단계의 설정은 [settings.el] 로 넘겨주기 때문에 [../packages/] 내의 패키지들은 이맥스 내장 패키지 처럼 작동하게 되어있다.

#### 순서대로 표현한 로딩 순서

1. **상위 디렉토리** ([.emacs.d/])
   1. [init.el] 실행
   2. [load-packages.el] 실행
2. **현재 디렉토리** ([.emacs.d/settings/])
   3. [settings.el] 실행
   4. [first-settings.el] 실행
3. **하위 디렉토리**
   5. [var/var.el] 실행
   6. [lib/lib.el] 실행
   7. [plugin/plugin.el] 실행
   8. [data/data.el] 실행
   9. [default/default.el] 실행
   10. [keymap/keymap.el] 실행
   11. [syntax/syntax.el] 실행
   12. \[ _[test/test.el]_ ***선택적 실행*** \]
4. **다시 현재 디렉토리** ([.emacs.d/settings/])
   13. [last-settings.el] 실행
   14. [customize-settings.el] 실행
   15. \[ _[simple-settings.el]_ ***선택적 실행*** \]

#### 계층적으로 표현한 로딩 순서

1. [init.el] 실행
   1. [load-packages.el] 실행, 완료
   2. [settings.el] 실행
	  1. [first-settings.el] 실행, 완료
	  2. [var/var.el] 실행, 완료
	  3. [plugin/plugin.el] 실행, 완료
	  4. [data/data.el] 실행, 완료
	  5. [default/default.el] 실행, 완료
	  6. [keymap/keymap.el] 실행, 완료
	  7. [syntax/syntax.el] 실행, 완료
	  8. \[ _[test/test.el]_ ***선택적 실행, 완료*** \]
	  9. [last-settings.el] 실행, 완료
	  10. [customize-settings.el] 실행, 완료
	  11. \[ _[simple-settings.el]_ ***선택적 실행, 완료*** \]
   3. [settings.el] 완료
2. [init.el] 완료

### 디렉토리 간단 설명
---
#### [var/]
이맥스 설정을 좀 더 원할하기 위한 이맥스 기본 시스템 변수를 설정한다.

Elisp 이 C 언어의 전처리기와 비슷한 동작을 하게 만들기 위해 (*선택적인 실행*) 만들어 졌다.

다른 설정들이 이 변수를 참조하여 실행하므로 가장 먼저 실행되어야 한다.

#### [lib/]
이맥스 설정을 좀 더 원할하게 돕기 위한 라이브러리이다.

[plugin/] 내의 설정 파일들이 주로 많이 쓴다.

그 이외에도 활용도는 무긍무진하다. 그러므로 [var/var.el] 다음의 우선순위를 가진다.

#### [plugin/]
외부 패키지가 아닌 내가 직접 만들어 쓰는 간단한 패키지들의 집합소이다.

기존의 my-plugin 을 계승한다.

외부 패키지가 `require` 되기 전에 외부 패키지 함수를 덮어 쓸때에도 사용한다. (*오버라이딩*)

그러므로 [default/default.el] 보다 선행되어야 한다.

#### [data/]
[auto-complete] , [yasnippet], theme 과 같이 사용자화가 가능하면서 데이터 양이 많아 따로 관리를 해야 할 때, 이 디렉토리에 패키지 명과 함께 디렉토리를 생성하여 따로 관리한다.

데이터들의 집합이므로, 패키지가 `require` 되기 전에 먼저 실행되어야 하므로 [default/default.el] 이 실행되기 전에 먼저 실행된다.

#### [default/]
각종 패키지를 이맥스 세션에 `require` 하는 작업과 더불어 기본적인 설정을 담당한다.

우선순위는 낮은편으로, [plugin/plugin.el] 이 선행되어야 한다.

#### [keymap/]
`require` 된 패키지를 기반으로 키 바인딩을 수행한다.

**이맥스의 꽃**이라고 할 수 있는 키 바인딩 관련 설정이다.

키 바인딩을 하기 전 미리 패키지가 `require` 되고 기본설정이 마친 상태가 되어야 하므로 [default/default.el] 이 선행되어야 한다.

#### [syntax/]
이맥스 모드에 따라 텍스트에 하이라이팅을 하거나 들여쓰기 등을 할 때 쓰인다.

주로 비주얼 적인 역할을 담당한다.

우선순위는 가장 낮다.

#### [test/]
이맥스에 설정된 기능들이 잘 작동하는지 유닛 테스트를 위한 정보를 담은 디렉토리이다.

주로 [feature] 를 이용하여 테스트를 한다.

### 파일 상세 설명
---
#### [CHANGELOG.md]

#### [ERRORLOG.md]
이맥스 설정을 하면서 생긴 에러를 해결하거나 해결하지 못했을 때, 날짜와 함께 해당 에러를 적고, 해결하였으면 해결 방법을 적어 놓는다.

날짜는 역시 최근 - 과거로 내림차순이다.

#### [TODO.org]
이맥스 설정에 관하여 해야할일 목록이다.

모든 설정파일은 이 하나의 TODO.org 에서 관리되므로 해야할일을 참조할 땐 오직 이 파일만 확인하면 된다.

#### [settings.el]
메인 설정 파일이다.

#### [first-settings.el]
맨 처음에 불러들이는 설정 파일이다.

#### [last-settings.el]
마지막으로 불러들이는 설정 파일이다.

#### [customize-settings.el]
이맥스 내장 `customize` 가 만들어내는 사용자 설정 파일으로써, `custom-file` 변수를 설정해야 한다.

가장 마지막에 실행되는 파일이다.

[default/default.el] 설정이 제대로 동작하지 못하는 원인이 될 수 있으며, 해당 파일의 내용은 지워도 무방하다. (모든 설정은 [default/default.el] 에 있기 때문)

#### [simple-settings.el]
이맥스에서 문제가 생겼을 때, 마지막에 즈음에 불러들이는 [keymap/keymap.el] 을 불러오지 못하는 경우를 대비해서 만들어진 설정 파일이다.

이 파일이 필요한 이유는 원인을 찾기위해서 `require` 를 하나씩 없애면서 디버깅을 해야 하는데, 그렇게 할 경우 기존 키바인딩을 사용할 수가 없게 된다.

기존 키바인딩을 사용하지 못하면 편집속도가 상당히 느려진다.

그래서 이러한 단점을 극복하기 위해 간단한 이동과 관련하여 키맵핑을 해놓은 파일이다.

평소에는(이맥스가 문제없이 잘 돌아갈 때) 쓸일이 없다.

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
[data/]: data
[default/]: default
[keymap/]: keymap
[lib/]: lib
[plugin/]: plugin
[syntax/]: syntax
[test/]: test
[var/]: var

<!-- 현재 파일 정보 -->
[CHANGELOG.md]: CHANGELOG.md
[ERRORLOG.md]: ERRORLOG.md
[README.md]: README.md
[TODO.org]: TODO.org
[settings.el]: settings.el
[first-settings.el]: first-settings.el
[last-settings.el]: last-settings.el
[customize-settings.el]: customize-settings.el
[simple-settings.el]: simple-settings.el

<!-- 하위 디렉토리 정보 -->

<!-- 하위 파일 정보 -->
[data.el]: data/data.el
[data/README.md]: data/README.md
[default.el]: default/default.el
[default/README.md]: default/README.md
[keymap.el]: keymap/keymap.el
[keymap/README.md]: keymap/README.md
[lib.el]: lib/lib.el
[lib/README.md]: lib/README.md
[plugin.el]: plugin/plugin.el
[plugin/README.md]: plugin/README.md
[syntax.el]: syntax/syntax.el
[syntax/README.md]: syntax/README.md
[test.el]: test/test.el
[test/README.md]: test/README.md
[var.el]: var/var.el
[var/README.md]: var/README.md

<!-- 절대 경로 -->
[.emacs.d/]: ../
[.emacs.d/settings/]: ../settings

<!-- 외부 링크 -->
<!-- Github -->
[auto-complete]: https://github.com/auto-complete/auto-complete
[yasnippet]: https://github.com/capitaomorte/yasnippet
[feature]: https://github.com/michaelklishin/cucumber.el

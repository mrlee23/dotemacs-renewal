## .emacs.d/packages
### 개요
---
이맥스에 바인딩 되는 외부 패키지를 관리하기 위한 디렉토리이다.

여기에 있는 모든 디렉토리는 가장 처음 [init.el] 에서 파일이 로딩된다.

자세한건 해당 [README.md] 참조.

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


[cask/](cask)
[elpa/](elpa)

[init.el](../init.el)
[README.md](../README.md)

[Cask](https://github.com/cask/cask)
[Melpa](http://melpa.org)
[Github](http://www.github.com)

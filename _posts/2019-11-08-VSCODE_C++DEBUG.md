---
layout: posts
title: Win10에서 Visual Studio Code C/C++ 사용하기
date: 2019-11-08
category: vscode
tags: vscode, mingw
sidebar:
  nav: "docs"
---
# [VSCODE 공식 가이드](https://code.visualstudio.com/docs/cpp/config-mingw)

공식 가이드 링크에서 조금만 찾아보면 다른 언어들에 대한 다양한 설명도 있으니 참고하면 좋습니다.

가이드를 요약하면
## 필요한 설치
1. VS CODE를 설치합니다.
2. VS CODE에서 EXTENSIONS의 C++ extension을 설치합니다.
3. [이곳](http://mingw-w64.org/doku.php/download/mingw-builds)에서 Mingw-w64를 설치합니다. 단, 설치 경로에 공백이 들어가지 않게 합니다.
4. Mingw-w64/bin 폴더의 경로를 윈도우 환경 변수에 추가합니다.
5. cmd를 열고 프로젝트 폴더를 생성합니다.
6. 생성한 프로젝트 폴더로 이동해 code .를 입력하면 해당 폴더가 작업 영역으로 설정되어 vs code가 실행됩니다.
---
## VS CODE 빌드 설정
1. vs code에서 `ctrl+shif+p`로 커맨드 창을 열고 `EDIT CONFIGURATIONS(UI)`를 찾습니다.
2. 컴파일러 경로를 설정해주고 intellisense mode를 gcc-x64로 설정해줍니다.
3. 8번 행동의 결과로 `.vscode`폴더와 `c_cpp_properties.json` 파일이 생성된 것을 확인할 수 있습니다.
4. vs code에서 `ctrl+shift+p`로 커맨드 창을 열고 `TASKS: CONFIGURE DEFAULT BUILD TASK`를 찾습니다.
5. OTHERS를 선택하고 링크와 동일하게 변수들을 설정해줍니다.
---
## VS CODE 디버깅 설정
1. vs code에서 `ctrl+shift+p`로 커맨드 창을 열고 `DEBUG: OPEN LAUNCH.JSON`를 찾습니다. 그리고 `GDB/LLDB`를 선택합니다.
2. 링크와 동일하게 설정하되, `MIDEBUGGERPATH`는 본인 컴퓨터의 gdb.exe 경로로 설정해줍니다.
3. 작업 영역에 `helloworld.cpp`로 파일을 생성한 후, 테스트 코드를 입력합니다.
4. 코드를 `ctrl+shift+b`로 빌드한 후, `F5`번을 누르면 디버깅이 가능합니다.

## 주의할 점
1. `MINGW`가 32비트 버전인지, 64비트 버전인지 확인
2. `C_CPP_PROPERTIES.JSON`의 `COMPILER PATH`, `INTELLISENSEMODE` 확인
3. `TASKS.JSON`의 `ARGS`변수의 값은 빌드할 소스파일의 이름과 같아야합니다. 더 궁금한 부분은 `G++`의 옵션을 알아보면 됩니다.
4. `LAUNCH.JSON`의 `MIDEBUGGERPATH` 확인
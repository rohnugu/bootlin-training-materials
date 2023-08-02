Teaching Material for AICS321 System Programming
-------------------------------------------------
Lecturer: Heejun Roh, Ph.D.

1. 작성법
 - `slides/first-slides` 디렉토리에 강사 소개 tex 파일을 만듬 (e.g., `heejun-roh.tex`)
 - `mk` 디렉토리에 `system-programming.mk` 파일을 생성 (e.g., `cp embedded-linux.mk system-programming.mk`)
 - `common` 디렉토리에 LaTeX 스타일 파일 (슬라이드의 경우 Beamer)을 만듬 (e.g., `cp beamerthemeBootlin.sty beamerthemeDNSLab.sty`)
 - LaTeX 스타일 파일에서 로고 부분 변경
   - `\includegraphics[width=0.04\textwidth]{common/koreauniv-logo.pdf}`
   - `\includegraphics[width=1cm]{common/logo-koreauniv-symbol.pdf}`
   - `\includegraphics[height=4cm]{common/koreauniv-logo-square.pdf}`   
 - `common` 디렉토리에 타이틀 템플릿을 만듬 (e.g., `cp embedded-linux-title.tex system-progarmming.tex`)
 - TRAINER는 make에서 전달하는 인자로 덮어쓰기가 가능하지만, STYLESHEET는 Makefile에서 전달을 무시하고 정의하고 있기 때문에 Makefile의 수정은 필수임. `STYLESHEET = common/beamerthemebootlin.sty`를 `STYLESHEET = common/beamerthemeDNSLab.sty`로 변경해야 함

```
make TRAINER=heejun-roh full-system-programming-slides.pdf
```
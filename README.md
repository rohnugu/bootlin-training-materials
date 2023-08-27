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

 - slides/first-slides에 `[트레이너 이름].tex`를 작성한 경우
```
make TRAINER=heejun-roh full-system-programming-slides.pdf
```

 - 그게 아니면 기본 모드로 빌드됨
```
make full-system-programming-slides.pdf
```

 - bootlin-training-materials과 LaTeX 템플릿 변경으로 인해 달라진 점
   * documentclass 글로벌 옵션에서 t 옵션을 줘서 beamer의 각 frame이 본문을 윗쪽 정렬되게 함 (beamer의 default는 가운데 정렬임)
     - 이로 인해 깨지는 슬라이드 (frame)은 \frame[t]로 옵션을 주어야 함
   * beamer에서 frame을 여러 단 (column)으로 나누는 columns에서 큰 그림으로 시작되는 단이 있으면 다른 단의 텍스트가 그림의 아래끝에 맞춰서 나타나는 문제를 해결하기 위해서 columns[T] 옵션을 주어야 함 (columns의 default인 t 옵션이 가지는 한계로 인한 것임)
   
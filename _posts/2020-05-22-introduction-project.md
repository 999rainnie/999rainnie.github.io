---
layout: post
title:  "프로젝트 소개"
date:   2020-05-22 18:05:55 +0300
image:  03.jpg
tags:   Jekyll
---

Pyxel은 파이썬으로 개발된 레트로 게임 엔진이다. Pyxel로 게임을 만들면 16가지 색상과 4개의 사운드를 이용하여 자유롭게 픽셀 아트 스타일 게임을 즐길 수 있다. Pyxel용 게임 콘솔 및 API 사양은 PICO-8 및 TIC-80을 나타내며, 오픈소스로 무료로 사용할 수 있다. 

___

# Specification

* Window, MAC, Linux 지원
* Python3으로 코드 작성
* 16색 고정 팔레트
* 256x256 크기의 이미지 뱅크 3개
* 256x256 크기의 타일 맵 8개
* 4개의 사운드 동시 재생, 64개의 정의 가능한 사운드
* 임의의 사운드를 조합 가능한 8개의 음악
* 키보드, 마우스, 게임 패드 입력
* 이미지 및 사운드 에디터

___

# Install examples

- [01_hello_pyxel.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/01_hello_pyxel.py) - Simplest application
- [02_jump_game.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/02_jump_game.py) - Jump game with Pyxel resource file
- [03_draw_api.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/03_draw_api.py) - Demonstration of drawing API
- [04_sound_api.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/04_sound_api.py) - Demonstration of sound API
- [05_color_palette.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/05_color_palette.py) - Color palette list
- [06_click_game.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/06_click_game.py) - Mouse click game
- [07_snake.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/07_snake.py) - Snake game with BGM
- [08_triangle_api.py](https://github.com/kitao/pyxel/blob/master/pyxel/examples/08_triangle_api.py) - Demonstration of triangle drawing API

___

# How to use

<strong> Create pyxel application </strong><br>

먼저 Python 코드 내에서 Pyxel 모듈을 import한 뒤, `init` 함수로 화면 크기를 지정한 후에, `run` 함수로 Pyxel 애플리케이션을 실행합니다.

```python
import pyxel

pyxel.init(160, 120)

def update():
    if pyxel.btnp(pyxel.KEY_Q):
        pyxel.quit()

def draw():
    pyxel.cls(0)
    pyxel.rect(10, 10, 20, 20, 11)

pyxel.run(update, draw)
```

`run` 함수의 인자로는 프레임 갱신을 처리하는 `update` 함수와, 필요할 때 화면을 그리는 `draw` 함수가 사용됩니다.

실제 애플리케이션에서는 아래와 같이 클래스에서 Pyxel 코드를 감싸는 것이 좋습니다:

```python
import pyxel

class App:
    def __init__(self):
        pyxel.init(160, 120)
        self.x = 0
        pyxel.run(self.update, self.draw)

    def update(self):
        self.x = (self.x + 1) % pyxel.width

    def draw(self):
        pyxel.cls(0)
        pyxel.rect(self.x, 0, 8, 8, 9)

App()
```

`show`나 `flip` 함수를 이용해 간단한 그래픽이나 애니메이션을 그리는 것도 가능합니다.

`show` 함수는 화면을 표시하고 `ESC` 키가 눌릴 때까지 대기합니다.

```python
import pyxel

pyxel.init(120, 120)
pyxel.cls(1)
pyxel.circb(60, 60, 40, 7)
pyxel.show()
```

`flip` 함수는 화면을 한 번 갱신하는 함수입니다.

```python
import pyxel

pyxel.init(120, 80)

while True:
    pyxel.cls(3)
    pyxel.rectb(pyxel.frame_count % 160 - 40, 20, 40, 40, 7)
    pyxel.flip()
```

___

# Editor

**이미지 에디터:**

이미지 뱅크를 편집하는 화면입니다.

<img src="https://raw.githubusercontent.com/kitao/pyxel/master/pyxel/editor/screenshots/image_editor.gif">

이미지 에디터 화면에 png 파일을 Drag & Drop하면, 이미지 파일을 선택 중인 이미지 뱅크에 추가할 수 있습니다.

**타일 맵 에디터:**

이미지 뱅크의 이미지를 타일 모양으로 늘어놓은 타일 맵을 편집하는 화면입니다.

<img src="https://raw.githubusercontent.com/kitao/pyxel/master/pyxel/editor/screenshots/tilemap_editor.gif">

**사운드 에디터:**

사운드를 편집하는 화면입니다.

<img src="https://raw.githubusercontent.com/kitao/pyxel/master/pyxel/editor/screenshots/sound_editor.gif">

**음악 에디터:**

사운드를 플레이 순서대로 늘어놓은 음악을 편집하는 화면입니다.

<img src="https://raw.githubusercontent.com/kitao/pyxel/master/pyxel/editor/screenshots/music_editor.gif">


___

# License

Pyxel is under MIT license. It can be reused within proprietary software provided that all copies of the licensed software include a copy of the MIT License terms and the copyright notice.


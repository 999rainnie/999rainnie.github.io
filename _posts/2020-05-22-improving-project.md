---
layout: post
title:  프로젝트 개선방안
date:   2020-05-22 15:01:35 +0300
image:  06.jpg
tags:   Style
---

## 1. Pyxel editor를 활용하여 직접 게임에 이미지, 사운드, 색깔 등을 추가
Pyxel editor로 애플리케이션에 이미지와 사운드를 제작할 수 있다. 이를 이용해서 게임에 필요한 이미지와 사운드를 추가하는 방향으로 프로젝트를 개선할 수 있다. 또 현재 게임 디자인에 적용할 수 있는 팔레트 색은 16개인데 이외에 다른 색을 추가한다.


## 2. pyxel을 이용한 3가지 게임에 대해 개선할 사항과 추가할 기능들 구현
pyxel/examples 파일의 세가지 게임을 여러 난이도로 진행할 수 있도록 구현한다. 
* jump_game.py와 snake_game.py의 속도 조절: 높은 level일수록 빠르게 움직이도록 하여 난이도를 조절할 수 있다. 
* jump_game.py에서 장애물들을 파괴하는 기능을 추가
* snake_game.py에서 snake가 먹으면 길이가 줄어드는 장치를 추가


## 3. pyxel을 이용한 새로운 게임을 프로젝트에 추가
현재 project에 없는 새로운 게임들을 추가한다.
* Tetris
* Copter
* WhatAmI
* FlappyClone

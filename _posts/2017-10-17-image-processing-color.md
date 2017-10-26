---
layout: post
section-type: post
title: (디지털 영상처리)삼자극치(tristimulus value)와 CIE 다이어그램
category: image-processing
tags: [ 'image-processing' ]
---

# 색깔(color)과 람다함수

## 색깔(color)

인간이 볼 수 있는 빛의 영역. 인간은 가시광선으로 색을 인식한다. 파장의 길이(nm, 나노미터)에 따라 성질이 변화하여 각각의 색깔로 나타난다.(400nm ~ 700nm)   
파장의 길이가 높은 순 -> 낮은 순으로 빨(700nm),주,노,초,파,남,보(400nm)가 표현된다.  

400nm보다 짧은 파장은 X선, 감마선, 자외선 등이 있으며, 700nm보다 큰 파장은 라디오파, 마이크로파 등이 있다. 물론 이런 파장은 눈에 보이지 않는다.

## 람다 함수

특정 색은 가시광선 대역에서 에너지 분포를 갖는다. 이를 **파장의 함수로 색을 기술 할 수 있는데,** 이 파장의 함수를 람다 함수(λ)라고 한다.  
람다 함수가 주어졌을 때(좌측 그림), 인간의 눈에는 서로 다른 반응곡선을 갖는 세 종류의 추상체가 있다.(우측 그림)    
이 세 종류의 추상체를 X(λ), Y(λ), Z(λ)로 표현할 수 있다.(하단의 그림 참조)

![lambda](/images/posts/lambda.png)

람다의 함수는 달라도 사람의 홍채를 통하면 색깔[x,y,z]이 같아보일 수 있는데, 이를 조건 등색(metameric pair)라고 한다.  

# 삼자극치(tristimulus value)

람다 함수의 [x,y,z], 즉 눈의 센서를 수치화 한것을 **3자극치(tristimulus value)** 라고 한다. [x,y,z]를 정규화 시키면 `x = X/(X+Y+Z), y = Y/(X+Y+Z), z = Z/(X+Y+Z)`가 되는데, `x+y+z=1` 이므로 x,y를 알면 자동적으로 z를 알수 있다. 그래서 두 개의 삼자극 계수인 [x,y]로만 색을 표현하게 된다.

# CIE 다이어그램

삼자극치(tristimulus value)로 좌표평면에 사람이 인식하는 색깔을 표현했을때, 그림은 아래와 같다.

![CIE](/images/posts/CIE.png)

- 곡선 궤적에 있는 색깔이 순수색(pure color), 좌표평면에 적힌 하얀색 숫자가 파장, 하얀 삼각형을 색 범위라고 한다. 이 하얀 삼각형은 컴퓨터에서 표현할 수 있는 색의 범위(CRT colors)를 말하는데, 삼각형의 범위는 컴퓨터마다 다르다.  
- 흰색을 정의할 때 위 그림에 표시된 Black Body Curve(흑채 곡선, 온도에 따른 색을 표현한 곡선)에서, 6500도에서의 색온도를 흰색으로 정의한다.  
- 특정 두 색을 좌표평면에서 정한 후(x1, y1과 x2,y2라고 하자), 그 두 색을 섞은 색은 (x1,y1)과 (x2, y2)를 잇는 선분 사이에 있다.
- 특정 pure color(x1,y1)와 흰색(x2,y2)를 이은 선분사이의 색들은 pure color의 채도에 따라 달라지는 색들이다.
- 두 색 C1, C2를 같은 양으로 섞어서 그것이 흰색이 되면, C1, C2가 **보색 관계** 에 있다고 한다.
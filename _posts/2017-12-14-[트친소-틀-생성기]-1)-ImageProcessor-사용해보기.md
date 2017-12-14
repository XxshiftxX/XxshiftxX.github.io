---
layout: post
current: post
navigation: true
title: "[트친소 틀 생성기] 1) ImageProcessor 사용해보기"
date: 2017-12-14 12:18:00
tags: fiction
class: post-template
author: shift
categories: 트친소 틀 생성기
---

시험이 끝난 기념으로 트친소를 돌리려고 하는데

트친소 틀이 너무 중구난방하게 흩어져있어서 찾기도 힘들거 이미지 하나하나 넣고 펜으로 체크하고...

너무 불편한 것 같아서 자동생성기를 만들어보기로 했다!

우선 처음 기획한 대로라면 이미지를 겹치거나 텍스트를 표시할 수 있어야 하기 때문에 이미지를 에디팅할 수 있는 라이브러리가 필요하다!

http://imageprocessor.org/

위 라이브러리는 이미지를 가지고 여러가지 편집을 하거나 효과를 줄 수 있는 라이브러리다!
Docs 자체에도 많은 것이 들어있지 않았을 뿐더러, 내가 필요한 기능은 이미지 위에 이미지를 오버랩시키고 텍스트를 삽입하는 것 정도가 전부였기 때문에 크게 어려운 것은 없었다.

```cs
ImageFactory imageFactory;
imageFacotry.Load(" // 이미지 경로 //")
			.Resize(new Size(250, 0))
            .Format(new PngFormat {Quality = 70})
            .Save(" // 이미지 경로 //");
```

ImageFactory라는 객체에 이미지를 로드(Load 함수)시키고, ImageFactory에 내장되어있는 다양한 함수를 통해 이미지를 가공한 후 이미지를 파일로 출력하거나 변수에 저장(Save 함수)하는 등의 행동이 가능하다.

다음 시간에는 WPF와 연동하여 사용자가 편하게 이미지를 가공할 수 있게 UI를 설계할 것 같다.

Github Repository : https://github.com/XxshiftxX/TwitterFriend
# SLICK SLIDER

![](https://code.d2.co.kr/sallykwak/study/02_slick/slick.PNG)

**the last carousel you'll ever need**

`너에게 필요한 마지막 스핀`

- http://kenwheeler.github.io/slick/
- https://cdnjs.com/libraries/slick-carousel

Browser Support : Chrome, Firefox, Safari, IE8 +



## 1. CDN

```
/* CDN css */
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.8.1/slick.css"/>
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.8.1/slick-theme.min.css"/>

/* CDN js */
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.8.1/slick.min.js"></script>
```

jQuery 1.7  이상 필요



## 2. Mark up

```
<div class="slider1">
	<div>slider1</div>
	<div>slider2</div>
	<div>slider3</div>
</div>

<script type="text/javascript">
$(document).ready(function(){
	$('.slider1').slick({
    	//셋팅값 입력
    });
});
</script>
```



## 3. Property

, 로 구분

- autoplay: ture, //자동 실행
- autoplaySpeed: 2000, // 자동 실행 시간치
- infinite: flase, //무한 롤링
- swipe: false, // 마우스 드래그 기능
- fade: true, // 사라지는 페이드 효과
- dots: true, // 페이지 버튼
- arrows: false, // 좌우 화살표 버튼
- slidesToScroll: 3, // 스크롤 할 슬라이드 수
- slidesToShow: 3, // 표시 할 슬라이드 수
- vertical: true, // 세로방향 슬라이드
- pauseOnHover: true, // 마우스 오버 시 제어
- responsive: [{속성}], // 반응형
- cssEase: 'liner',  // 효과



## 4. Setting

| Option         | Type     | Default                                                | Description                                 |
| -------------- | -------- | ------------------------------------------------------ | ------------------------------------------- |
| adaptiveHeight | boolean  | false                                                  | 슬라이더 높이를 현재 슬라이드 맞춘다        |
| arrows         | boolean  | true                                                   | 다음/이전 화살표                            |
| autoplay       | boolean  | false                                                  | 슬라이드 자동 재생                          |
| autoplaySpeed  | int      | 3000                                                   | 자동 재생 변경 간격                         |
| centerMode     | boolean  | false                                                  | 이전/다음 슬라이드가 있는 경우 가운데 보기. |
| cssEase        | string   | 'ease'                                                 | CSS3                                        |
| customPaging   | function | n/a                                                    | 사용자 지정 페이징                          |
| dots           | boolean  | false                                                  | 현재 슬라이드 표시 점                       |
| dotsClass      | string   | 'slick-dots'                                           | 슬라이드 표시 dot 클래스                    |
| easing         | string   | 'linear'                                               | animate () 대체                             |
| fade           | boolean  | false                                                  | fade 효과                                   |
| infinite       | boolean  | true                                                   | 무한반복                                    |
| nextArrow      | string   | <button type="button" class="slick-next">Next</button> | "다음" 화살표에 대한 html                   |
| prevArrow      | string   | <button type="button" class="slick-prev">Prev</button> | "이전" 화살표에 대한 html                   |
| responsive     | array    | null                                                   | 반응형                                      |
| slidesToScroll | int      | 1                                                      | 한 번에 스크롤 할 슬라이드 수               |
| slidesToShow   | int      | 1                                                      | 한 번에 표시 할 슬라이드 수                 |
| swipe          | boolean  | true                                                   | 마우스 드래그 기능                          |
| vertical       | boolean  | false                                                  | 수직 슬라이드 방향                          |



## 5. Events

```
// On before slide change
$('.slider1').on('beforeChange', function(event, slick, currentSlide, nextSlide){
	console.log(nextSlide);
});
```

| Event        | Params                                | Description                                                  |
| ------------ | ------------------------------------- | ------------------------------------------------------------ |
| afterChange  | event, slick, currentSlide            | 슬라이드 전환 콜백 후                                        |
| beforeChange | event, slick, currentSlide, nextSlide | 슬라이드 전환 콜백 전                                        |
| edge         | event, slick, direction               | 무한 모드에서 가장자리가 지나치게 커질 때 발생               |
| init         | event, slick                          | 처음 콜백을 초기화 할 때.<br />슬라이더를 초기화 하기전에 정의 |
| swipe        | event, slick, direction               | 드래그 후 발생                                               |



## 6. Method

```
// Add a slide
$('.slider1').slick('slickAdd',"<div></div>");

// Get the current slide
var currentSlide = $('.slider1').slick('slickCurrentSlide');
```

| Method            | Argument                              | Description                                                  |
| ----------------- | ------------------------------------- | ------------------------------------------------------------ |
| slick             | options : object                      | 초기화                                                       |
| slickNext         |                                       | 다음 슬라이드 트리거                                         |
| slickPrev         |                                       | 이전 슬라이드 트리거                                         |
| slickPause        |                                       | 자동 재생 일시중지                                           |
| slickPlay         |                                       | 자동 재생 시작                                               |
| slickGoTo         | index : int, <br />dontAnimate : bool | 두 번째 매개 변수가 true로 설정된 경우 <br />애니메이션을 건너 뛰고 색인별로 이동. |
| slickCurrentSlide |                                       | 현재 슬라이드 색인을 반환                                    |
| slickSetOption    |                                       | 옵션 변경                                                    |

> **Exemple**

```
$(element).slick({
	dots: true,
	speed: 500
});
```

change

```
$(element).slick('slickSetOption', 'speed', 5000, true);
```



## 7. Example

1. basic : https://code.d2.co.kr/sallykwak/study/02_slick/01_basic.html 
2. center mode : https://code.d2.co.kr/sallykwak/study/02_slick/02_center.html 
3. side : https://code.d2.co.kr/sallykwak/study/02_slick/03_side.html 
4. both : https://code.d2.co.kr/sallykwak/study/02_slick/04_both_side.html 
5. responsive : https://code.d2.co.kr/sallykwak/study/02_slick/05_responsive.html 
6. controls : https://code.d2.co.kr/sallykwak/study/02_slick/06_controls.html 
7. progress bar : https://code.d2.co.kr/sallykwak/study/02_slick/07_progressbar.html 
8. video : https://code.d2.co.kr/sallykwak/study/02_slick/08_video.html 
9. mousewheel : https://code.d2.co.kr/sallykwak/study/02_slick/09_mousewheel.html 
10. data : https://code.d2.co.kr/sallykwak/study/02_slick/10_data.html 

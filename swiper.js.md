# swiper.js
スライダーを簡単に作れるjsライブラリ
```
<div class="swiper">
    <!-- ↑スライダーを掛けたい要素にswiperクラスを書く -->
    <div class="swiper-wrapper">
    <!-- ↓スライドにはswiper-slide -->
    <div class="swiper-slide"><img src="images/image-1.jpg" alt=""></div>
    <div class="swiper-slide"><img src="images/image-2.jpg" alt=""></div>
    <div class="swiper-slide"><img src="images/image-3.jpg" alt=""></div>
    ...
    </div>
    <!-- If we need pagination -->
    <div class="swiper-pagination"></div>

    <!-- If we need navigation buttons -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>

    <!-- If we need scrollbar -->
    <div class="swiper-scrollbar"></div>
</div>
```

```
const swiper = new Swiper('.swiper', {
    // Optional parameters
    //direction: 'vertical', verticalを指定すれば縦方向にスライド、層じゃなければ横になる
    loop: true,//ループするかどうか
    effect: "coverflow",//スライドするときのエフェクト"fade"とかいろいろある
    // If we need pagination
    pagination: {
      el: '.swiper-pagination',
    },
  
    // Navigation arrows
    navigation: {
      nextEl: '.swiper-button-next',
      prevEl: '.swiper-button-prev',
    },
  
    // And if we need scrollbar
    scrollbar: {
      el: '.swiper-scrollbar',
    },
  });
```
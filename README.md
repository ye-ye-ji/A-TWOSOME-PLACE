# A-TWOSOME-PLACE

기존 투썸플레이스 홈페이지를 리뉴얼한 웹페이지입니다.<br>
3명(디자인 1명 & 퍼블리싱 2명)이 팀을 이루어서 제작했으며<br>
 슬랙을 사용하여 파일을 업로드하고 피드백 받는 방식으로 협업했습니다.<br>
- [투썸플레이스 홈페이지](https://www.twosome.co.kr:7009/main.asp)
- [투썸플레이스 리뉴얼 페이지](http://yeji-jung.com/project/Twosome/common/main/index.html)

###### * *리뉴얼 페이지는 구글 크롬 브라우저에 최적화되어 있습니다.* ######

<h2>메인 페이지</h2>
<h4>1. Swiper 플러그인을 사용하여 이미지가 슬라이드 되도록 작업했습니다.</h4>

![slide](https://user-images.githubusercontent.com/74514595/113393027-0407cc80-93d1-11eb-86ed-c28e3f20c531.jpg)
    
    var swiper = new Swiper('.mainVisual .swiper-container', {
        slidesPerView: 1,
        spaceBetween: 10,
        loop: true,
        loopAdditionalSlides: 1,
        centeredSlides: true,
        autoplay: {
            delay: 3000,
            disableOnInteraction: false,
        },
        pagination: {
            el: '.mainVisual .swiper-pagination',
            clickable: true,
        },
    });

<h4>2. GNB에 마우스를 올리면 2depth가 나타납니다.</h4>

![GNB](https://user-images.githubusercontent.com/74514595/113502650-968ea400-9568-11eb-99e0-c1f371f284af.jpg)
   
    var dep1 = $('#header .wrapper #gnb > li'),
        dep2 = $('#header .wrapper #gnb > li > .dep2'),
        gnbNum = -1;
        
    dep1.each(function (i) {
        dep1.mouseenter(function () {
            gnbNum = i;
            $(this).stop().eq(gnbNum).children('.dep2').fadeIn(300, function () {
                $(this).stop().siblings('a').addClass('active');
            });

        });
        dep1.mouseleave(function () {
            gnbNum = i;
            $(this).stop().eq(gnbNum).children('.dep2').fadeOut(300, function () {
                $(this).stop().siblings('a').removeClass('active');
            });
        });
    });
   
 <h4>3. 우측에 퀵 메뉴를 배치했으며 상단으로 자동 스크롤되는 버튼을 넣었습니다.</h4>
   
![btn](https://user-images.githubusercontent.com/74514595/113395235-804fdf00-93d4-11eb-975c-bd882866ed12.jpg)

    $('.top-bt').click(function () {
        $('html, body').animate({
            scrollTop: 0
        }, 400);
        return false;
    });
    
<h2>서브 페이지</h2>
<h4> 1. NEW MENU : 제품을 클릭하면 상세설명과 영양성분표가 나타나도록 구현했습니다.</h4>

![menu](https://user-images.githubusercontent.com/74514595/113396553-a9716f00-93d6-11eb-82dc-0da1a6070393.jpg)

    1. detail 에 display:none 을 적용하여 첫 화면에 a 태그의 내용이 보이도록 구현했습니다.
        <li>
            <div class="detail list1">
                <div class="pro_descript">
                    <h3>스트로베리 라떼</h3>
                    <span>Strawberry Latte</span>
                    <p>달콤한 스트로베리와 부드러운 우유가<br>
                        조화롭게 만난 스트로베리 시즌 시그니처 음료</p>
                </div>
                <div class="pro_nutri">
                    <div class="pro_nutri_conwrap">
                        <dl>
                            <dt>1회 제공량</dt>
                            <dd>414ml</dd>
                        </dl>
                        <dl>
                            <dt>칼로리</dt>
                            <dd>210Kcal</dd>
                        </dl>
                    </div>
                </div>
            </div>
            <a href="#">
                <img src="../common/images/list_product_3_1.png" alt="스트로베리 애플 비안코 프라페">
                <h3>스트로베리 라떼</h3>
                <span>Strawberry Latte</span>
                <div class="datail_bg list1"></div>
            </a>
        </li>
    
    2. 각 li에 마우스를 올리면(li:hover) 제품 상세 이미지(.datail_bg)가 보입니다.
        .list_product li:hover .datail_bg{display: block;}
        .list_product li .datail_bg{display: none; position: absolute; top: 0; width: 100%; height: 100%;}
    
    3. 클릭하면 detail의 display가 block이 되어 상세설명이 보입니다.
        var $list = $("#con_wrap .container .list_product"),
            $listbt = $list.children("li"),
            $detail = $listbt.children(".detail"),
            gnbNum = -1;

        $listbt.each(function(i){      
            $listbt.on('click',function(e){
                gnbNum = i;
                e.preventDefault();
                $(this).eq(gnbNum).children(".detail").toggle();
            });
        });

#### 2. [매장찾기](http://yeji-jung.com/project/Twosome/common/store/store.html), [투썸 리워드](http://yeji-jung.com/project/Twosome/common/reword/reword.html), [진행중인 이벤트](http://yeji-jung.com/project/Twosome/common/sub-menu/event/eventList.html) 페이지에 방문해보세요. ####

![map](https://user-images.githubusercontent.com/74514595/113665507-8b628200-96e8-11eb-9e59-9eea7c31dac3.jpg)

![reword](https://user-images.githubusercontent.com/74514595/113504271-fb9ac780-9571-11eb-9ec9-79ad6aef5730.jpg)

## 참고 사이트 ##
Swiper : https://swiperjs.com/ 

##### [리뉴얼 페이지](http://yeji-jung.com/project/Twosome/common/main/index.html) 에 직접 방문해보세요. #####

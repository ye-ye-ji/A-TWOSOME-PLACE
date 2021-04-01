# A-TWOSOME-PLACE

기존 투썸플레이스 홈페이지를 리뉴얼한 웹페이지입니다.<br>
3명(디자인 1명 & 퍼블리싱 2명)이 팀을 이루어서 제작했으며,<br>
슬랙을 사용하여 디자인 파일, 코딩파일을 업로드하고 피드백 받는 방식으로 협업했습니다.<br>
- [투썸플레이스 홈페이지](https://www.twosome.co.kr:7009/main.asp)
- 투썸플레이스 리뉴얼 페이지

<h2>메인 페이지</h2>
1. Swiper 플러그인을 사용하여 이미지가 슬라이드 되도록 작업했습니다.<br> 
    
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

    $('.top-bt').click(function () {
        $('html, body').animate({
            scrollTop: 0
        }, 400);
        return false;
    });
    
    $(function () {
        $(window).scroll(function () {
            var scroll_height = $(document).scrollTop();
            if (1334 <= scroll_height) {
                $(".btn-area").fadeIn();
            } else {
                $(".btn-area").fadeOut();
            }
        });
    });
    


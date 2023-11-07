<template>
    <section class="maincontents">
        <section class="mainbanner"><img src="/images/mainimg.jpg"></section>
        <section class="newbook">
            <h1 class="maintit">
                작업물<span>분야별로 감상해보세요</span>
            </h1>
            <div class="tapcontent">
                <div class="tap">
                    <b-button variant="tap active" @click="AddContents('Newbooks_it')">가구 디자인</b-button>
                    <b-button variant="tap" @click="AddContents('Newbooks_work')">가전 디자인</b-button>
                    <b-button variant="tap" @click="AddContents('Newbooks_photo')">캐릭터 디자인</b-button>
                    <b-button variant="tap " @click="AddContents('Newbooks_science')">일러스트</b-button>
                </div>
                <VueSlickCarousel class="mainslider" v-bind="settings">
                    <div class="rollimg" v-for="(item, index) in Newbooks" :key="index">
                        <span class="imgbox"><img :src="item.imgurl" /></span>
                        <strong v-html="item.name"></strong>
                        <span class="textbox" v-html="item.subdec"></span>
                    </div>
                </VueSlickCarousel>
            </div>
        </section>

        <section class="searchbook">
            <h1 class="maintit">
                서브메뉴<span>곧 추가될 예정입니다</span>
            </h1>
        </section>
          
            <section class="bannermenu"> 
            <div class="itembox" v-for="(item,index) in mainbanner" :key="index" @click="gotoPage(item.url)">
                <span v-html="item.stitle"></span>
                <strong v-html="item.maintit"></strong>
                <i class="bi" :class="item.iconname"></i>
            </div>
            </section>
        <section class="notice">
            <div class="noticebox">
            <h1 class="maintit">공지 사항</h1>
            <b-button variant="noticemore" @click="viewmore($event)"/>
                <div class="newsitem" v-for="(item, index) in noticelists" :key="index">
                    <strong v-html="item.noticetit"></strong>
                    <span v-html="item.date"></span>
                </div>
            </div>
        </section>
    </section>
</template>


<script>
export default{
    data() {
        return{
            Newbooks: [],
            Newbooks_it: [
                {
                    imgurl: "/images/books_image/book01.jpg",
                    name: "Layerd Desk",
                    subdec: "2021 졸업작품으로 제작된 작업용 책상입니다...",
                },
                {
                    imgurl: "/images/books_image/book02.jpg",
                    name: "Hue Stool",
                    subdec: "간단하게 들어올리면서 스툴에서 누울 수 있는 공간으로 변형이 가능합니다.",
                },
                {
                    imgurl: "/images/books_image/book03.jpg",
                    name: "Bookcase",
                    subdec: "자유롭게 칸막이를 이동할 수 있습니다.",
                },
                {
                    imgurl: "/images/books_image/book04.jpg",
                    name: "FRP Stool",
                    subdec: "이렇게 가벼운 스툴이 있나?",
                },
               
            ],
            Newbooks_work: [
                {
                    imgurl: "/images/books_image/book06.jpg",
                    name: "Cleon",
                    subdec: "Led 마스크입니다...",
                },
                {
                    imgurl: "/images/books_image/book07.jpg",
                    name: "Hue -Rest",
                    subdec: "휴대폰 살균기",
                },
                {
                    imgurl: "/images/books_image/book08.jpg",
                    name: "Sprout vaccum",
                    subdec: "휴대용 미니청소기",
                },
                {
                    imgurl: "/images/books_image/book09.jpg",
                    name: "Retro Radio",
                    subdec: "레트로 라디오",
                },
            ],
            Newbooks_photo: [
                {
                    imgurl: "/images/books_image/book11.jpg",
                    name: "깐귤이",
                    subdec: "2018 아트토이공모전에 공모했던 귤껍질 캐릭터입니다...",
                },
                {
                    imgurl: "/images/books_image/book12.jpg",
                    name: "도리토스",
                    subdec: "도리를 찾아서의 '도리'와 금융기업 '토스'를 콜라보해 제작했습니다.",
                },
                {
                    imgurl: "/images/books_image/book13.jpg",
                    name: "발광이끼냥",
                    subdec: "우주 발광이끼를 먹고 살던 슬라임을 가공해서 만들어진 우주고양이입니다.",
                },
                {
                    imgurl: "/images/books_image/book14.jpg",
                    name: "세얼간이",
                    subdec: "네이처파크 공모전에 공모했던 캐릭터들로 돼지꼬리 원숭이, 왕관앵무, 살가타육지거북...",
                },
                {
                    imgurl: "/images/books_image/book15.jpg",
                    name: "세한티콘",
                    subdec: "세한이라는 큐트한 정령이 있습니다.",
                },
            ],
            Newbooks_science: [
                {
                    imgurl: "/images/books_image/book21.jpg",
                    name: "Graduation work",
                    subdec: "졸업작품으로 작업한 책상을 넣어봤습니다!",
                },
                {
                    imgurl: "/images/books_image/book22.jpg",
                    name: "Space Frog",
                    subdec: "오버워치의 루시우를 아시나요?",
                },
                {
                    imgurl: "/images/books_image/book23.jpg",
                    name: "cold",
                    subdec: "에어컨은 적당히 틉시다!",
                },
                {
                    imgurl: "/images/books_image/book24.jpg",
                    name: "Venice",
                    subdec: "베니스에 가보고 싶네요",
                },
                {
                    imgurl: "/images/books_image/book25.jpg",
                    name: "Cr2ate",
                    subdec: "3D프린터가 있는 작업실이 갖고싶군요",
                },
            ],

                mainbanner: [
                    {
                        stitle: "포트폴리오 아직 준비중입니다.",
                        maintit: "비핸스",
                        iconname: "bi-stickies",
                        url: "https://www.behance.net/jun777k8075"
                    },
                    {
                        stitle: "블로그",
                        maintit: "네이버 블로그",
                        iconname: "bi-book-half",
                        url: "https://blog.naver.com/jun777k"
                    },
                    {
                        stitle: "Kiwibird_studio",
                        maintit: "인스타그램",
                        iconname: "bi-instagram",
                        url: "https://www.instagram.com/kiwibird_studio/"
                    },
                ],

                noticelists: [
                    {
                        noticetit:"웹 포트폴리오는 매주 업데이트 됩니다",
                        date: "2023.10.17",
                    },
                    {
                        noticetit:"명절 잘 보내세요. 추석에는 쉽니다",
                        date: "2023.09.17",
                    },
                    {
                        noticetit:"취업 준비 시작합니다!",
                        date: "2023.09.10",
                    },
                ],

            settings: {
                slidesToShow: 5,
                arrows: true,
                dots: false,
                infinite: true,
                responsive: [
                    //반응형 옵션
                    {
                        breakpoint: 767,
                        settings: {
                            slidesToShow: 4,
                        },
                    },
                    {
                        breakpoint: 414,
                        settings: {
                            slidesToShow: 2,
                        },
                    },
                ],
            },
        };
    },
    created() {
        this.Newbooks = this.Newbooks_it;
    },
    methods:{
        AddContents(contents) {
            this.Newbooks = this[contents];
            document.querySelector(".active").classList.remove("active");
            event.target.classList.add("active");
        },
        gotoPage(url) {
            if (url == "/classsample") {
                this.$router.push(url);
            } else {
                window.open(url, "_blank");
            }
            },
            viewmore(event) {
                if (event.target.parentElement.classList.value.indexOf("full") > -1) {
                    event.target.parentElement.classList.remove("full");
                } else {
                    event.target.parentElement.classList.add("full");
                }
            },
        },
    };
</script>
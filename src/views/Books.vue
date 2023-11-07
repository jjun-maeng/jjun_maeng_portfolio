<template>
    <Subpage :pagetit ="'작업물 소개'">
        <div class="bookpage">
            <VueSlickCarousel class="subpageslider" v-bind="settings"
            @init="handleInit" ref="carousel">
                    <div class="rollimg" :class="{ active: index === tabIndex }" 
                    v-for="(item, index) in Newbooks" :key="index" 
                    @click="Clicklink(index)">
                        <span class="imgbox"><img :src="item.imgurl" /></span>
                        <strong v-html="item.name"></strong>
                    </div>
                </VueSlickCarousel>
                <component
                :is="componentslist[tabIndex]"
                :bookUrl="Newbooks[tabIndex].imgurl"
                :bookName="Newbooks[tabIndex].name"
                :bookDec="Newbooks[tabIndex].dec"
            >
            </component>
        </div>
    </Subpage>
</template>

<script>
import Subpage from "@/layout/components/Subpage.vue";
import BookDetail1 from "./BookDetail1.vue";
import BookDetail2 from "./BookDetail2.vue";
import BookDetail3 from "./BookDetail3.vue";
import BookDetail4 from "./BookDetail4.vue";
import BookDetail5 from "./BookDetail5.vue";
import BookDetail6 from "./BookDetail6.vue";
import BookDetail7 from "./BookDetail7.vue";
import BookDetail8 from "./BookDetail8.vue";
import BookDetail9 from "./BookDetail9.vue";
import BookDetail10 from "./BookDetail10.vue";
import BookDetail11 from "./BookDetail11.vue";
import BookDetail12 from "./BookDetail12.vue";
import BookDetail13 from "./BookDetail13.vue";
import BookDetail14 from "./BookDetail14.vue";
export default {
    components: {
        Subpage,
        BookDetail1,BookDetail2,BookDetail3,BookDetail4,
        BookDetail5,BookDetail6,BookDetail7,BookDetail8,BookDetail9,
        BookDetail10,BookDetail11,BookDetail12,BookDetail13,BookDetail14
    },
    mounted() {
        if (!this.$route.query.tabId) {
            this.tabIndex = 0;
        } else {
            this.tabIndex = Number(this.$route.query.tabId);
        }
    },
    data() {
        return{
            Newbooks: [
                {
                    imgurl: "/images/books_image/book01.jpg",
                    name: "Layerd Desk",
                    dec: "레이어드 데스크"
                },
                {
                    imgurl: "/images/books_image/book02.jpg",
                    name: "Hue Stool",
                    dec: "휴 스툴"
                },
                {
                    imgurl: "/images/books_image/book03.jpg",
                    name: "Bookcase",
                    dec: "책꽂이"
                },
                {
                    imgurl: "/images/books_image/book04.jpg",
                    name: "FRP Stool",
                    dec: "FRP 스툴"
                },
                {
                    imgurl: "/images/books_image/book06.jpg",
                    name: "Cleon",
                    dec: "Cleon LED 마스크"
                },
                {
                    imgurl: "/images/books_image/book07.jpg",
                    name: "Hue-Rest",
                    dec: "휴레스트 휴대폰 살균기"
                },
                {
                    imgurl: "/images/books_image/book08.jpg",
                    name: "Sprout Vaccum",
                    dec: "새싹 청소기"
                },
                {
                    imgurl: "/images/books_image/book09.jpg",
                    name: "Retro radio",
                    dec: "레트로 라디오"
                },
                {
                    imgurl: "/images/books_image/book11.jpg",
                    name: "깐귤이",
                    dec: "귤껍질 캐릭터"
                },
                {
                    imgurl: "/images/books_image/book12.jpg",
                    name: "도리토스",
                    dec: "도리토스"
                },
                {
                    imgurl: "/images/books_image/book13.jpg",
                    name: "발광이끼냥",
                    dec: "우주고양이"
                },
                {
                    imgurl: "/images/books_image/book14.jpg",
                    name: "세 얼간이",
                    dec: "네이처파크 캐릭터 공모전"
                },
                {
                    imgurl: "/images/books_image/book15.jpg",
                    name: "세한티콘",
                    dec: "심심해서 만든 이모티콘"
                },
                {
                    imgurl: "/images/books_image/book21.jpg",
                    name: "당신의 방을 소개해주세요",
                    dec: "방 꾸미기 일러스트"
                },
            ],


            settings: {
                slidesToShow: 8,
                arrows: true,
                dots: false,
                infinite: true,
                responsive: [
                    {
                        breakpoint: 1023,
                        settings: {
                            slidesToShow: 5,
                        },
                    },
                    {
                        breakpoint: 767,
                        settings: {
                            slidesToShow: 2,
                        },
                    },
                ],
            },
            componentslist: [
                BookDetail1,BookDetail2,BookDetail3,BookDetail4,
                BookDetail5,BookDetail6,BookDetail7,BookDetail8,BookDetail9,BookDetail10,BookDetail11,BookDetail12,BookDetail13,BookDetail14
            ],
            tabIndex: 0,
          
        };
    },
    methods: {
        Clicklink(tabIndex) {
            if (!(this.$route.query.tabId == tabIndex)) {
                this.tabIndex = tabIndex;
                return this.$router.push("/book?tabId=" + tabIndex);
            }
        },
        handleInit() {
            this.$nextTick(() => {
                this.$refs.carousel.goTo(this.tabIndex);
            });
        },
    },
};
</script>
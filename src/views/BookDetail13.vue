<template>
    <section class="bookdetail">
        <h1 class="booktitle">
            {{ bookName }}
            <span>{{ bookDec }}</span>
        </h1>
        <div class="book-info">
            <div class="imgview">
                <div class="imgbook"><img :src="bookUrl" alt="" /></div>
                <div class="bookbtns">
                    <b-button variant="lightgray">
                    <i class="bi bi-search" />자세히 보기
                    </b-button>
                    <b-button variant="lightgray">
                    <i class="bi bi-hdd" />판넬
                    </b-button>
                </div>
            </div>
            <div class="infolist">
                <ul>
                    <li v-for="(item, index) in bookinfolists" :key="index">
                        <span class="label" v-html="item.label"></span>
                        <span class="infocontent" v-html="item.content"></span>
                    </li>
                </ul>
            </div>
        </div>
        <div class="book-detailinfo">
            <div class="detailTap">
                <b-form-radio
                name="detail-tap"
                v-model="tapselect"
                value="introduce"
                button
                button-variant="detailtap">
                    <i class="bi bi-mic" />소개
                </b-form-radio>
                <b-form-radio
                name="detail-tap"
                v-model="tapselect"
                value="review"
                button
                button-variant="detailtap">
                    <i class="bi bi-chat-left-text" />디자인 배경
                </b-form-radio>
                <b-form-radio
                name="detail-tap"
                v-model="tapselect"
                value="order"
                button
                button-variant="detailtap">
                    <i class="bi bi-layout-text-sidebar-reverse"/>디테일
                </b-form-radio>
                <b-form-radio
                name="detail-tap"
                v-model="tapselect"
                value="write"
                button
                button-variant="detailtap">
                    <i class="bi bi-journal-text" />후기
                </b-form-radio>
                <b-form-radio
                name="detail-tap"
                v-model="tapselect"
                value="recommendation"
                button
                button-variant="detailtap">
                    <i class="bi bi-person-check" />사진
                </b-form-radio>
                <b-form-radio
                name="detail-tap"
                v-model="tapselect"
                value="reference"
                button
                button-variant="detailtap">
                    <i class="bi bi-inboxes" />자료실
                </b-form-radio>
            </div>
            <template v-if="tapselect === 'introduce'">
                <div class="detailTapCon">
                    <h1 class="tapcontit"><strong>"{{ bookName }}"</strong>를 소개합니다.</h1>
                    <p>
                        <strong>귀여운 히키코모리 정령 세한이! <br />한번 만나보는 것도 좋을지도 모릅니다.<br></strong><br>
                        <img src="images/books_image/book15.jpg"/><br><br> 
                    </p>
                </div>
            </template>
            <template v-else-if="tapselect=='review'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경입니다.</h1>
                <p>
                    <strong>2022년 4월 17일 파워블로거 세한쿤의 생일을 맞아 제작한 이모티콘입니다.
                        <br>스티커로도 제작 예정입니다.<br> 앗 참고로 세한이는 티코를 굉장히 좋아한답니다!
                    </strong><br><br>
                    
                    <img src="images/sekan01.jpg"/><br><br>
                    <img src="images/sekan02.jpg"/><br><br>
                    <img src="images/sekan03.jpg"/><br><br>
                    <img src="images/sekan04.jpg"/><br><br>
                    <img src="images/sekan05.jpg"/><br><br>

                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='order'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다</h1>
                <p>
                    <strong>세한티콘 입니다.</strong><br><br>
                    <img src="images/sekan06.jpg"/><br><br>              
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='write'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
                <p>
                    세한티콘은 깐귤티콘 이후로 두번째 이모티콘입니다.<br>
                    그저 저의 책임없는 쾌락을 위한 것이라서 큰 의미는 없지만 은근 귀엽습니다.<br>
                    하루빨리 파워블로거 세한이의 실체가 세상에 알려졌으면 하는 마음입니다.<br>
                    아 그리고 세한티콘은 실물과 거의 유사하다고 보면 된답니다~!!<br><br>
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='recommendation'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
                <p>
                    <strong>스케치</strong><br>
                    <img src="images/sekan07.jpg"/><br><br>              
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='reference'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
                <p>블로그에서도 확인 하실 수 있습니다.</p>
                </div>
            </template>
        </div>
    </section>
</template>
<script>
export default {
    props: ['bookName', 'bookDec', 'bookUrl'],
    data() {
        return {
        bookinfolists: [
                { label: "디자이너", content: "김준명"},
                { label: "제작 기간", content: "2022-04-17"},
                { label: "사이즈", content: "20*20"},
                { label: "재료", content: "리무버블 용지"},
                { label: "사용 프로그램", content: "Clip Studio"},
                { label: "사용툴", content: ""},
                { label: "설명", content: "저의 대학시절 룸메 세한이를 소개합니다."},
        ],
        tapselect: "introduce",
        };
    },
};
</script>
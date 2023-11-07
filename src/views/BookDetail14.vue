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
                        <strong>당신의 방을 소개시켜주세요!<br>
              다양한 포스트카드와 스티커로 당신의 방을 일러스트로 표현해보세요!<br><br>
             </strong>
              
             <img src="images/room01.jpg"/>
                    <br><br>
                    
                        SNS 인스타그램에서 @kiwibird_studio라는 계정으로 활동했던 일러스트 작품들입니다.<br>
                        이 작품 외에도 다양한 엽서와 스티커로 꾸며진 샘플들이 있습니다.
                        메인 홈에서 SNS 인스타그램 링크로 들어가시거나<br>
                        https://www.instagram.com/kiwibird_studio/
                        로 접속해주시면 샘플들을 보실 수 있습니다.
                    </p>
                </div>
            </template>
            <template v-else-if="tapselect=='review'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경입니다.</h1>
                <p>
                    이 프로젝트는 고객이 자신의 방을 굿즈로 커스터마이징할 수 있도록<br>
                    다양한 컬러 조합의 벽지 엽서와 가구 소품 스티커들을 제공하는 서비스를 목표로 시작했습니다.<br><br>
                    <img src="images/room02.jpg"/><br><br>

                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='order'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다</h1>
                <p>
             <img src="images/room10.jpg"/>   
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='write'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
                <p>
                    <strong>프로젝트를 마치면서...</strong><br><br>
                    자신의 공간을 꾸민다는 것은 정말 뿌듯하기도 하고 누군가에겐 목표이기도 합니다.<br>
                    저는 그 공간을 일러스트화해서 다른 사람에게도 자랑할 수 있도록 다양한 색감의 벽지 엽서와<br>
                    소품 스티커들을 제공하는 콘텐츠를 만들어보는 목표로 처음에 프로젝트를 시작했습니다.<br>
                    당시 트렌드 중 하나였던 다이어리 꾸미기처럼 무언가를 꾸민다는 컨셉과 방로 새로운 트렌드를 만들어보고 싶었습니다.<br>
                    간단하게 똑같은 형식의 배색이 다른 엽서에 소품스티커들을 배치해 자신만의 일러스트 엽서를 만들 수 있는 것이죠.<br>
                    하지만 세상에는 많은 배색과 가구 소품이 있습니다. <br>
                    그래서 일단 차근차근 샘플을 그려보면서 데이터를 쌓고, 배색에서 오는 방의 분위기 <br>
                    등을 한번 연구해보고 싶어 키위스튜디오라는 인스타그램 계정을 만들었습니다.<br>
                    순조롭게 1년 8개월 정도를 진행하다가 중간에 발을 다치게 되었는데, 이것이 참...<br>
                    책상에 앉아서 작업을 할 수가 없어서 한동안 쉬다보니 뭔가 여유가 없어진 기분이었답니다 ㅎ<br>
                    핑계같지만, 그 뒤로 작업을 하기가 힘들어서 무기한으로 쉬게 되었습니다. <br><br>

                    이 프로젝트는 여유가 생길때 쯤 언제든 다시 할 생각은 있습니다.<br>
                    대략 2024년 쯤에는 다시 시작해볼까 합니다 ㅎㅎ!<br>
                    그동안 너무 오래 쉬어서 팔로우해주신 분들에게는 죄송하고 아주 감사하고 있습니다.<br>
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='recommendation'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
                <p>
                    <strong>일부 샘플입니다! <br> 더 많은 샘플을 보시려면 인스타를 방문해주세요!</strong><br><br>
                    <img src="images/room09.jpg"/><br><br>
                    <img src="images/room03.jpg"/><br><br>
                    <img src="images/room08.jpg"/><br><br>
                    <img src="images/room05.jpg"/><br><br>
                    <img src="images/room06.jpg"/><br><br>
                    <img src="images/room07.jpg"/><br><br>              
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='reference'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
                <p>메인 홈에서 SNS 인스타그램 링크로 들어가시거나 
                        https://www.instagram.com/kiwibird_studio/<br>
                        로 접속해주시면 샘플들을 보실 수 있습니다.</p>
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
                { label: "제작 기간", content: "2020-02-01 ~ 2021-11-04"},
                { label: "사이즈", content: "210*148 엽서 사이즈"},
                { label: "재료", content: "고급지(랑데뷰) 210g, 리무버블 용지"},
                { label: "사용 프로그램", content: "Illustrator"},
                { label: "사용툴", content: "레이저 프린터"},
                { label: "설명", content: "다양한 컨셉의 일러스트가 있습니다"},
        ],
        tapselect: "introduce",
        };
    },
};
</script>
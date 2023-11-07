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
                        <strong>레이어처럼 기능을 나눠쓰는 데스크! <br />상판의 변형을 통해 책상의
                        사용성을 높였습니다<br /></strong><br>
                        평소에는 온라인 수업이나 PC작업으로 사용하면서 레일을 통해 상판을 더 꺼내면 작업하기 편리하게 넓게 사용하실 수 있습니다.<br>
                        그리고 상판을 올리면 가벽이 생기면서 도구나 메모장을 부착할 수 있고 공부가 끝나면 치울 필요 없이 바로 상판을 닫고 사용할 수 있습니다.
                        <br><br> 이상으로 용도에 따라 레이어처럼 나눠쓰는 레이어드 데스크 입니다!<br><br>
                    작업 용도<br>
                        <img src="images/lay01.jpg"/><br><br>
                    PC 용도<br>
                    <img src="images/lay011.jpg"/><br><br>
                    오픈 과정<br>
                    <img src="images/lay02.jpg"/><br><br>
                    스터디 용도<br>
                    <img src="images/lay03.jpg"/><br><br>

                    </p>
                </div>
            </template>
            <template v-else-if="tapselect=='review'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경입니다.</h1>
                <p>
                    코로나 사태 이후 가택 근무나 온라인 수업 등으로 본인이 거주하고 있는 공간 안에서 업무를 보거나
                    작업을 하는 경우가 크게 증가하였다. <br><br>
                    거주 공간에서 그동안 하지 않던 작업들을 수행하는데 공간적으로 어려움을 느끼는 경우가 생겼고,<br><br> 
                    평소 학교나 작업실 등의 넓은 책상에서 작업하던 것을 한정된 공간 안에서 수행하기 위해 효율적인 책상을 만들고자했다.<br><br>
                    사용자의 환경을 분석하는데 있어 장소성을 중점으로 연구하였다. <br><br>
                    개인 공간에서 다양한 작업을 수행해야 하는 상황에 기존의 일반적인 책상의 불편함이
                    대두되는 문제점을 해결하기 위해서 <br><br>
                    디자인은 사용자와 책상, 그리고 장소의 연관성을 면밀히 살펴볼 필요가 있었다. <br><br>
                    학생들이 온라인 강의를 수강하거나 컴퓨터 작업을 할 때는 그 공간은 컴퓨터 작업실의 의미를 가지게 된다. <br><br>
                    또한 스케치나 목업 등 구체적인 디자인 작업을 진행할 때는 보다 활동 반경이 넓은 작업실로서 기능하게 된다. <br><br>
                    이 외에도 책상(작업대)은 사용자가 어떤 행위를 하느냐에 따라 다른 공간으로 바뀔 수 있다. <br><br>                   
                    우리는 여기서 사용자가 본인의 임의대로 책상을 
                    변형시키고 새로운 환경을 만들어낼 수 있는, 더 나아가 인간과 관계하는 책상,<br><br> 
                    다양한 장소성을 지닐 수 있는 책상을 디자인하는 것을 목표로 하였다.<br />

                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='order'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다</h1>
                <p>

                    <strong>CMF</strong>
                    <br><br>
                    주조색은 책상 전체에 무거우면서 안정감이 느껴지는 BK를 사용하여 모던한 느낌을 주었습니다.<br>

                    상판1은 공부를 하는 용도로 N9.5를 사용하여 사물이 눈에 잘 들어오도록 하였습니다. 전체적인 형태에서 열리는 파트라는 점을 감안해 눈에 띄게 구분을 해주었습니다.<br>

                    상판2는 PB/dp색상을 사용하여 전체적으로 검정, 흰색 조합에 파트구분을 가능하게 함과 동시에 북유럽풍 분위기를 느낄 수 있도록 배색하였습니다.<br>

                    <br><br>
                    <strong>소재</strong>
                    <br><br>
                    올리는 상판 같은 경우에는 무게를 경량화하기 위해 MDF 소재를 활용하였습니다.<br>
                    전체적으로 받쳐주는 프레임이나 모니터 받침대 같은 경우에는 튼튼한 자작나무 합판으로 선정하였으며 18t정도의 두께로 선정하였습니다<br>
                    다리 파트는 안정성있게 받쳐주면서 세련된 느낌을 주고자 철제를 사용하였습니다<br>
                    마감은 페인트로 도장, 샌딩기로 가공을 3번 이상 반복 후 바니쉬와 샌딩기 가공을 3번 이상 진행하여 마감하였습니다.
                    <br><br>
                    <strong>도면</strong>
                    <br><br>
                    <img src="images/lay04.jpg"/><br><br>
                    <img src="images/lay05.jpg"/><br><br>
                    <strong>전기 선 관리</strong>
                    <br><br>
                    <img src="images/lay12.jpg"/><br><br>
                    <strong>경첩 및 공간</strong>
                    <br><br>
                    <img src="images/lay13.jpg"/><br><br>
                    <img src="images/lay14.jpg"/><br><br>
                    <strong>레일</strong>
                    <br><br>
                    <img src="images/lay15.jpg"/><br><br>
                    <strong>손잡이 홈</strong>
                    <br><br>
                    <img src="images/lay16.jpg"/><br><br>
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='write'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
                <p>
                    <strong>후기</strong><br><br>
                    프로젝트를 진행하면서 디자인 과정에서는 큰 문제가 발생하지는 않았지만 <br>
                    제작을 하는 과정에서 치수의 문제나 구조상의 문제들이 존재했습니다. <br>
                    대부분의 작업 과정을 수작업으로 진행했기 때문에 어쩔 수 없이 생기는 오차들도 있었지만, <br>
                    모델링 과정에서 생각하지 못한 근본적인 문제도 생겨났습니다.  <br>
                    제품을 제작하기 위해 구매했던 경첩이나 레일이 생각했던 치수와 다른 경우였습니다. <br>
                    시제품을 충분히 조사하고 우리 책상에 맞는 최적의 부품들로 구매를 하였지만 <br>
                    생각했던 치수와 , 경첩을 접었을 때 생기는 치수의 오차가 달라 계산에 착오가 생겨 많은 시행착오를 겪었습니다.<br><br>
                    <img src="images/lay17.jpg"/><br><br>
                    전시 때 이름이 잠깐 문제가 있어서 유틸리티 데스크로 표기되었지만 원래 이름은 레이어드 데스크입니다 ㅠㅜ <br>
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='recommendation'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>제작 과정 사진입니다.</h1>
                <p>
                    <strong>아이디어 스케치</strong><br>
                    <img src="images/skt01.jpg"/><br>
                </p>
                <p><strong>1차 목업</strong><br><br>
                    <img src="images/lay06.jpg"/><br>
                </p>
                <p><strong>2차 목업</strong><br><br>
                    <img src="images/lay07.jpg"/><br>
                </p>
                <p><strong>3차 목업</strong><br><br>
                    <img src="images/lay08.jpg"/><br>
                </p>
                <p><strong>제작 과정</strong><br><br>
                <strong>후가공</strong><br><br>
                    <img src="images/lay10.jpg"/><br>
                </p>
                <p><strong>조립</strong><br><br>
                    <img src="images/lay11.jpg"/><br>
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='reference'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
                <p>곧 작업될 예정입니다.</p>
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
                { label: "제작 기간", content: "2021-01-01 ~ 2021-06-20"},
                { label: "사이즈", content: "1400*650*842"},
                { label: "재료", content: "자작나무, MDF, STEEL, 레일, 경첩"},
                { label: "사용 프로그램", content: "Rhino6, Keyshot, PhotoShop"},
                { label: "사용툴", content: "라우터, 레일쏘"},
                { label: "설명", content: "다양한 기능이 있습니다"},
        ],
        tapselect: "introduce",
        };
    },
};
</script>
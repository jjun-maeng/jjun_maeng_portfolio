<template>
    <section class="bookdetail">
      <h1 class="booktitle">
        {{bookName}}
        <span>{{ bookDec }}</span>
      </h1>
      <div class="book-info">
        <div class="imgview">
          <div class="imgbook"><img :src="bookUrl" alt=""></div>
          <div class="bookbtns">
            <b-button variant="lightgray"><i class="bi bi-search" />자세히 보기</b-button>
            <b-button variant="lightgray"><i class="bi bi-hdd" />판넬</b-button>
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
        <template v-if="tapselect=='introduce'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>를 소개 합니다.</h1>
            <p>
              <strong>공간을 내 맘대로!<br>
                파티션을 자유롭게 조정할 수 있습니다!<br><br>
             </strong>
             책이 기울지 않을 뿐만 아니라,
            여분의 공간을 다른 용도로 사용할 수 있습니다.
            </p><br><br>
            <p>
              <img src="images/bcase02.jpg"/>
              <img src="images/bcase03.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경 입니다.</h1>
            <p>
              책이 얼마 없을 때 책꽂이에 책을 넣으면 금새 기울어져 쓰러집니다<br>
              그래서 중간에 칸막이를 만들어 조절을 하면서 남는 공간을 또 활용하면 어떨까 라는 생각에 시작하였습니다.
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다.</h1>
            <p>
              <img src="images/bcase06.jpg"/> <br><br>
              <strong> 도브테일 구조 </strong><br><br>
              <img src="images/bcase07.jpg"/><br><br>
              <strong> 홈 </strong><br><br>
              <img src="images/bcase08.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong> 후기 입니다.</h1>
            <p>
              <strong>아쉬운 점</strong><br>
              아무래도 급하게 만들다보니 오차를 최대한 내지 않으려고 했지만, 생각보다 두께가 얇았던 점<br>
              거기에서 나오는 미세한 오차가 빈틈을 발생시켰습니다. 또한, 두께가 얇아 타카를 사용할 수 없어,
              안정감이 조금 떨어지는 편이 있습니다. <br>
              다시 제작하게 된다면, 외형의 두께를 12t 정도로 더 키워서 견고하게 만들어보고자 합니다.
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
            <p>
              <strong>도면 & 모델링 </strong><br><br>
              <img src="images/bcase04.jpg"/><br><br>
              <img src="images/bcase05.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>비핸스에 들어가시면 더 많은 내용을 확인 할 수 있습니다.</p>
          </div>
        </template>
      </div>
    </section>
  </template>
  <script>
  export default {
    props: ['bookName', 'bookDec', 'bookUrl'],
    data(){
      return{
        bookinfolists:[
                { label: "디자이너", content: "김준명"},
                { label: "제작 기간", content: "2020-02-13 ~ 2020-02-17"},
                { label: "사이즈", content: "600*400*400"},
                { label: "재료", content: "자작나무 6t"},
                { label: "사용 프로그램", content: "AutoCad, Rhino6"},
                { label: "사용툴", content: "라우터, 레일쏘"},
                { label: "설명", content: "칸막이를 조절해 공간을 사용하세요"},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
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
              <strong>도리를 찾아서의 '도리'와 금융기업 '토스'의 로고를 섞어 만들어봤습니다!<br>
              귀여운 도리토스를 감상해보세요!<br><br>
             </strong>
             <img src="images/dory01.jpg"/><br><br>     
              
  
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경 입니다.</h1>
            도리토스는 그저 ... 과자를 먹다가 문득 생각나서 만들어보게 된 작업물입니다.ㅎㅎ<br>
            별 다른 목표없이 도리랑 토스를 합쳐서 일러스트나 만들어볼까라는 생각에서 시작된 작업물이라고 할 수 있습니다!<br>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다.</h1>
            <p>
              <img src="images/dory06.jpg"/><br><br>
              <img src="images/dory07.jpg"/><br><br>
              <img src="images/dory08.jpg"/><br><br>
              <img src="images/dory09.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
            <p>
              도리토스는 가볍게 만든 일러스트였는데, 생각보다 마음에 들어서 배경화면으로도 사용하고<br>
              그립톡에 이어서 은근 여러 굿즈를 만들 기회만 생기면 이 녀석을 실험체로 많이 사용했던 것 같습니다 ㅎㅎ<br>
              가끔 누군가 그립톡이나 배경화면을 보고 물어보면 은근 자랑하는 녀석입니다~!<br><br>
              <img src="images/dory05.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
            <p>
              <img src="images/dory02.jpg"/><br><br>
              <img src="images/dory03.jpg"/><br><br>     
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>비핸스에서 더 많은 내용을 확인 할 수 있습니다.</p>
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
                { label: "제작 기간", content: "2019-08-20"},
                { label: "사이즈", content: ""},
                { label: "재료", content: ""},
                { label: "사용 프로그램", content: "Illustrator"},
                { label: "사용툴", content: ""},
                { label: "설명", content: "도리와 토스가 합쳐진 도리토스입니다."},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
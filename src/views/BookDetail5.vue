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
              <strong>남성을 주 고객으로 생각하여 기존의 LED마스크에 견고한 이미지의 캐딜락 느낌을 콜라보하였습니다.</strong><br>
            </p>

              <p>
              <img src="images/clone01.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경 입니다.</h1>
            <p>
            
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다.</h1>
              <p>
            <strong>패키지</strong><br><br>
              <img src="images/clone03.png"/><br>
            </p>
            <p>
              <strong>익스플로드 뷰</strong><br><br>
              <img src="images/clone07.jpg"/><br><br>
              <strong>충전기</strong><br><br>
              <img src="images/clone08.png"/><br><br>
              <strong>케이스</strong><br><br>
              <img src="images/clone18.jpg"/><br><br>
              <img src="images/clone19.jpg"/><br><br>
              <img src="images/clone04.png"/><br><br>
              <img src="images/clone05.jpg"/><br><br>
              </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
            <p>
              <img src="images/clone15.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1> 
            <p>
              <strong>레퍼런스</strong><br><br>
              <img src="images/clone09.jpg"/><br><br>
              <img src="images/clone14.jpg"/><br><br>
              <strong>2D 렌더</strong><br><br>
              <img src="images/clone16.jpg"/><br><br>
              <img src="images/clone17.png"/><br><br>
              <strong>목업</strong><br><br>
              <img src="images/clone11.jpg"/><br><br>
              <strong>도면 & 모델링</strong><br><br>
              <img src="images/clone10.jpg"/><br><br>
              <img src="images/clone12.jpg"/><br><br>
              <strong>렌더링</strong><br><br>
              <img src="images/clone13.jpg"/><br><br>
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
        { label: "디자이너", content: "김준명, 박상우"},
                { label: "제작 기간", content: "2020-10-11 ~ 2020-12-16"},
                { label: "사이즈", content: "187*230.5*90.5"},
                { label: "재료", content: "플라스틱, LED 및 회로"},
                { label: "사용 프로그램", content: "Rhino6, keyshot, Photoshop, Makerbot"},
                { label: "사용툴", content: "3D프린터"},
                { label: "설명", content: "견고하고 무게감 있는 느낌의 LED마스크입니다."},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
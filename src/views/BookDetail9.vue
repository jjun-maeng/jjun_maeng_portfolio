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
              <strong>귤을 타고 다니면서 제주도를 돌아다니는 귤껍질 캐릭터 깐귤이!<br>
              동료를 모아 주인을 찾아 떠납니다!<br><br>
             </strong>
             <img src="images/tang05.jpg"/><br><br>
             <img src="images/tang09.png"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경입니다.</h1>
            <p>
              <strong>2018 아트토이 공모전에 귤껍질 캐릭터 도전</strong><br><br>

              깐귤이는 2018 아트토이 공모전에 제주도라는 주제로 탄생한 캐릭터입니다.<br>

              제주도하면 귤캐릭터는 너무 진부한 것 같고 고민한 끝에 나온 것이 <br>
              
              귤에서 떨어져 나간 귤껍질이 귤을 타고 여행한다는 컨셉이었습니다.<br><br>

              귤껍질 캐릭터 깐귤이 초안 스케치<br><br>
             <img src="images/tang07.jpg"/><br><br>
             용두암 캐릭터 두용이 초안 스케치<br><br>
             <img src="images/tang08.jpg"/><br><br>

              </p>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다.</h1>
            <p>
              <strong></strong><br><br>
              <strong>깐귤이의 리메이크 버전 깐귤티콘입니다.</strong><br><br>
              <img src="images/tang06.jpg"/><br><br>
             <img src="images/tang02.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
            <p>
             캐릭터 공모전으로는 첫 공모전이었던 것이라 신박한 캐릭터를 해야겠다는 목표로
              만든 캐릭터입니다. <br>
            나름 듣도보도 못한 귤껍질이라는 컨셉이었기에 기대가 컸었고<br>
             당연히 좋은 결과가 있겠지 라고 생각했지만? 어림도 없었답니다~<br>
             좋은 결과는 없었지만 나름 만족하는 캐릭터이고, 조금만 더 준비를 잘 했으면
             어땠을까 하는 아쉬움이 많은 캐릭터입니다.<br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
            <p>
              <img src="images/tang03.jpg"/><br><br>
              <img src="images/tang04.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>메인 홈에서 블로그나 인스타로 들어가시면 더 많은 내용을 확인 할 수 있습니다.</p>
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
                { label: "제작 기간", content: "2018-07-04 ~ 2018-07-17"},
                { label: "사이즈", content: ""},
                { label: "재료", content: ""},
                { label: "사용 프로그램", content: "Illustrator"},
                { label: "사용툴", content: ""},
                { label: "설명", content: "귤껍질 캐릭터 깐귤이입니다."},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
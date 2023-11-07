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
              <strong>우주발광이끼를 먹고 자란 슬라임을 납치해 가공한 우주고양이입니다.<br>
              무거우면서 차분한 검정색과 밝게 빛나는 야광 물질은 마음을 편안하게하고 긍정적인 효과를 줍니다.<br><br>
             </strong>
         
             <img src="images/space01.jpg"/><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경 입니다.</h1>
            <p>
              <strong>발광이끼냥 스토리입니다.<br></strong>
              <img src="images/space05.jpg"/><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong> 디테일 입니다.</h1>
            <p>
              <strong>캐릭터 시트입니다. </strong><br><br> 
         
             <img src="images/space03.jpg"/><br><br>
             <img src="images/space02.jpg"/><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong> 후기 입니다.</h1>
            <p>      
              발광이끼냥은 원래 피규어로 출시될 아이었지만, <br><br>
              제가 게을러서 프로젝트가 흐지부지 되어부렸습니다 ㅎㅎ<br><br>
              다음에 기회가 된다면 더 준비를 철저히 해서 피규어가 될 수 있도록 노력해보겠습니다!<br><br>
              <img src="images/space11.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong> 갤러리 입니다.</h1>
            <p>
              <strong>초기 컨셉 및 디자인과정입니다.<br></strong>
              <img src="images/space09.jpg"/><br><br>
              <img src="images/space10.jpg"/><br><br>
              <img src="images/space08.jpg"/><br><br>
              <img src="images/space06.jpg"/><br><br>
              <img src="images/space07.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>추후에 발전시켜 더 좋은 모습을 보여드리겠습니다.</p>
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
                { label: "제작 기간", content: "2023-06-01 ~ 2023-08-20"},
                { label: "사이즈", content: "-"},
                { label: "재료", content: "-"},
                { label: "사용 프로그램", content: "Clip Studio"},
                { label: "사용툴", content: "-"},
                { label: "설명", content: "우주발광이끼를 먹고 태어난 고양이입니다"},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
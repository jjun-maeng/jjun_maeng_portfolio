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
          <b-form-radio name="detail-tap" v-model="tapselect" value="introduce" button  button-variant="detailtap"><i class="bi bi-mic" /> 소개</b-form-radio>
          <b-form-radio name="detail-tap" v-model="tapselect" value="review" button  button-variant="detailtap"><i class="bi bi-chat-left-text" /> 디자인 배경</b-form-radio>
          <b-form-radio name="detail-tap" v-model="tapselect" value="order" button  button-variant="detailtap"><i class="bi bi-layout-text-sidebar-reverse" /> 디테일</b-form-radio>
          <b-form-radio name="detail-tap" v-model="tapselect" value="write" button  button-variant="detailtap"><i class="bi bi-journal-text" /> 후기</b-form-radio>
          <b-form-radio name="detail-tap" v-model="tapselect" value="recommendation" button button-variant="detailtap"><i class="bi bi-person-check" />사진</b-form-radio>
          <b-form-radio name="detail-tap" v-model="tapselect" value="reference" button button-variant="detailtap"><i class="bi bi-inboxes" />자료실</b-form-radio>
        </div>
        <template v-if="tapselect=='introduce'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>를 소개 합니다.</h1>
            <p>
              <strong>기분좋게 책상을 청소한다!<br>
              쾌적한 청소로 방 안의 분위기를 바꾼다.<br><br>
             </strong>
              
             <img src="images/sprout01.jpg"/>
  
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경입니다.</h1>
                <p>
                  가끔 먼지가 가득 쌓인 책상을 청소할 때면, 퀴퀴한게 썩 기분이 좋지 않습니다.<br>
                  그래서 생각을 해봤습니다. 청소를 기분좋게 해보는 제품을 주제로 해볼까?<br>
                  현재 시중에 나온 책상 청소기를 실제 모델링해보면서 내부의 부품들과 디테일한 부분들을 익히고<br>
                  추가적인 기능을 넣으면서 새로운 책상 청소기를 고안하게 되었습니다.<br>
                  청소할때 진동으로 볼을 흔들면서 내부의 디퓨져가 같이 나오는 책상 청소기!<br>
                  이것으로 더 쾌적한 기분으로 청소를 해보는 것은 어떨까요? <br><br>
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='order'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다</h1>
                <p>
                  <strong>익스플로드 뷰</strong><br><br>
            <img src="images/sprout03.jpg"/>
            </p>
                </div>
            </template>
            <template v-else-if="tapselect=='write'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
                <p>
                  저에겐 첫 3D 모델링 작품이었기에 기억에 오래남는 작품같습니다.<br>
                  제품치고 장난감처럼 귀여운 이미지도 줄 수 있어, 제품으로 이런 느낌도 주는구나를 느꼈죠.ㅎㅎ<br>
                  보기에는 간단하지만 나름 시바툴로 모형을 만들어 테스트도 거쳐가면서 계속 디벨롭했답니다?<br>
                  당시 성적은 좋게 못 받았지만 나름 만족하던 제품 중 하나입니다!<br>
                  그래도 이 프로젝트를 진행하면서 제품을 디자인할 때 기존 제품을 한번 모델링해보면서 자세히<br>
                  관찰하고 적용하는 것을 배운 경험이 있었습니다!<br><br>
                  <img src="images/sprout09.jpg"/>
                </p>
                </div>
            </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
            <p>
              <strong>레퍼런스 제품</strong><br><br>
              시중에 나와있는 자동차 데스크 청소기를 모델링해보면서
              구조와 원리를 파악하였습니다.<br><br>
            <img src="images/ref07.jpg"/><br>
            <strong>아이디어 스케치</strong><br><br>
            <img src="images/skt07.jpg"/><br>
            <img src="images/sprout04.jpg"/><br>
            <img src="images/sprout05.jpg"/><br>
            <img src="images/sprout06.jpg"/><br>
            <strong>목업</strong><br><br>
            <img src="images/sprout07.jpg"/><br><br>
            <strong>모델링</strong><br><br>
            <img src="images/sprout08.jpg"/><br><br>
            <strong>렌더링</strong><br><br>
            <img src="images/sprout10.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>비핸스나 블로그에서 자세한 디테일 사진을 확인하실 수 있습니다.</p>
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
                { label: "제작 기간", content: "2019-05-01 ~ 2019-06-12"},
                { label: "사이즈", content: "83*110*62"},
                { label: "재료", content: "플라스틱 및 부품"},
                { label: "사용 프로그램", content: "Rhino6, keyshot, Photoshop, Makerbot"},
                { label: "사용툴", content: "3D프린터"},
                { label: "설명", content: "방 안을 기분좋게 청소해보세요"},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
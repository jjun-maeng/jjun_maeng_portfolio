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
                    <strong>
                    우리는 일상에서 전자기기를 많이 사용합니다. <br>잠시 스마트폰으로부터 잠시 떨어짐과 동시에
                    스마트폰도 쉬면서<br> 배터리도 충전하고 살균도 함께 해보는 것은 어떨까요?
                    <br /><br />
                    </strong><br>
                    <img src="images/huerest01.jpg"/><br><br>
                    <img src="images/huerest17.jpg"/>        
                </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경입니다.</h1>
                <p>
                  일상생활에서 가장 많이 사용하는 제품은 무엇일까? 아마, 스마트폰일 것이다.<br>
                  그러나, 그 스마트폰에 얼마나 많은 세균이 있는 지 사람들은 잘 인식하지 못하는 것 같았다.<br>
                  코로나 19로 인해 살균이 우리의 일상에 얼마나 필요한지 절실하게 느끼고 있는 요즘, 우리는 생각했다.<br>
                  과연 사람들이 핸드폰 살균기를 구매하지 않고 있는지.<br>
                  생소한 소형 가전제품이기도 하고, 시중에는 갑작스럽게 나온 제품들과 과거에 나와 구형이 된 제품들이 공존하고 있었기에,<br>
                  이러한 제품이 존재했다는 것을 사람들에게 알려주는 것과 동시에, 핸드폰 살균기 디자인의 질서 성립에 앞장서고자 했다.<br>
                  코로나 사태 이후 살균에 대한 중요성과 스마트폰을 장시간 사용하는 사용자를 대상으로<br>
                  침대에서 스마트폰 사용을 잠시 쉬라는 의미에서 휴 레스트라는 제품을 기획하게 되었다.<br>
                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='order'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다</h1>
                <p>
                  <strong>인터페이스</strong><br><br>
                    <img src="images/huerest15.jpg"/><br><br>
                    <img src="images/huerest16.jpg"/><br><br>
                    <strong>설명서</strong><br>
                    <img src="images/huerest11.jpg"/>

                </p>
                </div>
            </template>
            <template v-else-if="tapselect=='write'">
                <div class="detailTapCon">
                <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
                <p>
                   
                </p>
                </div>
            </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
            <p>
              <strong>자료 조사</strong><br><br>
                    <img src="images/huerest02.jpg"/><br><br>
                    <img src="images/huerest04.jpg"/><br><br>
                    <strong>아이디어 스케치</strong><br><br>
                    <img src="images/huerest05.jpg"/><br><br>
                    <img src="images/huerest06.jpg"/><br><br>
                    <strong>비율 목업</strong><br><br>
                    <img src="images/huerest03.jpg"/><br><br>
                    <img src="images/huerest07.jpg"/><br><br>
                    <img src="images/huerest14.jpg"/><br><br>
                    <strong>1차 목업</strong><br><br>
                    <img src="images/huerest08.jpg"/><br><br>
                    <strong>2차 목업</strong><br><br>
                    <img src="images/huerest09.jpg"/><br><br>
                    <strong>3차 목업</strong><br><br>
                    <img src="images/huerest10.jpg"/><br><br>
                    <strong>모델링 & 렌더링</strong><br><br>
                    <img src="images/huerest12.png"/><br><br>
                    <img src="images/huerest13.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>비핸스에 들어가시면 더 많은 내용을 확인 할 수 있습니다.</p>
            <p>아래 QR코드를 스캔하시면 작동 영상을 보실 수 있습니다<br><br>
              <img src="images/QR02.jpg"/>
            </p>
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
        { label: "디자이너", content: "김준명, 윤석현"},
                { label: "제작 기간", content: "2020-04-01 ~ 2020-06-20"},
                { label: "사이즈", content: "1400*650*842"},
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
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
              <strong>네이처 파크에서 동물 친구들이 탈출했습니다!<br>
              자신을 착각하거나 자신의 이름에 맞춰 살아가는
              안타깝지만 귀여운 동물친구들 세 얼간이!<br>
              지금 바로 네이처파크에서 찾아보세요!!<br><br>
             </strong>
              
             땡야는 돼지꼬리원숭이입니다.<br>
             사람들이 자꾸 '왜 돼지꼬리가 아닌데 돼지꼬리원숭이냐'라고 하자<br>
             스트레스를 받아서 그냥 돼지꼬리가 달린 바지를 입고 살게 됩니다.<br><br>
             
             알렉산더는 왕관앵무입니다.<br>
             어릴때 왕관을 주워 쓴 적이 있는데 이것 때문에 <br>
             자신이 왕관앵무라고 불리는줄 알고 계속 왕관을 쓰고 다닙니다<br>
             볼을 부끄러워서 빨갛다는 소문이 자자 합니다.<br><br>

            감자는 설가타육지거북입니다.<br>
            등껍질이 올록볼록하고 다리엔 가시가 돋아 있어서<br>
            자신이 공룡인줄 알고 있습니다.<br>
            육지거북이라 그런지 수영은 잘 못 하는 편입니다.<br><br>             
            <img src="images/three01.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경 입니다.</h1>
            <p>
              세 얼간이는 2019년 7월에 열린 네이처파크 캐릭터 공모전에 공모했던 캐릭터들입니다.<br>
              네이처 파크의 동물들 중에 세 마리를 선정해 디자인하는 것이었는데, 다들 매력 있었지만<br>
              포유류 1마리, 파충류 1마리, 조류 1마리로 밸런스있게 해보고자<br>
              돼지꼬리 원숭이, 왕관앵무, 설가타육지거북을 선정하게 되었습니다.<br><br>

              캐릭터 컨셉은 당시 보던 나혼자 산다의 세 얼간이를 모티브로 하게 되었습니다.<br>
              처음에는 생각 없이 시작했지만, 뭔가 자신들의 정체성을 혼동하는 캐릭터들이 <br>
              마치 얼간이들과도 잘 어울려 중간부터는 세 얼간이의 느낌으로 방향을 잡게 되었습니다.<br>
              별로 느낌은 안날지도 모르지만 돼지꼬리 원숭이는 이시언님, 왕관앵무는 핸리님, <br>
              설가타 육지거북은 기안84님을 생각하면서 만들게 되었습니다.<br><br>

            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다.</h1>
            <p>
              <strong>기본형과 응용형 캐릭터 시트입니다.</strong><br><br>
              <img src="images/three02.jpg"/>
              <img src="images/three03.jpg"/>
              <img src="images/three04.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
            <p>
              
              결국 공모전에선 아무런 성과는 없었지만, 나름 재미있던 경험이었기에
              기록을 하고자 합니다. 감사합니다!<br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
            <p>
              <img src="images/three05.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>비핸스로 들어가시면 더 많은 내용을 확인 할 수 있습니다.</p>
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
                { label: "제작 기간", content: "2019-07-17 ~ 2019-07-23"},
                { label: "사이즈", content: "200*200"},
                { label: "재료", content: ""},
                { label: "사용 프로그램", content: "Illustrator"},
                { label: "사용툴", content: ""},
                { label: "설명", content: "네이처파크 동물 캐릭터입니다!"},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
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
              <strong>가볍고 편하게 쓰는 스툴!<br>
              가볍고 튼튼하기 때문에 막 다루셔도 좋습니다!<br><br>
             </strong>

              FRP 스툴은 가벼운 아이소핑크에 FRP를 두른 것으로 상당히 무게가 가볍습니다. <br><br>
              
              또한, 앉았을 때도 부러지거나 변형되지 않을 정도의 튼튼함을 보여줍니다. <br><br>

              직접 앉아보고, 앉혀보면서 사용성 테스트까지 마쳤습니다!  <br><br>
              
              형태는 한자(나무 목)을 형상화하여 만들었으며, 나무처럼 견고하고 안정감있는 형태를 목표로 디자인했습니다.<br><br>
    
              <img src="images/frp06.jpg"/>

            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경입니다.</h1>
            <p>
              <strong>가볍고 튼튼한게 최고지!</strong><br><br>

              스툴은 기본적으로 등받이와 팔걸이가 없는 의자입니다.<br><br>
              스툴은 주로 오래 앉아있기보다는 여러 장소에 편하게 옮겨 작업하는데 많이 사용되는 것을 보았습니다.<br><br>
              아무래도 들고 다닐 수 있기 편하게 가볍고, 앉았을 때 부서지지 않는 안정성을 갖춘 스툴을 만들고자 FRP STOOL을 고안하게 되었습니다.<br><br>
              FRP는 유리 및 카본 섬유로 강화된 플라스틱계 복합재료로, 비중은 2.0 정도로 철강 재료의 1/4 정도로 가벼워 <br><br>
              뛰어난 기계특성을 가지는 경량 구조용 재료입니다.<br><br>
              가벼운 재료인 아이소핑크로 모형을 만들고, FRP를 물에 적셔 감아 굳혀 튼튼한 강도와 가벼운 무게의 스툴을
              구현해낼 수 있었습니다.<br><br>
              <img src="images/frp07.jpg"/>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일입니다.</h1>
            <p>
              중앙에 구멍이 있어 압력이 분산되어 안정적인 구조를 가졌습니다!<br><br>
              또한, 이동을 위해 들고다니기 편합니다!<br><br>
              <img src="images/frp05.jpg"/><br><br>
              무게가 가벼워 그냥 던지셔도 부서지지 않습니다 !<br><br>
              뭔가 걸치기도 쉬운 모형이라 이렇게 나무에 슬쩍 올려놔도 잘 걸립니다!<br><br>
              <img src="images/frp01.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
            <p>
              <strong>아쉬운 점<br></strong><br>
              초기에 외형에 의미를 담는 방향으로 시작했기에 안정성은 조금 떨어지는 부분이 있습니다.<br><br>
              사용성 테스트로 일정 체중까지 버티는 것은 확인했으나, 그 이상은 형태가 조금 눌리는 것을 확인하였습니다.<br><br>
              더 안정성을 높이기 위해서는 다리의 각도나 지지하는 부분을 보완할 필요성이 있습니다.
              <br><br>
              
              <img src="images/frp02.jpg"/>   
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>제작과정입니다.</h1>
            <p>
              “스티로폼 뭉탱이에서 스툴이 되는 과정!”<br>
              <img src="images/frp03.jpg"/><br><br>
              <img src="images/frp04.jpg"/><br><br>
            </p>
            <img src="images/FRP.jpg"/>
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
                { label: "디자이너", content: "김준명, 정세한"},
                { label: "제작 기간", content: "2019-06-01 ~ 2019-06-20"},
                { label: "사이즈", content: "230*230*400"},
                { label: "재료", content: "FRP, 아이소핑크"},
                { label: "사용 프로그램", content: ""},
                { label: "사용툴", content: "열선 커팅기"},
                { label: "설명", content: "새끼 손가락으로 올릴만큼 가볍습니다"},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
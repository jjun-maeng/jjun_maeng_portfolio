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
            <b-button variant="lightgray">
                <i class="bi bi-search" />자세히 보기</b-button>
            <b-button variant="lightgray">
                <i class="bi bi-hdd" />판넬</b-button>
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
              <strong>간단하게 들어올려 변형한다!<br>
              작업 도중 쉬고 싶으시면 들어올려 보세요!<br><br>
             </strong>
              
             <img src="images/hue01.jpg"/><br>
            </p>
            <p>
             <img src="images/hue02.jpg"/><br>
            </p>
            <p>
             <img src="images/hue03.jpg"/><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='review'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디자인 배경 입니다.</h1>
            <p>
              <strong>제품으로 공간을 바꿔보자!<br />스터디룸을 쉴 수 있는 공간으로!</strong><br><br>
              대학시절 제품조형실습 과목에서 '스터디룸에서 사용하는 스툴'이라는 주제로 만든 과제 작품입니다.<br>

              등받이 없는 스툴로 장시간 작업이나 공부를 하다보면 허리에 무리가 오는 것을 문제로 보았고<br>
              스툴 디자인을 통해 스터디룸이라는 공간을 중간에 편하게 쉴 수 있는 공간으로도 만들어보자는 목표로<br>
              이 작품을 기획하게 되었습니다.
              <br>
              <br>
            </p>
            <p>
              <img src="images/hue04.jpg"/><br><br>
            간단한 스케치목업부터 1차, 2차, 3차 목업을 통해 지금 형태의 스툴까지 발전하게 되었고<br>
            기획하던 기능을 구현할 수 있었습니다. 제품의 자세한 설명은 소개 탭에서 봐주시면 감사하겠습니다.<br><br>
            </p>
            <p>
              <img src="images/hue05.jpg"/><br><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='order'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>디테일 입니다.</h1>
            <p>
              <strong> 조립 전 파츠들입니다. </strong><br><br>
              <img src="images/hue06.jpg"/><br>
            </p>
            <p>
              <img src="images/hue20.jpg"/><br>
            </p>
            <p>
              <img src="images/hue18.jpg"/><br>
            </p>
            <p>
              <img src="images/hue19.jpg"/><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='write'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>후기 입니다.</h1>
            <p>
              <strong>프로젝트를 마치며<br></strong><br>
              지금까지 만든 스툴들을 함께 배치해봤을 때 디자인을 일관성 있게 잘 진행했다고 느꼈다.<br>
              사실 휴 스툴을 만들기까지 사람들 반응이 대부분은 괜찮은 아이디어라고 했지만,<br>
              몇몇은 '그게 구현이 될까?' 혹은 '구조적으로 힘들지 않겠어?' 라는 말을 하여 흔들릴뻔한 적이 있었다.<br>
              그래도 내가 만드는 가구니까 실패를 하더라도 하고 싶은 것을 구현하는 것에 초점을 맞추었다.<br>
              중간 과정에서도 스케일 때문에 스툴보다는 책상같다는 말을 들었을 때도 살짝 마음의 상처가 조오오오금 있었다.<br>
              그래도 포기하지 않고 일관성 있게 발전시킨 점이 최종적으로 좋은 결과물이 되었고, <br>
              스툴 전시에서도 가장 많은 투표를 받아 증명을 해낸 것 같았다.<br>
              마지막으로 여기까지 오게 해준 과정과 시련에 감사하게 생각한다.<br>
              아쉬운 점이 있다면 무게를 줄이지 못한 것이었다. 무게와 안정성을 둘 다 가져가기에는 <br>
              무리가 있어 과감하게 무게를 포기해야만 했던 상황이 아쉬웠다.<br>
              만약 후에 상업적으로 생산을 하게 된다면 재료와 두께를 타협해서 무게와 안정성을 모두 가져가는 제품으로 만들고 싶다.<br>
              <img src="images/hue22.jpg"/><br>
                  
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='recommendation'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>갤러리 입니다.</h1>
            <p>
              <strong>썸네일 목업</strong><br><br>
              <img src="images/hue11.jpg"/><br>
            </p>
            <p>
              <strong>아이디어 스케치</strong><br><br>
              <img src="images/skt02.jpg"/><br>
            </p>
            <p>
              <strong>1차 목업</strong><br><br>
              <img src="images/hue12.jpg"/><br>
            </p>
            <p>
              <strong>1차 목업 디테일</strong><br><br>
              <img src="images/hue13.jpg"/><br>
            </p>
            <p>
              <strong>2차 목업</strong><br><br>
              <img src="images/hue14.jpg"/><br>
            </p>
            <p>
              <strong>2차 목업 디테일</strong><br><br>
              <img src="images/hue15.jpg"/><br>
            </p>
            <p>
              <strong>3차 목업</strong><br><br>
              <img src="images/hue16.jpg"/><br>
            </p>
            <p>
              <strong>도면 & 모델링</strong><br><br>
              <img src="images/hue17.jpg"/><br>
            </p>
            <p>
              <strong>라우터 & 드릴링</strong><br><br>
              <img src="images/hue07.jpg"/><br>
            </p>
            <p>
              <img src="images/hue08.jpg"/><br>
            </p>
            <p>
              <strong>후가공 & 오차 조절</strong><br><br>
              <img src="images/hue09.jpg"/><br>
            </p>
            <p>
              <strong>조립 & 스테인,바니쉬 도포</strong><br><br>
              <img src="images/hue10.jpg"/><br>
            </p>
            <p>
              <strong>전시</strong><br><br>
              <img src="images/hue21.jpg"/><br>
            </p>
          </div>
        </template>
        <template v-else-if="tapselect=='reference'">
          <div class="detailTapCon">
            <h1 class="tapcontit"><strong>"{{bookName}}"</strong>자료실 입니다.</h1>
            <p>비핸스에 들어가시면 더 많은 내용을 확인 할 수 있습니다.</p>
            
            <p>아래 QR코드를 스캔하시면 작동 영상을 보실 수 있습니다.<br><br>
              <img src="images/QR01.jpg"/>
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
                { label: "디자이너", content: "김준명"},
                { label: "제작 기간", content: "2019-10-01 ~ 11-20"},
                { label: "사이즈", content: "600*400*400/ 1400*400*150"},
                { label: "재료", content: "자작나무, 경첩"},
                { label: "사용 프로그램", content: "AutoCad ,Rhino6"},
                { label: "사용툴", content: "라우터, 레일쏘"},
                { label: "설명", content: "간단하게 들어올려 변형이 가능합니다"},
              ],
        tapselect:"introduce"
      }
    }
  }
  </script>
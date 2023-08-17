<template>
  <a :href="news.link" class="news__card">
    <div class="news__card" :class="{'news__card--border': !news.image}">
      <div class="news__card-img">
        <img :src="news.image" alt="">
      </div>
      <div class="news__card-content">
        <div class="news__card-desc">
          <div class="news__card-date">
            <div class="news__card-date-num">
              {{ newsDate.day }}
            </div>
            <div class="news__card-date-add">
              <span>{{ newsDate.month }}</span>
              <span> {{ newsDate.year }}</span>
            </div>
          </div>
          <div class="news__card-title">
            {{ news.name }}
          </div>
          <div class="news__card-text">
            {{ news.previewText }}
          </div>
        </div>
        <div class="news__card-type">
          {{ news.type.value }}
        </div>
      </div>
    </div>
  </a>
</template>

<script>
import moment from 'moment'
import {reactive, toRefs} from "vue";

export default {
  name: 'FileItem',
  props: {
    news: {
      type: [Object, null],
      required: true,
      default: null
    }
  },
  setup(props) {
    const { news } = toRefs(props)
    const newsDate = reactive({
      day: moment.unix(news.value.date).format("D"),
      month: moment.unix(news.value.date).format("MMMM"),
      year: moment.unix(news.value.date).format("YYYY")
    })
    return {
      newsDate
    }
  }
}
</script>

<style scoped lang="scss">
.news__card {
  height: 100%;
  text-align: left;
  display: flex;
  flex-direction: column;
  border-radius: 16px;
  overflow: hidden;
  transition: 0.2s;
  &:hover {
    box-shadow: 0px 5px 15px 0px rgba(#0F62FE, 0.2);
  }
  &--border {
    border: 1px solid #0F62FE;

    .news__card-content {
      border: none;
    }
  }
}

.news__card-content {
  padding: 32px;
  border: 1px solid #0F62FE;
  border-radius: 0 0 16px 16px;
  border-top: 0;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
  @media (max-width: 991px) {
    padding: 20px 15px;
  }
}

.news__card-title {
  color: #0C5BEF;
  font-size: 22px;
  font-weight: 400;
  line-height: 120%;
  margin-bottom: 16px;
  @media (max-width: 991px) {
    font-size: 18px;
    margin-bottom: 10px;
  }
}

.news__card-text {
  color: #222327;
  font-size: 20px;
  font-weight: 400;
  line-height: 130%;
  letter-spacing: -0.2px;
  @media (max-width: 991px) {
    font-size: 16px;
  }
}

.news__card-type {
  color: #00133A;
  font-size: 14px;
  font-weight: 400;
  line-height: 140%;
  border-radius: 360px;
  background: #F0F6FE;
  display: inline-flex;
  padding: 5px 16px;
  margin-top: 40px;
}

.news__card-date {
  display: flex;
  align-items: center;
  margin-bottom: 18px;
}
.news__card-date-num {
  color: #A1A7B5;
  font-size: 36px;
  font-weight: 400;
  line-height: 100%;
  margin-right: 4px;
}
.news__card-date-add {
  display: flex;
  flex-direction: column;
  color: #A1A7B5;
  font-size: 15px;
  font-weight: 700;
  line-height: 110%;
  letter-spacing: -0.15px;
}
</style>

<template>
  <div class="hot_search history"
  v-if="historyRes.length>0"
  >
                <div class="hot_search_header">
                    <div class="search_title">history</div>
                    <div class="search_icon clear">
                        <i class="iconfont icon-bin"
                        @click="clear"
                        ></i>
                    </div>
                </div>
                <ul class="hot_search_conent">
                    <li class="search_label"
                    v-for="(item, index) in historyRes"
                    :key="index"
                    @click="toRes(item)"
                    >
                        <span class="search_label_text">{{item}}</span>
                        </li>
                </ul>
 </div>
</template>

<script>
export default {
  name: 'HistorySearch',
  props: {
    historyRes: {
      type: Array
    }

  },
  data () {
    return {
      goSearch: ''
    }
  },
  methods: {
    clear () {
      this.$emit('clearHistory')
    },
    toRes (item) {
      this.goSearch = item
      this.$emit('toResult', this.goSearch)
    }
  }
}
</script>

<style  lang="scss" scoped>
.hot_search {
    padding: 16px 16px 24px;
    box-sizing: border-box;
    width: 100%;
    .hot_search_header {
    width: 343px;
    height: 44px;
}

.search_title {
    float: left;
    width: 299px;
    font-size: 18px;
    color: #666;
    letter-spacing: 0;
    line-height: 44px;
    font-weight: 700;
}

.search_label {
    overflow: hidden;
    display: inline-block;
    vertical-align: middle;
    background: #efefef;
    border-radius: 2px;
    margin-right: 16px;
    margin-bottom: 8px;
    padding: 0 17px;
    height: 36px;
    line-height: 36px;
    color: #666;
    font-size: 14px;
}

.search_icon {
    float: right;
    height: 44px;
    width: 44px;
    color: #999;
    line-height: 44px;
    font-size: 30px;
    text-align: center;
}
}

.history {
    padding: 0px 16px 24px;
    box-sizing: border-box;
    width: 100%;
}

</style>

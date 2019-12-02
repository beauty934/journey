<template>
  <div>
    <i-grid>
    <i-grid-item>
        <i-grid-icon>
            <image src="/static/images/user.png" />
        </i-grid-icon>
        <i-grid-label>美食</i-grid-label>
    </i-grid-item>
    <i-grid-item>
        <i-grid-icon>
            <image src="/static/images/user.png" />
        </i-grid-icon>
        <i-grid-label>景区</i-grid-label>
    </i-grid-item>
    <i-grid-item>
        <i-grid-icon>
            <image src="/static/images/user.png" />
        </i-grid-icon>
        <i-grid-label>游乐</i-grid-label>
    </i-grid-item>
    <i-grid-item>
        <i-grid-icon>
            <image src="/static/images/user.png" />
        </i-grid-icon>
        <i-grid-label>高校</i-grid-label>
    </i-grid-item>
</i-grid>
<i-panel title="热门">
    <view style="padding: 15px;">
      <i-card i-class="split" title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
         <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
       <i-card i-class="split" title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
         <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
       <i-card i-class="split" title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
         <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
    </view>
</i-panel>
  </div>
</template>

<script>

export default {
  data () {
    return {
     
      }
  },
  methods: {
    },

  created () {
  }
}
</script>

<style scoped>

</style>
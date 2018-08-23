<template>
    <div class="team">
        <navBar navTitle="我的团队" isChildPage="y"></navBar>
        
        <div class="searchBar weui-search-bar" id="searchBar">
            <form class="weui-search-bar__form">
                <div class="weui-search-bar__box">
                    <i class="weui-icon-search"></i>
                    <input type="search" class="weui-search-bar__input" id="searchInput" placeholder="搜索" required="">
                    <a href="javascript:" class="weui-icon-clear" id="searchClear"></a>
                </div>
                <label class="weui-search-bar__label" id="searchText">
                    <i class="weui-icon-search"></i>
                    <span>搜索</span>
                </label>
            </form>
            <a href="javascript:" class="weui-search-bar__cancel-btn" id="searchCancel">取消</a>
        </div>

        <div class="team-toolBar">
            <div class="team-toolBar-select">
                <img src="">
                <div class="team-toolBar-select-text">全部</div>
            </div>
            <div class="team-toolBar-totalTeamMenber">团队总人数: {{totalTeamMenber}}</div>
        </div>

        <div class="team-list">
            <div class="team-list-item" v-for="item in items" :key="item.number">
                <div class="team-list-item-content">
                    <img src="@/assets/ic_user.png" class="icon-user">
                    <div class="team-list-item-userinfo">
                        <div class="accountDetail-list-item-name">{{item.username}}</div>
                        <div class="accountDetail-list-item-recommendedBy">推荐人: {{item.recommendedBy}}</div>
                        <div class="accountDetail-list-item-recommendedTime">{{item.recommendedTime}}</div>
                    </div>
                    <div class="accountDetail-list-item-recommendedFrom">来源: {{item.recommendedFrom}}</div>
                    <img src="" class="icon-link">
                </div>
                <hr class="divider">
            </div>
        </div>
    

    </div>
</template>

<script>
import navBar from '@/components/navBar.vue'

export default {
  name: 'team',
  components: {
    navBar
  },

  data: function(){
      return{
          totalTeamMenber: '85',
          items: [
            {
                number: '1',
                username: '初夏',
                recommendedBy: '小黄',
                recommendedTime: '2018-07-02 01:11:01',
                recommendedFrom: '二维码'
            },
            {
                number: '2',
                username: '李颖',
                recommendedBy: 'lily bai',
                recommendedTime: '2018-07-02 01:11:01',
                recommendedFrom: '分享'
            },
            {
                number: '3',
                username: '薄荷',
                recommendedBy: '多多麻麻',
                recommendedTime: '2018-07-02 01:11:01',
                recommendedFrom: '二维码'
            }
        ]
      }
  },

  methods: {
  }

}
</script>

<style scoped>
.divider{
    color: #888888;
    margin: 1.25rem 0;
    line-height: 1px;
}

.team-toolBar{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin: .9375rem 0.9375rem;
}

.team-toolBar-select{
    display: flex;
    flex-direction: column;
}

.team-list{
    display: flex;
    flex-direction: column;
}

.team-list-item{
    display: flex;
    flex-direction: column;
    margin: 0 0.9375rem;
}

.team-list-item-content{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-end;
}

.team-list-item-userinfo{
    display: flex;
    flex-direction: column;
}

.accountDetail-list-item-recommendedBy{
    font-size: 15px;
    color: #888888;
}

.accountDetail-list-item-recommendedTime{
    font-size: 15px;
    color: #888888;
}

.accountDetail-list-item-recommendedFrom{
    font-size: 15px;
}

.icon-user{
    width: 6.25rem;
    height: 6.25rem;
    /* margin: 0 auto; */
}
</style>


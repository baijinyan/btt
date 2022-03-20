<template>
  <div id="home">
    <!-- 顶部 -->
    <div class="nav">
      <input type="text" placeholder="爱情" class="ipt" /><button class="btn">
        取消
      </button>
    </div>
    <!-- 菜单导航 -->
    <div class="meau">
      <div
        v-for="(item, index) in data"
        :key="index"
        :class="count === item.id ? 'meau-item active' : 'meau-item'"
        @click="change(item.id)"
      >
        {{ item.title }}
      </div>
    </div>
    <div class="row channel">
      <ul id="list">
        <li class="list" v-for="(item, index) in meauData" :key="index">
          {{ item.title }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  setup() {
    // 需要进行响应式的值
    const state = reactive({
      count: 1,
      meauData: [
        {
          title: "影片",
          id: 1,
        },
        {
          title: "创意",
          id: 2,
        },
        {
          title: "励志",
          id: 3,
        },
        {
          title: "搞笑",
          id: 4,
        },
        {
          title: "运动",
          id: 5,
        },
        {
          title: "旅行",
          id: 6,
        },
        {
          title: "爱情",
          id: 7,
        },
        {
          title: "广告",
          id: 8,
        },
        {
          title: "动画",
          id: 9,
        },
        {
          title: "剧情",
          id: 10,
        },
      ],
    });
    // 改变菜单标题高亮 和内容
    const change = (i) => {
      // 判断定义的值 是否与数据的顺序是否一致
      // 一致则终止return后续代码的执行
      if (state.count === i) {
        return;
      }

      state.count = i;
      state.meauData = arr[state.count - 1];
      // if(state.count==1){
      //   meauData=meauData1
      // }else if( state.count==2){
      //   meauData=meauData2
      // }
    };
    const data = [
      {
        title: "影片",
        id: 1,
      },
      {
        title: "默认排序",
        id: 2,
      },
      {
        title: "全部频道",
        id: 3,
      },
    ];

    const meauData1 = [
      {
        title: "影片",
        id: 1,
      },
      {
        title: "创意",
        id: 2,
      },
      {
        title: "励志",
        id: 3,
      },
      {
        title: "搞笑",
        id: 4,
      },
      {
        title: "运动",
        id: 5,
      },
      {
        title: "旅行",
        id: 6,
      },
      {
        title: "爱情",
        id: 7,
      },
      {
        title: "广告",
        id: 8,
      },
      {
        title: "动画",
        id: 9,
      },
      {
        title: "剧情",
        id: 10,
      },
    ];
    const meauData2 = [
      {
        title: "默认排序",
        id: 1,
      },
      {
        title: "创意",
        id: 2,
      },
      {
        title: "励志",
        id: 3,
      },
      {
        title: "搞笑",
        id: 4,
      },
      {
        title: "运动",
        id: 5,
      },
      {
        title: "旅行",
        id: 6,
      },
      {
        title: "爱情",
        id: 7,
      },
      {
        title: "广告",
        id: 8,
      },
      {
        title: "动画",
        id: 9,
      },
      {
        title: "剧情",
        id: 10,
      },
    ];
    const meauData3 = [
      {
        title: "全部频道",
        id: 1,
      },
      {
        title: "创意",
        id: 2,
      },
      {
        title: "励志",
        id: 3,
      },
      {
        title: "搞笑",
        id: 4,
      },
      {
        title: "运动",
        id: 5,
      },
      {
        title: "旅行",
        id: 6,
      },
      {
        title: "爱情",
        id: 7,
      },
      {
        title: "广告",
        id: 8,
      },
      {
        title: "动画",
        id: 9,
      },
      {
        title: "剧情",
        id: 10,
      },
      {
        title: "音乐",
        id: 11,
      },
      {
        title: "科幻",
        id: 12,
      },
      {
        title: "纪录",
        id: 13,
      },
      {
        title: "预告",
        id: 14,
      },
      {
        title: "混剪",
        id: 15,
      },
      {
        title: "实验",
        id: 16,
      },
      {
        title: "生活",
        id: 17,
      },
      {
        title: "时尚",
        id: 18,
      },
      {
        title: "汽车",
        id: 19,
      },
      {
        title: "游戏",
        id: 20,
      },
      {
        title: "美食",
        id: 21,
      },
    ];
    const arr = [meauData1, meauData2, meauData3];

    return {
      // 将需要响应式的值进行导出
      ...toRefs(state),
      // 挂载自定义的方法
      change,
      // 没有响应式的值
      data,
    };
  },
  // data() {
  //   return {
  //     count: 0,
  //   };
  // },
  // methods: {
  //   add() {
  //     console.log(this);
  //     this.count++;
  //   },
  // },
};
</script>

<style lang="scss" scoped>
#home {
  padding: 10px;
  background-color: #141414;

  .nav {
    display: flex;
    align-items: center;
    .ipt {
      flex: 8;
      height: 30px;
      padding-left: 20px;
      border: none;
      outline: none;
      color: #fff;
      background-color: #6e6d6d;
    }
    ::-webkit-input-placeholder {
      color: #fff;
    }
  }
  .btn {
    flex: 2;
    height: 30px;
    color: #6e6d6d;
    border: none;
    background: #141414;
  }
}
.meau {
  display: flex;
  justify-content: space-around; //将子元素在水平轴按照一定的间距排版

  padding: 10px 0;
  .meau-item {
    color: #999;
    font-size: 14px;
  }
}
.row {
  #list {
    display: flex;
    flex-wrap: wrap;
    .list {
      color: #fff;
      font-size: 13px;
      padding: 3px;
      border-radius: 5px;
      margin: 0 5px;
      margin-bottom: 10px;
      background: #282828;
      list-style: none;
      height: 20px;
      line-height: 20px;
    }
  }
}
.active {
  color: #fff !important;
}
</style>>

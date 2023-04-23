<template>
<div id="app" class="vertical-tab">
    <!-- 左侧tab栏 -->
    <ul class="nav nav-tabs1">
      <li v-for="i in link_list_left" :key="i"><a href="#" :class="activated(i)" @click="display = i"> Section {{i}} </a></li>
	</ul>
	<!-- 内容区域 -->
    <div class="tab-content tabs">
        <div class="tab-pane  fade" >
            <h3 >{{ list[display-1].title }}</h3>
            <p>{{ list[display-1].content }}</p>
        </div>
    </div>
    <ul class="nav nav-tabs2">
        <!-- 右侧tab栏 -->
        <li v-for="i in link_list_right" :key="i"><a href="#" :class="activated(i)" @click="display = i"> Section {{i}} </a></li>
    </ul>
</div>          

</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      display: 1,
      link_list_left: [1,2,3],
      link_list_right: [4,5,6],
      
      list: [{
               id: 1,
               title: 'Section 1',
               content: 'content1'
             }, {
                id: 2,
                title: 'Section 2',
                content: 'content2'
             }, {
                 id: 3,
                 title: 'Section 3',
                 content: 'content3'
             }, {
                 id: 4,
                 title: 'Section 4',
                 content: 'content4'
             }, {
                 id: 5,
                 title: 'Section 5',
                 content: 'content5'
             }, {
                 id: 6,
                 title: 'Section 6',
                 content: 'content6'
             }]   

    }
  },
  methods: {
    click_link(i){
        this.display = i;
    },
    activated(i) {
      let active = 0;
      let inactive = 1;
      if(i == this.display) {
        active = 1;
        inactive = 0;
      }
      return {
        active,
        inactive
      }
    }
  }
}
</script>

<style>
        * {
            margin: 0;
            padding: 0;
        }

        .active {
          color: blue;
        }

        .inactive {
          color: green;
        }

        .vertical-tab {
            width: 920px;
            margin: 100px auto;
        }
        
        .vertical-tab .nav {
            list-style: none;
            width: 200px;
        }
        
        .vertical-tab .nav-tabs1 {
            border-right: 3px solid #e7e7e7;
        }
        
        .vertical-tab .nav-tabs2 {
            border-left: 3px solid #e7e7e7;
        }
        
        .vertical-tab .nav a {
            display: block;
            font-size: 18px;
            font-weight: 700;
            text-align: center;
            letter-spacing: 1px;
            text-transform: uppercase;
            padding: 10px 20px;
            margin: 0 0 1px 0;
            text-decoration: none;
        }
        
        .vertical-tab .tab-content {
            color: #555;
            background-color: #fff;
            font-size: 15px;
            letter-spacing: 1px;
            line-height: 23px;
            padding: 10px 15px 10px 25px;
            display: table-cell;
            position: relative;
        }
        
        .vertical-tab .nav-tabs1 {
            float: left;
        }
        
        .vertical-tab .tabs {
            width: 500px;
            box-sizing: border-box;
            float: left;
        }
        
        .vertical-tab .tab-content h3 {
            font-weight: 600;
            text-transform: uppercase;
            margin: 0 0 5px 0;
        }
        
        .vertical-tab .nav-tabs2 {
            float: right;
        }
        
        /* .tab-content .tab-pane {
            display: none;
        } */
        
        .tab-content .tab-pane.active {
            display: block;
        }
</style>

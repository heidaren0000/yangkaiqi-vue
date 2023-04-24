<template>
<div id="app" class="vertical-tab">
        <h3>名称:</h3>
        <input v-model="search_term" type="text" id="name" name="name" required minlength="4" maxlength="8" size="10">
        <button type="button" @click="search" >查询</button>
    <infoTable :headers="titles" :info="data_to_show" @delete="delete_handler" ></infoTable>
</div>          

</template>

<script>

import infoTable from './components/infoTable.vue'
export default {
  name: 'App',
  data() {
    return { 
        titles:["ID","主标题","起步价格","显示","操作"],
        search_term: "",
        info:[{
            "id": 287,
            "title": "严选新式样板间",
            "price_info": 29.9,
            "is_show": 1
        }, {
            "id": 286,
            "title": "无“油”无虑的甜蜜酥脆",	
            "price_info": 45,
            "is_show": 1
        }, {
            "id": 283,
            "title": "孩子成长中少不了的一双鞋",
            "price_info": 78,
            "is_show": 1
        }, {
            "id": 282,
            "title": "成就一室笋香1",
            "price_info": 121,
            "is_show": 1
        }, {
            "id": 281,
            "title": "条纹新风尚",
            "price_info": 29,
            "is_show": 1
        }, {
            "id": 277,
            "title": "治愈生活的满怀柔软",
            "price_info": 66.78,
            "is_show": 1
        }, {
            "id": 274,
            "title": "没有软木拖，怎么过夏天",
            "price_info": 50.99,
            "is_show": 1
        }, {
            "id": 272,
            "title": "料理也要精细简单",
            "price_info": 69,
            "is_show": 1
        }, {
            "id": 271,
            "title": "选式新懒人",
            "price_info": 15.3,
            "is_show": 1
        }, {
            "id": 268,
            "title": "米饭好吃的秘诀：会呼吸的锅",
            "price_info": 20.1,
            "is_show": 1
        }]}
    },
    components:{
        infoTable
    },
    methods: {
        delete_handler(record) {
            let index = this.info.indexOf(record);
            if(index > -1) {
                this.info.splice(index,1);
            }
        },
        search(){
            if(this.search_term == "") {
                this.info.forEach((e) => {
                    e.is_show = 1;
                })
            } else {
                this.info.forEach((e) => {
                    if(e.title != this.search_term)
                        e.is_show = 0;
                });
            }
        }
    },
    computed: {
        data_to_show() {
            let array2show = [];
            this.info.forEach((e) => {
                if(e.is_show) 
                    array2show.push(e);
            });
            return array2show;
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

<template>
<div class="aqccrdion">
    <div v-for="(item,index) in divmodel" :key="index">
        <span class="hi"  @click="aindex(index)">
            <h2>{{item.title}}</h2>
            <i class="el-icon-caret-bottom" :class="{'el-icon-caret-right':index === ind}"></i>
        </span>
        <div class="aqccr_li ative" :class="{'ativeback':index === ind}" v-html="item.content">
        
        </div> 
    </div> 
</div>
</template>
<script>
import Es6 from '@/components/es6'
export default{
    data(){
        return {
            ind:0,
            divmodel:[
                {
                    title:'标题一',
                    content:Es6
                },
                {
                    title:'标题二',
                    content:'<div>这是一个模板</div>'
                },
                {
                    title:'标题三',
                    content:'<div>这是一个模板</div>'
                },
                ]
        }
    },
    created(){
        console.log(Es6)
    },
    methods:{
        aindex(name){
            if(name == this.ind){
                this.ind = 0
            }else{
                this.ind = name
            }
        }
    },
    components:{
        es6:Es6
    }
}    
</script>
<style lang="">
    .aqccrdion{
        margin:10px auto;
        background:#f0f;
    }
    
    .aqccr_li{
        height:90px;
        background:#ccc;
    }
    .aqccrdion .hi{
       cursor: pointer;
    }
    .aqccrdion .hi h2{
        text-align: left;
        padding:5px 20px;
    }
    .aqccrdion .hi i{
       float: right;
       margin-top:-30px;
       margin-right:20px;
    }
    .ative{
        display: none;
    }
    .ativeback{
        display: block;
    }
</style>
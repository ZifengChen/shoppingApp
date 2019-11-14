<template>
    <div name="show">
        <ul class="goodList">
            <li v-bind:key="good.goodName" v-for="good in list">
                <img v-bind:src="good.img">
                <p>{{good.goodName}}</p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "show",
    data(){
        var obj = this;
        var url = "";
        if(obj.goodId==1){
            url = "json/sb.json";
        }
        else if(obj.goodId==2){
            url = "json/shouji.json";
        }
        else{
            url = "json/sb.json";
        }
        this.$http.get(url).then(function(res){
            obj.list=res.data;
        })
        return{
            list:[]
        }
    },
    props:{
        goodId: Number
    },
    watch:{
        goodId(){
            var obj = this;
            var url = "";
            if(obj.goodId==1){
                url = "json/sb.json";
            }
            else if(obj.goodId==2){
                url = "json/shouji.json";
            }
            this.$http.get(url).then(function(res){
            obj.list=res.data;
        })
        return{
            list:[]
        }
        }
    }
}
</script>

<style>
    .goodList li{
        width: 200px;
        height: 200px;
        list-style: none;
        float: left;
        font-size: 13px;
        color:red;
        margin-bottom: 30px;
    }
    .goodList img{
        width: 180px;
        height: 180px;
    }
</style>
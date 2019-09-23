<template>
    <div name="show">
        <ul class="goodlist">
            <li v-for="goods in list">
                <img v-bind:src = "goods.img">
                <p>{{goods.goodsName}}</p>
            </li>
        </ul>

    </div>
</template>
<script>
export default {
    name:"show",
    data(){
        var obj = this;
        var url = "";
         if(obj.goodId == 1){
                url = "../static/json/bjb.json";
            }else if(obj.goodId == 2){
               url =  "../static/json/sj.json";
            }else{
                url = "../static/json/bjb.json";
            }
        this.$http.get("../static/json/bjb.json").then(function(res){
            console.log(res)
            obj.list =res.data;
        })
        return {
            list:[]
        }
    },
    props:{
        goodId:Number
    },
    watch:{
        goodId(){
            var obj = this;
            var url = "";
            if(obj.goodId == 1){
                url = "../static/json/bjb.json";
            }else if(obj.goodId == 2){
               url =  "../static/json/sj.json";
            }else{
                url = "../static/json/bjb.json";
            }
            this.$http.get(url).then(function(res){
                obj.list =res.data;
            })
            return {
                list:[]
            }
        }
    }
}
</script>
<style>
    .goodlist li{
        float: left;
        list-style: none
    }
    .goodlist p{
        font-size: 12px;
        margin-top: 0;
        background-color: white;
        color:red;
    }
    .goodlist img{
        width: 200px;
        height: 200px;
        margin-bottom: 0;
    }
</style>

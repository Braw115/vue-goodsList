<template>
    <div>
        <div v-if="kk==1">
            <GoodsList :goodId="1"></GoodsList>
        </div>
        <div v-else-if="kk==2">
            <GoodsList :goodId="2"></GoodsList>
        </div>
        <div v-else-if="kk==3">333333333</div>
        <div v-else-if="kk==4">444444444</div>
        <div v-else>
            <GoodsList></GoodsList>
        </div>
    </div>


</template>
<script>
import Msg from './msg.js'
import GoodsList from './GoodsList'
export default {
   
    data(){
        return {
            kk:0
        }
    },
    mounted:function(){
        var _this=this
        Msg.$on('val',function(res){
            _this.kk = res
        })
    },
     components :{
       GoodsList 
    }

}
</script>

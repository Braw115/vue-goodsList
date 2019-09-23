<template>
    <div class='main'>
        <div class='left'>
            <Left></Left>
        </div>
        <div class='right'>
            <div class='top'>
                <img src="../assets/logo.jpg" alt="">
            </div>
            <div class='buttom'>
                <Right></Right>
            </div>
        </div>

    </div>
</template>

<style>
    *{
        margin: 0;
        padding: 0;
    }
    .main{
        width: 1200px;
    }
    .left{
        width: 100px;
        margin-right: 10px;
        float: left;
       
    }
    .right{
        width: 1000px;
        margin-left: 10px;
        float: left;
        
    }
    .right img{
        width: 1000px;
        height: 200px;
    }
    .left,.right{
        background-color: #f5f5f5;
    }
</style>

<script>
    import Left from '../components/Left'
    import Right from '../components/Right'
    name:"First"
    module:history
    export default {
        components:{
            Left,
            Right
        }
    }
</script>


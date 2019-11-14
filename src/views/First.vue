<template>
    <div class="main">
        <div class="left">
            <Left/>
        </div>
        <div class="right">
            <div class="top">
                <img src="../../public/img/title.jpeg" alt="title">
            </div>
            <div class="bottom">
                <Right/>
            </div>
        </div>
    </div>
</template>

<script>
import Left from '../components/left';
import Right from '../components/Right';
export default {
    components: {
        Left,
        Right
    }
}
</script>

<style>
    *{
        padding: 0;
        margin: 0;
    }
    .left{
        width: 100px;
        float: left;
        margin-right: 10px;
    }
    .right{
        width: 1000px;
        float: left;
        margin-right: 10px;
    }
    .main{
        width: 1200px;
        margin: 20px auto;
    }
    .top img{
        width:1000px;
        height: 200px;
    }
    .left,.right{
        background-color: #f5f5f5;
        height: 500px;
    }
</style>
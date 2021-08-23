<template>
    <div>
        <br>
        <div class="active" style="box-shadow: 0 0 4px 0 rgba(0,0,0,0.2);">
            <span style="border:10%;font-size:20px;margin:1.5%">
                {{message}}
            </span>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            activeClass: 'active',
        }
    },
    props:['message']
}
</script>
<style>
.active{
    border-radius: 5px;
    line-height: 40px;
}
</style>
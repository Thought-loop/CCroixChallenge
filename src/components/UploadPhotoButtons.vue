<template>
    <div class = "action-button-area">
        <div class = "action-button">
            <p class="button-icon">📷</p>
            <p class="button-text">Take Photo</p>
        </div>
        <div class = "action-button">
            <p class="button-icon">📁</p>
            <p class="button-text">Upload</p>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style>
    .action-button-area{
        
        display: flex;
        justify-content: space-around;
        
    }

    .action-button{
        display: flex;
        flex-direction: column;
        width: 13rem;
        height: fit-content;
        background-color: rgba(105, 105, 105, 0.75);
        border-style: solid;
        border-color:rgb(80, 84, 97);
    }
    .action-button:hover{
        border-color:rgb(60, 63, 73);
        background-color: rgba(105, 105, 105, 0.658);
    }

    .button-icon{
       font-size:500%;
       margin: 0px;
    }

    .button-text{
       font-size:200%;
       margin: 0px;
    }
    
</style>
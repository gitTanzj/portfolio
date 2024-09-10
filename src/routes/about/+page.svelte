<script lang="ts"> 
    let textContainer
    
</script>

<div class="about-container">
    <div class="header">
        <h1>About me</h1>
    </div>
    <div class="about-text" id="aboutText" bind:this={textContainer}>
        <p>
            I am a software developer currently studying software development in Tartu Vocational College.
        </p>
    </div>
        <div class="scroll-down">
            <span class="material-symbols-outlined">
                chevron_left
            </span>
        </div>
</div>

<style>
    .about-container{
        display:flex;
        align-items: center;
        flex-direction: column;
        width: 100%;
        height: 100%;
    }
    .about-text{
        align-self: center;
        text-align: justify;
        width: 50%;
        
    }
    .about-text p{
        
    }
    .header{
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding:10px;
        width: 50%;
        height: 50%;
        transition: 0.4s;
        text-wrap: nowrap;
    }
    .header h1{
        align-self: flex-start;
        text-align: center;
        font-size: 3em;
        margin: 0;
        transition: 0.5s;
    }
    .scroll-down{
        bottom: 0;
    }
    .scroll-down span{
        rotate: 270deg;
    }
    @media (max-width: 768px){
        .header{
            width: 100%;
            height: 10%;
        }
        .header h1{
            font-size: 2em;
        }
    }
</style>
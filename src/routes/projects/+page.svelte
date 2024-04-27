<script lang="ts">
    
</script>

<div class="header">
    <h1>My Projects</h1>
    
</div>


<style>
    .header{
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding:10px;
        transition: 0.4s;
        width: 40%;
        height: 40%;
        text-wrap: nowrap;
    }

    .header h1{
        text-align: center;
        margin: 0;
        transition: 0.5s;
    }

    @media(max-width: 768px){
        .header{
            width: 100%;
            height: 10%;
        }
        .header h1{
            font-size: 3rem;
        }
    }
</style>
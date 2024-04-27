<div class="header">
    <h1>About page</h1>
    <p>This is the about page</p>
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

    .header p{
        text-align: center;
        margin: 10;
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
        .header p{
            font-size: 1.5rem;
        }
    }
</style>
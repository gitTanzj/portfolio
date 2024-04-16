<script lang="ts">
    import { onMount } from 'svelte';
    onMount(() => {
        const header = document.querySelector('.header') as HTMLElement;
        const hidden = document.querySelector('.hidden') as HTMLElement;
        header?.addEventListener('mouseover', () => {
            hidden.style.display = 'flex';
        });
        header?.addEventListener('mouseout', () => {
            hidden.style.display = 'none';
        });
    });
</script>

<div class="container">
    <div class="header">
        <h1>Kalle Riit</h1>
        <div class="hidden">
            <ul class="routes">
                <li>
                    <a href="/">Home</a>
                </li>
                <li>
                    <a href="/about">About</a>
                </li>
                <li>
                    <a href="/projects">Projects</a>
                </li>
            </ul>
        </div>
    </div>


</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap');
    
    

    .container {
        font-family: 'Playfair Display', serif;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        font-size: 2rem;
    }
    .header{
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding:10px;
        transition: 0.4s;
        width: 20%;
        height: 40%;
    }
    .header:hover{
        transform: translateY(-50px);
    }
    .header h1{ 
        text-align: center;
        margin: 0;
    }
    .routes{
        width: 100%;
        list-style-type: none;
        display: flex;
        justify-content: space-between;
        padding: 0;
        margin: 0;   
        gap: 10%;   
    }
    .routes a{
        text-decoration: none;
        font-size: 1.5rem;
        color: black;
    }
    .routes a:hover{
        animation: underline 0.4s;
    }
    .hidden{
        display:none;
        animation: fadeIn 0.4s;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }

    @keyframes underline {
        from {
            text-decoration: 2px underline white;
        }
        to {
            text-decoration: 2px underline black;
        }
    }
</style>


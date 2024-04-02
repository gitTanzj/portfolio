<script lang="ts">
    import { onMount } from 'svelte';
    onMount(() => {
        const header = document.querySelector('.header');
        const hidden = document.querySelector('.hidden');
        header?.addEventListener('mouseover', () => {
            hidden.style.display = 'block';
        });
        header?.addEventListener('mouseleave', () => {
            hidden.style.display = 'none';
        });
    });
</script>

<div>
    <div class="header">
        <h1>Kalle Riit</h1>
        <div class="hidden">
            <ul class="routes">
                <li>
                    <a href="/+page">Home</a>
                </li>
                <li>
                    <a href="/about/+page">About</a>
                </li>
                <li>
                    <a href="/projects/+page">Projects</a>
                </li>
            </ul>
        </div>
    </div>


</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap');
    
    div {
        font-family: 'Playfair Display', serif;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        font-size: 2rem;
    }
    .header{
        padding:10px;
        transition: 0.3s;
    }
    .header:hover{
        transform: translateY(-50px);
    }
    .routes{
        width: 100%;
        list-style-type: none;
        display: flex;
        margin: none;
        padding: none;
        justify-content: space-between;
        
    }
    .routes a{
        text-decoration: none;
        font-size: 1.5rem;
        color: black;
    }
    .routes a:hover{
        text-decoration: underline;

    }
    .hidden{
        display:none;
    }
</style>
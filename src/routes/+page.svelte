<script lang="ts">
    import { onMount } from 'svelte';
    onMount(() => {

        let currentURL = window.location.href;
        document.querySelectorAll('a').forEach(link => {
            link.addEventListener('click', (e) => {
                console.log(currentURL, link.href)
                if (currentURL === link.href){
                    e.preventDefault();
                    const reminder = document.querySelector('.link-reminder') as HTMLElement;
                    reminder.style.opacity = '1';
                    reminder.style.transform = 'translateY(10%)';
                    setTimeout(() => {
                        reminder.style.opacity = '0';
                        reminder.style.transform = 'translateY(-10%)';
                    }, 1000);
                }
            });
        })

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
    <p class="link-reminder">You are already on this page ; &#41;</p>
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
    
    :global(:root){
        --raisin-black: #272727ff;
        --mustard: #fed766ff;
        --moonstone: #009fb7ff;
        --dim-gray: #696773ff;
        --antiflash-white: #eff1f3ff;

        background-color: var(--raisin-black);
        color: var(--antiflash-white);
    }

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
    .header:hover {
        transform: translateY(-50px);
    }   
    .header h1{ 
        text-align: center;
        margin: 0;
        transition: 0.5s;
    }
    .header:hover > h1{
        transform: translate(3px, -3px);
        text-shadow: 
            -3px 3px 0px grey,
            -6px 6px 0px var(--dim-gray);
    }
    .routes{
        width: 100%;
        list-style-type: none;
        display: flex;
        justify-content: center;
        padding: 0;
        margin: 0;   
        gap: 10%;   
    }
    .routes a{
        text-decoration: 2px underline var(--raisin-black);
        font-size: 1.5rem;
        color: var(--antiflash-white);
    }
    .routes a:hover{
        text-decoration: underline;
        animation: underline 0.2s;
    }
    .hidden{
        display:none;
        animation: fadeIn 0.4s;
    }
    .link-reminder{
        font-size: 1rem;
        transition: 0.5s all;
        position: absolute;
        top: 20%;
        opacity: 0;
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
            text-underline-offset: 0.25em;
            text-decoration: 2px underline var(--raisin-black);
        }
        to {
            text-underline-offset: 0.1em;
            text-decoration: 2px underline var(--antiflash-white);
        }
    }
</style>


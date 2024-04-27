<script lang="ts">
    import { onMount } from 'svelte';
    import { base } from '$app/paths';

    onMount(() => {
        let currentURL = window.location.href;
        document.querySelectorAll('a').forEach(link => {
            link.addEventListener('click', (e) => {
                if (currentURL === link.href){
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

<p class="link-reminder">You are already on this page ; &#41;</p>
<div class="header">
    <h1>Kalle Riit</h1>
    <div class="hidden">
        <ul class="routes">
            <li>
                <a href="{base}/">Home</a>
            </li>
            <li>
                <a href="{base}/about">About</a>
                
            </li>
            <li>
                <a href="{base}/projects">Projects</a>
            </li>
        </ul>
    </div>
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

    @media(max-width: 768px){
        .header{
            width: 100%;
            height: 10%;
        }
        .header h1{
            font-size: 3rem;
        }
        .routes{
            gap: 5%;
        }
        .routes a{
            font-size: 1.5rem;
        }
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


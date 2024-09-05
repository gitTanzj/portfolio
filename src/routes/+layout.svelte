


<script lang="ts">
    import '$lib/styles/global.css'
    import { page } from '$app/stores';
    import { onDestroy, onMount  } from 'svelte';
    import { base } from '$app/paths';

    let currentPage: any;

    const unsubscribe = page.subscribe(value => {
        currentPage = value;
    });
    

    onDestroy(() => {
        unsubscribe();
    });
</script>

<div class="container">
    {#if currentPage.route.id !== "/"}
        <div class="navigate-back">
            <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0" />
            <a href="{base}/">
                <span class="material-symbols-outlined">
                    chevron_left
                </span>
            </a>
        </div>
    {/if}
    <slot class="slot"></slot>
    <div class="footer">
        <p>© 2024 Kalle Riit</p>
    </div>
</div>

<style>
    .navigate-back{
        position: absolute;
        top: 50%;
        left: 5%;
    }
    .navigate-back:hover{
        animation: arrow-bounce 0.4s infinite alternate;
    }
    .navigate-back a{
        color: var(--antiflash-white);
    }
    .material-symbols-outlined{
        font-family: 'Material Symbols Outlined', sans-serif;
        font-size: 4rem;
    }

    @media(max-width: 768px){
        .navigate-back{
            left: 2%;
        }
        .material-symbols-outlined{
            font-size: 2rem;
        }
    }

    @keyframes arrow-bounce {
        from {
            transform: translateX(0);
        }
        to {
            transform: translateX(-10%);
        }
    }
</style>

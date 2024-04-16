<script lang="ts">
    import '$lib/styles/global.css'

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
    })
</script>


<div class="container">
    <slot></slot>
    <div class="footer">
        <p>© 2024 Kalle Riit</p>
    </div>
</div>

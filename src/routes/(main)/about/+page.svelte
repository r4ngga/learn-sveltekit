<script>
    import { onMount } from 'svelte';
    import { goto } from '$app/navigation';

    onMount(() => {
        const checkStatus = window.location.href;

        if(checkStatus != `${location}/login`){
            if(localStorage.getItem('isLogin') != 'true'){
                goto('/login');
            }
        }
    });
</script>

<svelte:head>
    <title>This About</title>
</svelte:head>
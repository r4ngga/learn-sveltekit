<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';
    import { onMount } from 'svelte';
    import { goto } from '$app/navigation';

    $: logout = async () => {
        let checkStatus = window.location.href;
        if(checkStatus){
            localStorage.setItem('isLogin', 'false');
            goto('/login');
        }
    };
</script>

<div class="w-full h-20 justify-between items-center px-8 border-b-[1px] border-gray-500">
    <nav class="flex space-x-8 text-lg ">
        <li class="list-none h-10 flex items-center hover:border-b-2 hover:border-b-indigo-300">
            <a href="/">Home</a>
        </li>
        <li class="list-none h-10 flex items-center hover:border-b-2 hover:border-b-indigo-300">
            <a href="/about">About</a>
        </li>
        <li class="list-none h-10 flex items-center hover:border-b-2 hover:border-b-indigo-300">
            <a href="/note">Note(Comingsoon)</a>
        </li>
        <li class="list-none h-10 flex items-center hover:border-b-2 hover:border-b-indigo-300">
            <form on:submit|preventDefault={logout} action="">
                <button type="submit" class="list-none h-10 flex items-center hover:border-b-2 hover:border-b-indigo-300">
                    Logout
                </button>
            </form>            
        </li>
    </nav>
</div>
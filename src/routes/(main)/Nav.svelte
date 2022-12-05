<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';
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
            <button class="list-none h-10 flex items-center hover:border-b-2 hover:border-b-indigo-300">
                Logout
            </button>
        </li>
    </nav>
</div>
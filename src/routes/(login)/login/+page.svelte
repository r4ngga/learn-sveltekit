<script>
    /**  */
    import { goto } from "$app/navigation";
    import axios from 'axios';

    let username = '';
    let password = '';

    $:submit = async () => {
        // const resp = await fetch('https://dummyjson.com/auth/login', {
        // method: 'POST',
        // headers: { 'Content-Type': 'application/json' },
        // body: JSON.stringify({
            
        //     username,
        //     password,
        //     // expiresInMins: 60, // optional
        // })
        // }).then(res => res.json())
        // .then(console.log);

        const resp = await axios({
            method: 'POST',
            url: 'https://dummyjson.com/auth/login',
            headers: {},
            data: {
                username,
                password
            }
        });

        if(resp.status === 200){
            goto('/');
            localStorage.setItem('isLogin', 'true');
        }
    }
</script>

<svelte:head>
    <title>Login</title>
</svelte:head>

<section class="w-screen h-screen flex justify-center items-center bg-amber-200">
    
    <form on:submit|preventDefault={submit} 
    action="" 
    class="flex flex-col w-[500px] h-[300px] shadow-lg justify-evenly p-4 rounded-md bg-cyan-200 text-white">
    <h1 class="text-center text-2xl text-gray-700 font-bold">Login</h1>
    <div class="col-span-6 sm:col-span-3">
        <label for="username" class="block text-sm font-medium text-gray-700">Username</label>
        <input bind:value={username} type="text" name="username" id="username"  class="shadow appearance-none border border-red-500 rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline">
    </div>

    <div class="col-span-6 sm:col-span-3">
        <label for="password" class="block text-sm font-medium text-gray-700">Password</label>
        <input bind:value={password} type="password" name="password" id="password"  class="shadow appearance-none border border-red-500 rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline">
    </div>

    <button type="submit"
     class="inline-flex justify-center px-4 py-2 text-sm font-medium
      text-white bg-indigo-600 border border-transparent rounded-md shadow-sm
      hover:bg-indigo-700 focus:outline-none focus:ring-2
      focus:ring-indigo-500 focus:ring-offset-2">Submit</button>
    </form>
</section>
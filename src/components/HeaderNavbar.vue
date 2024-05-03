<template>
    <header class="m-8 mt-4 rounded-xl flex justify-center shadow-sm bg-white">
        <nav class="w-full mx-12 flex flex-row justify-between items-center">
            <router-link to="/">
                <img alt="Vue logo" class="" src="../assets/youtube.svg" width="125" height="125" />
            </router-link>    
            <form action="">
                <input 
                type="text" 
                name="" id="" 
                placeholder="Recherche..."
                class="my-3 ml-8 px-4 py-3 rounded-xl bg-white text-sm">
            </form>
            <font-awesome-icon icon="magnifying-glass" class="text-2xl ml-8" />
        </nav>
    </header>
</template>


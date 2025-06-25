<script lang="js">
    import '../style.css'
    import SideBar from '$lib/components/SideBar.svelte'

    let { children } = $props();
</script>


<div id="container">
    <SideBar/>
    <main>
       {@render children()}
    </main>
</div>

<style>
    #container{
        display: flex;
        max-width: 100dvw;
        height: 100dvh;
        background-color:#fafafa;      
    }
    main{
        display: flex;
        margin: 0 auto;
    }
    
</style>

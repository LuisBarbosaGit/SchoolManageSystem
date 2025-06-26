<script>
    import SideBar from "$lib/components/SideBar.svelte";
    import InfoGrid from '$lib/components/InfoGrid.svelte';
    import {fakeinfo, dados} from '$lib/index'

    for (let index = 0; index < 5; index++) {
        dados[index] = fakeinfo  
    }
</script>

<div id="container">
    <div id="header">
        <div id="header_text">
            <p id="tittle">Manutenção de cursos</p>
            <p id="subtittle">Insira, altere ou exclua cursos</p>
        </div>
    </div>
    <div id="grid">
        <InfoGrid tittle="Cursos cadastrados" subtittle="Lista dos cursos da sua instituição">
            {#each dados as item}
                <div id="item">
                    <span>{item.name}</span>
                    <span>{item.description}</span>
                </div>
            {/each}
        </InfoGrid>
    </div>
</div>

<style>
    #container{
        display: flex;
        flex-direction: column;
        width: 80dvw;
    }

    #tittle{
        display: flex;
        padding: 0;
        margin: 0px 10px;
        font-size: 1.9rem;
    }
    #subtittle{
        font-size: 1.3rem;
        color: #6b7280;
        margin: 0px 12px;
        font-family: sans-serif;
    }
    #header_text{
        display: flex;
        flex-direction: column;
        gap: 0.6rem;
        margin: 10px;
        padding: 5px;
    }
    #grid{
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 30px;
        
    }
    #item{
        display: flex;
        border: 1px solid #6b7280;
        border-radius: 10px;
        padding: 10px;
        flex-direction: column;
        height: 3.5rem;
        gap: 15px;
        background-color: #fdf4ff;
    }
</style>
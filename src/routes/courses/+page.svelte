<script>
    import SideBar from "$lib/components/SideBar.svelte";
    import InfoGrid from '$lib/components/InfoGrid.svelte';
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
            <div>
                <p>olá</p>
            </div>
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
</style>
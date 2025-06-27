<script>
    import SideBar from "$lib/components/SideBar.svelte";
    import InfoGrid from '$lib/components/InfoGrid.svelte';
    import {fakeinfo, dados} from '$lib/index'
	import Button from "$lib/components/Button.svelte";
	import Modal from "$lib/components/Modal.svelte";
	import { fetchModule } from "vite";

    let  data = $state({
        nome : '', 
        descricao : '', 
        duracao: ''
    })
    
    let isModalOpen = $state(false)

    function HandleClick() {
        isModalOpen = true       
    }

    async function submitForm() {
        try {
            const response =  await fetch('/endereco', {
                method : 'POST',
                headers : { 'COntent-Type': 'Application/json'},
                body : JSON.stringfy(data)
            })
            const result = await response.json();
        } catch (error) {
            alert(error)
        }
    }

</script>

<div id="container">
    <div id="header">
        <div id="header_text">
            <p id="tittle">Manutenção de cursos</p>
            <p id="subtittle">Insira, altere ou exclua cursos</p>
        </div>
        <Button text="Incluir" click={HandleClick}/>


    </div>
    <div id="grid">
        <InfoGrid tittle="Cursos cadastrados" subtittle="Lista dos cursos da sua instituição">
            {#each data as item}
                <div id="item">
                    <span>{item.nome}</span>
                    <span>{item.descricao}</span>
                    <span>{item.duracao}</span>
                </div>
            {/each}
        </InfoGrid>
    </div>
    <div>
        {#if isModalOpen}
            <Modal onFechar={() => isModalOpen = false}>
                <form action="" method="post" onsubmit={submitForm}>
                    <label for="nome">Insira o Nome do curso</label>
                    <input type="text" bind:value={data.nome}>
                    <label for="nome">Insira a descrição</label>
                    <input type="text" bind:value={data.descricao}>
                    <label for="nome">Insira a duração</label>
                    <input type="text" bind:value={data.duracao}>
                </form>
                <button type="submit">Enviar</button>
            </Modal>
        {/if}
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
    #header{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

</style>
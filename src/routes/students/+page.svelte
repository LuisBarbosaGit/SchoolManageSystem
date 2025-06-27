<script>
    import SideBar from "$lib/components/SideBar.svelte";
    import InfoGrid from '$lib/components/InfoGrid.svelte';
    import Button from "$lib/components/Button.svelte";
    import {fakeinfo, dados} from '$lib/index';
    import axios from 'axios';

    let students = $state([])
    let  data = $state({
        id : 1,
        name : '', 
        email : '',
        phone: '', 
        courseId: '',
        status: 'active'
    })
    
    let isModalOpen = $state(false)

    function HandleClick() {
        isModalOpen = true       
    }

    async function handleDelete(id){
        try {
            const response = await axios.delete(`https://eb250oif4f.execute-api.us-east-1.amazonaws.com/subjects/students${id}`)
        } catch (error) {
            
        }
    }
     async function submitForm() {
        try {
            const response = await axios.post('https://eb250oif4f.execute-api.us-east-1.amazonaws.com/students', data)
            students = response.data
        } catch (error) {
            alert(error)
        }
    }
    $effect(() => {
    const fetchData = async () => {
        try {
            const response = await axios.get('https://eb250oif4f.execute-api.us-east-1.amazonaws.com/students');

            data = response.data;
            console.log("Dados recebidos com sucesso!", data);

        } catch (error) {
            console.error("Falha ao buscar os dados:", error);
        }
    };

    fetchData();
});
</script>

<div id="container">
    <div id="header">
        <div id="header_text">
            <p id="tittle">Manutenção de estudantes</p>
            <p id="subtittle">Insira, altere ou exclua estudante</p>
        </div>
        <Button text="Incluir"/>
    </div>
    <div id="grid">
        <InfoGrid tittle="Disciplinas cadastrados" subtittle="Todas as disciplinas cadastradas em seu curso">
           {#each students as item}
                <div id="item">
                    <span>{item.name}</span>
                    <span>{item.status}</span>
                    <span>{item.courseId}</span>
                    <div> <button onclick={() => handleDelete(item.Id)}> Exluir</button></div>
                </div>
            {/each}
        </InfoGrid>
    </div>
    <div>
        {#if isModalOpen}
            <Modal onFechar={() => isModalOpen = false}>
                <form action="" method="post" onsubmit={submitForm}>
                    <label for="nome">Insira o Nome do aluno</label>
                    <input type="text" bind:value={data.name}>
                    <label for="nome">Insira o email do aluno</label>
                    <input type="text" bind:value={data.email}>
                    <label for="nome">Insira o telefone</label>
                    <input type="text" bind:value={data.phone}>
                    <label for="nome">Insira o id do curso cadastrado</label>
                    <input type="text" bind:value={data.courseId}>
                    <button type="submit">Enviar</button>
                </form>
                
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
        gap: 10px;
        background-color: #fdf4ff;
    }
    #header{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>
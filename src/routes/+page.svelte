<script lang="js">
    import '../style.css'
    import SideBar from '$lib/components/SideBar.svelte'
	import DashboardCard from '$lib/components/DashboardCard.svelte';
	import InfoGrid from '$lib/components/InfoGrid.svelte';
    import {fakeinfo, dados} from '$lib/index'

    for (let index = 0; index < 5; index++) {
        dados[index] = fakeinfo  
    }
</script>


<div id="content">
    <h1 id="tittle">Sistema de gestão escolar</h1>
    <div id="dashboardCards">
        <DashboardCard title="Total de Alunos" numInfo="567"/>
        <DashboardCard title="Disciplinas" numInfo="567"/>
        <DashboardCard title="Alunos Aprovados" numInfo="540"/>
        <DashboardCard title="Alunos Reprovados" numInfo="27"/>
    </div>
    <div id="grid">
        <InfoGrid tittle="Alterações recentes" subtittle="Ultimas Alterações do sistema">
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
    #content{
        display: flex;
        flex-direction: column;
        width: 80dvw;
    }
    #tittle{
        display: flex;
        margin-left: 1.4rem;
    }
    #dashboardCards{ 
        margin: 1.3rem;
        align-items: center;
        justify-content: center;
        display: flex;
        gap: 8rem;
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
        gap: 10px;
    }
    
</style>


<script>
	import { ChartNoAxesCombinedIcon } from "@lucide/svelte";

    
    const {title, numInfo } = $props()
</script>

<div id="card">
    <div id="content-Card">
        <div id="tittle">
            <span>{title}</span>
            <ChartNoAxesCombinedIcon />
        </div>
        <span id="number">{numInfo}</span>
    </div>
</div>

<style>
    #card{
        display: flex;
        width: 15rem;
        height: 5rem;
        border: 0.5px solid #9ca3af;
        border-radius: 10px;
        background-color: white;
        padding: 15px 15px;
    }
    #content-Card{
        display: flex;
        flex-direction: column;
        gap: 0.9rem;
        text-align: left;
        font-size: 1.7rem;
        font-family: sans-serif;
        font-weight: bold; 
        width: 11rem;
        height: 5rem;
    }
    #tittle{
        display: flex;
        align-items: center;
        justify-content: space-between;
        color: #111827;
        font-size: 0.8rem;
        font-family: Arial, Helvetica, sans-serif;     
    }
    #number{
        display: flex;
        align-items: end;
        justify-content: center;
        width: 100%;
        font-size: 2rem;
    }
    
</style>
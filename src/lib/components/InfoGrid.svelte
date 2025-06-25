<script>
    const {tittle, subtittle, children} = $props()
</script>

<div id="historyCard">
    <span id="historyTittle">{tittle}</span>
    <span id="historySubtittle">{subtittle}</span>
    <div id="historyInfo">
        {@render children()}   
    </div>
</div>

<style>
    #historyCard{
        display: flex;
        width: 95%;
        border: 0.5px solid #9ca3af;
        border-radius: 10px;
        background-color: white;
        flex-direction: column;
        padding: 15px 15px;
        gap: 5px;
    }
    #historyTittle{
        font-size: 1.8rem;
        font-weight: bold;
        color: black;
        font-family: sans-serif;
    }
    #historySubtittle{
        font-size: 1rem;
        color: #6b7280;
        font-family: sans-serif;
    }
</style>
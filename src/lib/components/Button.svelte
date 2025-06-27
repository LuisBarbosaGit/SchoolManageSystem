<script>
    let {text, click} = $props()
</script>

<button onclick={click}>{text}</button>


<style>
    button{
        width: 6rem;
        height: 3rem;
        background-color: blue;
        border-radius: 10px;
        color: white;
        text-align: center;
        transition: all 0.1s;
        
    }
    button:hover{
        transform: scale(1.02);
        cursor: pointer;
    }
</style>
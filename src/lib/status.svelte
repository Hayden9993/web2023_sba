<script>
    export let species;
    export let status;
</script>

<h3>
    <div class="{status}"/> 
    {status} - {species}
</h3>

<style>
    .Alive{
        background:greenyellow;
        
    }
    .unknown{
        background:gray;
    }
    .Dead{
        background:firebrick;
    }
    div{
        width:10px;
        height:10px;
        border-radius:100%;
        margin-right:10px;
    }
    h3{
        color:white;
        display:flex;
        align-items:center;
    }
</style>
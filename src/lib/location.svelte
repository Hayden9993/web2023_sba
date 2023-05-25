<script>
    export let location;
    export let location_path;
</script>

<h3 class="locationLabel">Last known location</h3>
<h3 class="location"><a href="location?id={location_path}">{location}</a></h3>

<style>
    *{
        font-size:16px;
        margin:0 0 5px;  
    }
    .locationLabel{
        color:#777;      
    }

    .location{
        color:white;
    }
</style>
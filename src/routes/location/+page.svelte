<script>

    import { page } from '$app/stores';
    
    const location_id = $page.url.searchParams.get('id');

    let name;
    let type;
    let dimension;
    let residents = 0;

    fetch(`https://rickandmortyapi.com/api/location/${location_id}`)
        .then(res => res.json())
        .then(data => {
            name = data.name
            type = data.type
            dimension = data.dimension
            for (let resident in data.residents) {
                residents++
            } 
        })

</script>

<div>
    <h1>{ name }</h1>
    <h3>{ type } | { dimension }</h3>
    <h5>{ residents } residents</h5>
</div>
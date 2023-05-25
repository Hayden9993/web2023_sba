<script>

    import Location from "./location.svelte";
    import Status from "./status.svelte";

    export function rng(max) { /*rng returns a random number within a range*/
        return Math.floor(Math.random() * max)
    }

    let name;
    let status;
    let species;
    let gender;
    let location;
    let image;
    let location_path;
    const location_regex = /[^/]+$/

    fetch(`https://rickandmortyapi.com/api/character/`)
    .then(res => res.json())
    .then(data => {

        let totalChars = data.info.count
        let charNo = rng(totalChars)
        fetch(`https://rickandmortyapi.com/api/character/${charNo}`)
        .then(res => res.json())
        .then(charData => {
            name =  charData.name;
            status = charData.status
            species = charData.species
            gender = charData.gender
            location = charData.location.name
            location_path = charData.location.url.match(location_regex)
            image = charData.image
        })
        
    })

</script>

<section class="card">
    <div class="image" style="background-image:url({image});"></div>
    <div class="info">
        <h1 class="name">{name}</h1>
        <Status status={status} species={species} />
        <Location location={location} location_path={location_path} />
    </div>
</section>

<style>
    *{
        font-family:sans-serif;
    }

    .card{
        background:#333;
        overflow:hidden;
        height:240px;
        display:flex;      
        border-radius:20px;  
    }

    .image{
        width:30%;
        background-image:url('https://rickandmortyapi.com/api/character/avatar/119.jpeg');
        background-size:cover;
        background-position:center;
    }

    .info{
        padding:10px 20px 15px 20px;
    }

    .name{
        color:white;
    }

    
</style>
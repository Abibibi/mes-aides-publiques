<script>
    export let nature;
    export let picture;
    export let title;
    export let description;

    $: type = nature.title;
</script>

<div>

</div>
    <h1>{type}</h1>
    <div>
        <img src={picture} alt={title}/>
    </div>
    <h2>{title}</h2>
    <p>{@html description}</p>
    <button>Vérifier éligibilité</button>
    <a>En savoir plus</a>
<style>
    button {
        display: block;
    }
</style>
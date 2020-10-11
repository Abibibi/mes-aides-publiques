<script>
    export let type;
    export let picture;
    export let title;
    export let description;
</script>

<div class="card">
    <h1>{type}</h1>
    <div class="card-picture-container">
        <img src={picture} alt={title}/>
    </div>
    <h2>{title}</h2>
    <div class="card-description">{@html description}</div>
    <div class="card-cta">
        <button>Vérifier éligibilité<span /></button>
        <a>En savoir plus</a>
    </div>
</div>

<style>
    .card {
        font-family: 'Mukta Mahee', sans-serif;
        display: flex;
        flex-direction: column;
        align-items: center;
        border: 2px solid #FC9F5B;
        border-radius: .3rem;
        padding: 1rem;
        text-align: center;
        position: relative;
    }

    h1 {
        color: #A3A3A3;
        font-weight: 500;
    }

    h1, .card-description, a {
        font-size: .9em;
    }

    .card-picture-container {
        width: 5rem;   
        min-height: 9rem;
        display: flex;
        align-items: center;
    }

    .card-picture-container, .card-description {
        margin: .9rem 0;
    }
   
    img {
        width: 100%;
    }

    h2 {
        color: #FC9F5B;
        font-weight: 500;
        font-size: 1.1em;
        line-height: 1.4rem;
    }

    .card-description {
        line-height: 1.2rem;
        color: #626263;
    }

    button {
        margin: .8rem 0;
        border-radius: 1.3rem;
        padding: 0.2rem 1rem;
        background-color: #4195DB;
        border: none;
        color: #FFFFFF;
        font-weight: 500;
    }

    button:hover {
        background-color: #367db8;
    }

    button, a {
        cursor: pointer;
    }

    span {
        height: 7px;
        width: 7px;
        border-right: 1.5px solid #FFFFFF;
        border-bottom: 1.5px solid #FFFFFF;
        display: inline-block;
        transform: rotate(-45deg);
        margin: 0 .4rem 0 1rem;
    }

    a {
        color: #4195DB;
        display: block;
    }

    @media only screen and (max-width: 549px) {
        .card {
            margin-bottom: 1rem;
        }
    }
    
    @media only screen and (min-width: 550px) {
        .card {
            min-height: 28rem;
        }

        .card-cta {
            position: absolute;
            bottom: 1rem;
        }   
    }

    @media only screen and (min-width: 768px) and (max-width: 1300px) {
        .card {
            min-height: 32rem;
        }
    }
</style>
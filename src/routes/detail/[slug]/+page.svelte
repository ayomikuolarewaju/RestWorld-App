<script>
    import {page} from '$app/stores'
    let slug = $page.params.slug
    console.log
    export let data;
    let country = data.countries;
    let ctydata = country.filter((cty)=>cty.name === slug)
    console.log(ctydata)
</script>


<div class=" container flex flex-col bg-gray-800 ">
    <div class="flex flex-row pb-20 ">
        <div class="flex flex-col mb-10 w-20">
            <a data-sveltekit-reload class="bg-gray-900 shadow-2xl text-white p-2 
            rounded-t-md text-center w-3/3" href="/"> &#8592; Back</a>
        </div>
       
            <div class="md:flex md:flex-row mt-40 my-auto mx-auto flex flex-col">
                <div>
                    <img src="{ctydata[0].flag}" alt="" srcset="" width="500" height="500">
                </div>
                <div class="p-5 text-white space-y-2 flex flex-col">
                    <div>
                        <h4 class="text-2xl font-bold">{ctydata[0].name}</h4>
                    </div>
                    <div class="grid grid-flow-row grid-cols-2 gap-10">
                        <small>Native Name: {ctydata[0].nativeName}</small>
                        <small>Population: {ctydata[0].population}</small>
                        <small>Top Level Domain: {ctydata[0].topLevelDomain}</small>
                        <small>Currencies: {ctydata[0].currencies}</small>
                        <small>Subregion: {ctydata[0].subregion}</small>
                        <small>Region: {ctydata[0].region}</small>
                        <small>Languages: {ctydata[0].languages[0].name}</small>
                        <small>Capital: {ctydata[0].capital}</small>
                    </div>
                    <div class="flex flex-row justify-around pt-10">
                        <p>Border Countries:</p>
                        {#each ctydata[0].borders as border}
                        <button class="bg-gray-900 shadow-2xl text-white p-2 rounded-b-md text-center w-3/3 space-x-10">
                            {border}
                        </button>
                        {/each}
                    </div>
                </div>
            </div>
    </div>
</div>
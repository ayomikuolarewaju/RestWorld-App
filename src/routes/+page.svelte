<script>
    export let data;
   
    let country = data.countries;
    console.log(country)
   
    let asia = country.filter((cty)=>cty.region === 'Asia')
    console.log(asia)
    
    let africa = country.filter((cty)=>cty.region === 'Africa')
    console.log(africa)
    
    let america = country.filter((cty)=>cty.region === 'Americas')
    console.log(america)

    let europe = country.filter((cty)=>cty.region === 'Europe')
    console.log(europe)

    let oceania = country.filter((cty)=>cty.region === 'Oceania')
    console.log(oceania)

    let flter = country;

    let rev = false;

</script>


<div class="flex flex-col bg-gray-800">

    <div class="container flex flex-row justify-between relative mb-10 mx-auto">
        <div id="search">
            <span>&#128269;</span><input type="text" id="search"   placeholder="Search By Country" 
            class="p-2 bg-gray-900 text-white rounded-md" >
        </div>
        <div id="searchbyregion" class="flex flex-col w-40 absolute z-30 right-10 cursor-pointer">
            <div on:click={()=>{ rev = !rev}} on:keydown>
                <p class="text-white bg-gray-900 shadow-2xl mb-1 p-2 rounded-t-md">All region by filter</p>
            </div>
            {#if rev == true}
            <button class="text-white bg-gray-900 mb-1 p-2" on:click={()=>{flter = asia}}>Asia</button>
            <button class="text-white bg-gray-900 mb-1 p-2" on:click={()=>{flter = africa}}>Africa</button>
            <button class="text-white bg-gray-900 mb-1 p-2" on:click={()=>{flter = america}}>America</button>
            <button class="text-white bg-gray-900 mb-1 p-2" on:click={()=>{flter = europe}}>Europe</button>
            <button class="text-white bg-gray-900 mb-1 p-2 rounded-b-md" on:click={()=>{flter = oceania}}>Oceania</button>
                
            {/if}
            
        </div>
    </div>
    <div class="container md:grid md:grid-flow-row md:gap-10 md:grid-cols-4 mx-auto flex flex-col">
        {#if flter === country}
        {#each country as cty (cty.name) }
        <div class="flex flex-col bg-gray-700 pb-5">
            <a href="/detail/{cty.name}"><img src="{cty.flag}" alt="" srcset="" width="300" height="300"></a>
            <div class="p-5 text-white space-y-2">
                <h4 class="font-bold">{cty.name}</h4>
                <p>Population:{cty.population}</p>
                <p>Region:{cty.region}</p>
                <p>Capital:{cty.capital}</p>
            </div>
        </div>
    {/each}
    {/if}
        {#if flter === asia}
            {#each asia as cty (cty.name) }
            <div class="flex flex-col bg-gray-700 pb-5">
                <a href="/detail/{cty.name}"><img src="{cty.flag}" alt="" srcset="" width="300" height="300"></a>
                <div class="p-5 text-white space-y-2">
                    <h4 class="font-bold">{cty.name}</h4>
                    <p>Population:{cty.population}</p>
                    <p>Region:{cty.region}</p>
                    <p>Capital:{cty.capital}</p>
                </div>
            </div>
        {/each}
        {/if}
                {#if flter === africa}
            {#each africa as cty (cty.name) }
            <div class="flex flex-col bg-gray-700 pb-5">
                <a href="/detail/{cty.name}"><img src="{cty.flag}" alt="" srcset="" width="300" height="300"></a>
                <div class="p-5 text-white space-y-2">
                    <h4 class="font-bold">{cty.name}</h4>
                    <p>Population:{cty.population}</p>
                    <p>Region:{cty.region}</p>
                    <p>Capital:{cty.capital}</p>
                </div>
            </div>
        {/each}
        {/if}
                {#if flter === america}
            {#each america as cty (cty.name) }
            <div class="flex flex-col bg-gray-700 pb-5">
                <a href="/detail/{cty.name}"><img src="{cty.flag}" alt="" srcset="" width="300" height="300"></a>
                <div class="p-5 text-white space-y-2">
                    <h4 class="font-bold">{cty.name}</h4>
                    <p>Population:{cty.population}</p>
                    <p>Region:{cty.region}</p>
                    <p>Capital:{cty.capital}</p>
                </div>
            </div>
        {/each}
        {/if}
                {#if flter === europe}
            {#each europe as cty (cty.name) }
            <div class="flex flex-col bg-gray-700 pb-5">
                <a href="/detail/{cty.name}"><img src="{cty.flag}" alt="" srcset="" width="300" height="300"></a>
                <div class="p-5 text-white space-y-2">
                    <h4 class="font-bold">{cty.name}</h4>
                    <p>Population:{cty.population}</p>
                    <p>Region:{cty.region}</p>
                    <p>Capital:{cty.capital}</p>
                </div>
            </div>
        {/each}
        {/if}
                {#if flter === oceania}
            {#each oceania as cty (cty.name) }
            <div class="flex flex-col bg-gray-700 pb-5">
                <a href="/detail/{cty.name}"><img src="{cty.flag}" alt="" srcset="" width="300" height="300"></a>
                <div class="p-5 text-white space-y-2">
                    <h4 class="font-bold">{cty.name}</h4>
                    <p>Population:{cty.population}</p>
                    <p>Region:{cty.region}</p>
                    <p>Capital:{cty.capital}</p>
                </div>
            </div>
        {/each}
        {/if}
    </div>
</div>
<script>

    import "../app.css";
    let changeMode = false
  </script>
  
{#if changeMode = true}
<div class=" flex flex-col bg-gray-800 h-auto p-7">
  <div class="container flex flex-row bg-gray-900 text-white shadow-2xl rounded-md mb-5 justify-between p-5 mx-auto">
    <div>
       <h4>Where In The World?</h4>
    </div>
    <div on:click={()=>{!changeMode}} on:keydown class='cursor-pointer'>
       <h4>Dark Mode</h4>
    </div>
   </div>

  <slot />
 
</div>
{:else}
<div class=" flex flex-col bg-gray-100 h-auto p-7">
  <div class="container flex flex-row bg-white text-black shadow-2xl rounded-md mb-5 justify-between p-5 mx-auto">
    <div>
       <h4>Where In The World?</h4>
    </div>
    <div on:click={()=>{!changeMode}} on:keydown class='cursor-pointer'>
       <h4>Dark Mode</h4>
    </div>
   </div>

  <slot />
 
</div>
  
{/if}




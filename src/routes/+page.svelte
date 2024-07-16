<script lang="ts">

let equation:string=" ";

function addToEquation(value:string){
 equation+=value
}
function backspace(){
  switch(equation.substring(equation.length-3,equation.length)){
  case " * ":
  case " + ":
  case " - ":
  case " / ":
  equation=equation.substring(0,equation.length-3);
  break;
    default:
    equation=equation.substring(0,equation.length-1);
  }
 
}
function clear(){
  equation=" "
}

function sqrt() {
    equation = Math.sqrt(eval(equation)).toString();
}

function solve(){
equation =eval(equation);

}


</script>
<svelte:head>
  <title>
    calculator
  </title>
</svelte:head>
   <div class=" bg-slate-200  rounded-xl max-w-[15rem]
    grid grid-cols-4 gap-3 p-3 font-semibold shadow-2xl ">

   <div class="bg-gray-400 rounded-full col-span-4 h-12 flex items-center px-4 mb-3 border border-gray-400 text-white text-xl font-semibold break-all overflow-y-auto">
   {equation}
   </div>
    <button  on:click={()=>addToEquation ('/100')} class="bg-gray-300  hover:bg-gray-300/50"> % </button>
    <button on:click={backspace} class="bg-gray-300  hover:bg-gray-300/50">
      <!--backspace -->
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M22 3H7c-.69 0-1.23.35-1.59.88L0 12l5.41 8.11c.36.53.9.89 1.59.89h15c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2m-3 12.59L17.59 17L14 13.41L10.41 17L9 15.59L12.59 12L9 8.41L10.41 7L14 10.59L17.59 7L19 8.41L15.41 12z"/></svg>
    </button>
    <button on:click={sqrt} class="bg-gray-300 text-black hover:bg-gray-800/50"> 
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12h2l4 8l4-16h8"/></svg>
    </button>

    <button on:click={clear} class="bg-gray-800 text-white hover:bg-gray-800/50"> AC </button>
    <button  on:click={()=>addToEquation ('7')}> 7 </button>
    <button  on:click={()=>addToEquation ('8')}> 8 </button>
    <button  on:click={()=>addToEquation ('9')}> 9 </button>
    <button  on:click={()=>addToEquation (' - ')} class="bg-blue-200 hover:bg-blue-200/50"> 
      <!--minus -->
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 12.998H5v-2h14z"/></svg>
    </button>
    <button  on:click={()=>addToEquation ('4')}> 4 </button>
    <button  on:click={()=>addToEquation ('5')}> 5 </button>
    <button  on:click={()=>addToEquation ('6')}> 6 </button>
    <button  on:click={()=>addToEquation (' / ')} class="bg-blue-200  hover:bg-blue-200/50"> 
      <!--dividion -->
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 13H5v-2h14zm-7-8a2 2 0 0 1 2 2a2 2 0 0 1-2 2a2 2 0 0 1-2-2a2 2 0 0 1 2-2m0 10a2 2 0 0 1 2 2a2 2 0 0 1-2 2a2 2 0 0 1-2-2a2 2 0 0 1 2-2"/></svg>
    </button>
    <button  on:click={()=>addToEquation ('1')}> 1 </button>
    <button  on:click={()=>addToEquation ('2')}> 2 </button>
    <button  on:click={()=>addToEquation ('3')}> 3 </button>
    <button  on:click={()=>addToEquation (' * ')} class="bg-blue-200  hover:bg-blue-200/50"> 
      <!--multiply -->
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 6.41L17.59 5L12 10.59L6.41 5L5 6.41L10.59 12L5 17.59L6.41 19L12 13.41L17.59 19L19 17.59L13.41 12z"/></svg>
    </button>
    <button  on:click={()=>addToEquation ('.')}> . </button>
    <button on:click={()=>addToEquation ('0')}> 0 </button>
    <button on:click={()=>solve()} class="bg-gray-300  hover:bg-gray-300/50" > 
      <!--equal -->
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 10H5V8h14zm0 6H5v-2h14z"/></svg>
    </button>
    <button  on:click={()=>addToEquation (' + ')} class="bg-blue-200  hover:bg-blue-200/50"> 
      <!-- plus -->
      <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"/></svg>
    </button>
   </div>
  

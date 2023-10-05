
<title>Unimportant Title Lmao</title>

<script lang="ts">
	import { browser } from '$app/environment';
	let tasks = ["Sample task"]
	let finished:string[] = []
	let today = new Date().getFullYear()+'-'+("0"+(new Date().getMonth()+1)).slice(-2)+'-'+("0"+new Date().getDate()).slice(-2)
	let temp = ""
	let yaytemp= ""
	let randomized:string[] = []
	let dates=["2023-10-3"]
	let parrots: string[] = ["bobrossparrot.gif",
"portalparrot.gif",
"pythonparrot.gif",
"revertitparrot.gif",
"rotatingparrot.gif",
"ryangoslingparrot.gif",
"schnitzelparrot.gif",
"shipitparrot.gif",
"shufflefurtherparrot.gif",
"shufflepartyparrot.gif",
"skiparrot.gif",
"slomoparrot.gif",
"sovjetparrot.gif",
"stalkerparrot.gif",
"standupparrot.gif",
"tacoparrot.gif",
"tripletsparrot.gif",
"uparrowparrot.gif",
"upvoteparrot.gif",
"wave1parrot.gif",
"wave2parrot.gif",
"wave3parrot.gif",
"wave4parrot.gif",
"wave5parrot.gif",
"wave6parrot.gif",
"wave7parrot.gif",
"wave8parrot.gif",
"wave9parrot.gif",
"chillparrot.gif",
"coffeeparrot.gif",
"cryptoparrot.gif",
"dabparrot.gif",
"darkbeerparrot.gif",
"databaseparrot.gif",
"deployparrot.gif",
"dizzyparrot.gif",
"docparrot.gif",
"dreidelparrot.gif",
"drupal_parrot.gif",
"ethparrot.gif",
"explodyparrot.gif",
"fadingparrot.gif",
"fidgetparrot.gif",
"fiestaparrot.gif",
"fixparrot.gif",
"halalparrot.gif",
"hamburgerparrot.gif",
"harrypotterparrot.gif",
"icecreamparrot.gif",
"krakenparrot.gif",
"loveparrot.gif",
"luckyparrot.gif",
"margaritaparrot.gif",
"matrixparrot.gif",
"mergedparrot.gif",
"metalparrot.gif",
"mongodbparrot.gif",
"oldtimeyparrot.gif",
"papalparrot.gif",
"parrot.gif",
"pear-parrots.gif",
"pizzaparrot.gif",
"asyncparrot.gif",
"bananaparrot.gif",
"blondesassyparrot.gif",
"bluescluesparrot.gif",]
let randomElement = "https://cultofthepartyparrot.com/parrots/"+parrots[Math.floor(Math.random() * parrots.length)];

	function handleclick(){
		if (yaytemp !== ""){
			finished.push(yaytemp)
			let idx = tasks.indexOf(yaytemp);
			tasks.splice(idx, 1);
			randomElement = "https://cultofthepartyparrot.com/parrots/"+parrots[Math.floor(Math.random() * parrots.length)];
			randomized.push(randomElement)
		}
		if (temp !== ""){
			tasks.push(temp)
			dates.push(new Date().getFullYear()+'-'+("0"+(new Date().getMonth()+1)).slice(-2)+'-'+("0"+new Date().getDate()).slice(-2))
		}
		

		tasks = tasks
		finished = finished
		dates = dates
		temp=""
		yaytemp= ""
	}
	function resetclick(){	
	finished = []
	randomized = []
	}
	$:{
	if (finished.length = 0){
		finished = JSON.parse(localStorage.getItem("finished") || "");}
	if (tasks.length = 0){
	tasks = JSON.parse(localStorage.getItem("tasks")||"");}
	 if (finished.length != 0) {
		localStorage.setItem("finished", JSON.stringify(finished));
	}
	 if (tasks.length != 0){
		localStorage.setItem("tasks", JSON.stringify(tasks));
	}

	}
</script>
<div class = "site" >
	<h1><img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot">Rex's Scuffed To Do List!<img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></h1><br>
	<p>Input New Tasks One At A Time:</p>
	<input type="text-box" style="width: 300px font-size:500px" bind:value={temp}><br>
	<p>Check Off a Completed Task:</p>
	{#if (tasks.length) != 0}
	{#each tasks as task}
		<input 
		type="checkbox"
		value = {task}
		bind:group={yaytemp}
	>{task}<br>
	{/each}
	{:else}
	<p><i>you have no tasks lol which either means your the most productive person in the world, or so lazy as to not even manage your todo list</i></p>
	{/if}
	<button on:click ={handleclick}>Click to update! </button><br>
	<br><br><br><br>

	<h1><img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot">Completed Tasks!<img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></h1>
	{#if (finished.length) !=0}
	{#each finished as finish,i}
	
	<h4 style="font-size: 50px;">{finish} is done! <img src={randomized[i]} alt = "partyparrot"/></h4>
	<p> Started on {dates[i]}</p>
	
	{/each}
	{:else}
	<p>get to work idiot</p>
	{/if}
	<button on:click = {resetclick}>Reset All Tasks <img src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></button>
</div>

































<style>h1 {
    display:inline-block;
    font-size: 72px;
    background: linear-gradient(45deg,#FF0000,#FF7F00,#FFFF00,#00FF00,#0000FF,#4B0082,#8B00FF);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-size: 400% 400%;

    -webkit-animation: rainbowanim 10s ease infinite;
       -moz-animation: rainbowanim 10s ease infinite;
            animation: rainbowanim 10s ease infinite;
}

@-webkit-keyframes rainbowanim {
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}
}
@-moz-keyframes rainbowanim {
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}
}
@keyframes rainbowanim { 
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}

	
}
.site {
        margin: 25px;
        border-style: solid;
        border-width: 5px;
        border-color: red;
        border-radius: 10px;
        padding: 50px;

        color: darkmagenta;
        background-color: lightblue;
      }
</style>
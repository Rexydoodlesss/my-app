<title>Unimportant Title Lmao</title>
<script>
	let tasks = ["real", "fake"]
	let finished = ["not real", "not fake"]
	let temp = ""
	let yaytemp= ""
	

	function handleclick(){
		if (temp !== ""){
		tasks.push(temp)
		}
		if (yaytemp !== ""){
		finished.push(yaytemp)
		let idx = tasks.indexOf(yaytemp);
		tasks.splice(idx, 1);
		
		}

		tasks = tasks
		finished = finished
		temp=""
		yaytemp= ""
	}
</script>
<div class = "site">
	<h1>Rex's Scuffed To Do List:</h1><br>
	<p>Input New Tasks One At A Time:</p>
	<input type="text-box" style="width: 300px font-size:500px" bind:value={temp}><br>
	<p>Check Off a Completed Task:</p>
	{#if tasks.length != 0}
	{#each tasks as task}
		<input 
		type="checkbox"
		value = {task}
		bind:group={yaytemp}
	>{task}<br>
	{/each}
	<button on:click ={handleclick}>Click to update! </button><br>
	{:else}
	<p>you have no tasks lol which either means your the most productive person in the world, or so lazy as to not even manage your todo list</p>
	{/if}
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
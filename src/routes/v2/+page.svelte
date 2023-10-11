<script lang="ts">
    import type { Todo } from "$lib/types";

    let tasks: Todo[] = [];
    let color = "white";
    let color2 = "black";
    let colors = ["red", "orange", "yellow", "green", "blue"];
    let finished: string[] = [];
    let today =
        new Date().getFullYear() +
        "-" +
        ("0" + (new Date().getMonth() + 1)).slice(-2) +
        "-" +
        ("0" + new Date().getDate()).slice(-2);
    let input = "";
    let randomized: string[] = [];
    let funnyrandom = "https://cultofthepartyparrot.com/parrots/parrot.gif";
    let parrots: string[] = [
        "bobrossparrot.gif",
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
        "bluescluesparrot.gif",
    ];
    let randomElement ="https://cultofthepartyparrot.com/parrots/" + parrots[Math.floor(Math.random() * parrots.length)];
    function funnyfunction() {
        funnyrandom ="https://cultofthepartyparrot.com/parrots/" + parrots[Math.floor(Math.random() * parrots.length)];
        color = colors[Math.floor(Math.random() * colors.length)];
        color2 = colors[Math.floor(Math.random() * colors.length)];
        randomized.forEach((element) => {});
    }
    function handlefinish(taskToComplete: string) {
        console.log(taskToComplete);

        tasks.forEach((task) => {
            if ((task.task == taskToComplete)) {
                task.done = true;
            }
        });
        tasks = tasks
    }

    // let idx = tasks.indexOf(task);
    // 		console.log(task)
    // 		finished.push(tasks[idx])
    // 		tasks.splice(idx, 1);
    // 		randomElement = "https://cultofthepartyparrot.com/parrots/"+parrots[Math.floor(Math.random() * parrots.length)];
    // 		randomized.push(randomElement)
    // 		finished = finished
    // 		tasks = tasks
    // 		randomized = randomized

    function handleclick() {
        if (input !== "") {
            tasks.push({
                task: input,
                done: false,
                parrotpath: parrots[Math.floor(Math.random() * parrots.length)],
                date:
                    new Date().getFullYear() +
                    "-" +
                    ("0" + (new Date().getMonth() + 1)).slice(-2) +
                    "-" +
                    ("0" + new Date().getDate()).slice(-2),
            });
            tasks = tasks;
            input = ""
        }
    }

    // if (finished.length == 0){
    // 	finished = JSON.parse(localStorage.getItem("finished") || "");}

    // if (dates.length == 0){
    // 	dates = JSON.parse(localStorage.getItem("dates") || "");}
    // if (tasks.length == 1){
    // tasks = JSON.parse(localStorage.getItem("tasks")||"");}

    // if (randomized.length == 0){
    // randomized = JSON.parse(localStorage.getItem("randomized")||"");
    // }
    //  {
    // localStorage.setItem("randomized", JSON.stringify(randomized));
    // localStorage.setItem("finished", JSON.stringify(finished));
    // localStorage.setItem("tasks", JSON.stringify(tasks));
    // localStorage.setItem("dates", JSON.stringify(dates));

    // }
</script>

<title>Unimportant Title Lmao</title>

<div class="site">
    <h1>
        <img
            style="height: 40px;"
            src="https://cultofthepartyparrot.com/parrots/parrot.gif"
            alt="partyparrot"
        />Rex's Scuffed To Do List!<img
            style="height: 40px;"
            src="https://cultofthepartyparrot.com/parrots/parrot.gif"
            alt="partyparrot"
        />
    </h1>
    <br />
    <p>Input New Tasks One At A Time:</p>
    <input
        type="text-box"
        style="width: 300px font-size:500px"
        bind:value={input}
    /><br />
    <button on:click={handleclick}>Click to update! </button><br/><br/><br/><br />
    <p>Cluck Off a Completed Task:</p>

    {#each tasks as task}
        {#if task.done == false}
        <button class="task" on:click={() => handlefinish(task.task)}
            >{task.task}</button><br>
        {/if}
        {#if task.done == true}
        <p><i>you have no tasks lol which either means your the most productive person in the world, or so lazy as to not even manage your todo list</i></p>
    {/if}
    {/each}

    <h1><img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot">Completed Tasks!<img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></h1>
    <br>
    {#each tasks as task}
        {#if task.done == true}
        <h4 style="font-size: 50px;">"{task.task}" is done! <img src={`https://cultofthepartyparrot.com/parrots/${task.parrotpath}`} alt = "partyparrot"/></h4><br>        
        {/if}
        {:else}
        <p>get to work idiot</p>
    {/each}
    <!-- {#if (tasks.length) != 0}
	{#each tasks as task}
		{#if (color == color2)}
		<button class="task" style="color: black; background-color: white" on:click={ () => handlefinish(task) }>{task}</button><br>
		{:else}
		<button class="task" style="color: {color2}; background-color: {color}" on:click={ () => handlefinish(task) }>{task}</button><br>
		{/if}
	{/each}
	{:else}
	<p><i>you have no tasks lol which either means your the most productive person in the world, or so lazy as to not even manage your todo list</i></p>
	{/if}
	<br><br><br><br>
	<h1><img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot">Completed Tasks!<img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></h1>
	{#if (finished.length) !=0}
	{#each finished as finish,i}
	<h4 style="font-size: 50px;">"{finish}" is done! <img src={randomized[i]} alt = "partyparrot"/></h4>
	<p> Started on {dates[i]}</p>
	{/each}
	{:else}
	<p>get to work idiot</p>
	{/if}
	<button on:click = {resetclick}>Reset All Tasks <img src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></button> <br><br><br><br>

	<button on:click = {funnyfunction}>Need to destress? Click here! <img src="{funnyrandom}" alt="woulda been a random partyparrot"></button> -->
</div>

<style>
    h1 {
        display: inline-block;
        font-size: 72px;
        background: linear-gradient(
            45deg,
            #ff0000,
            #ff7f00,
            #ffff00,
            #00ff00,
            #0000ff,
            #4b0082,
            #8b00ff
        );
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-size: 400% 400%;

        -webkit-animation: rainbowanim 10s ease infinite;
        -moz-animation: rainbowanim 10s ease infinite;
        animation: rainbowanim 10s ease infinite;
    }
    .task {
        background-color: green;
        color: black;
        padding: 8px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 12px;
        margin: 4px 2px;
        cursor: pointer;
    }

    @-webkit-keyframes rainbowanim {
        0% {
            background-position: 0% 50%;
        }
        50% {
            background-position: 100% 50%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
    @-moz-keyframes rainbowanim {
        0% {
            background-position: 0% 50%;
        }
        50% {
            background-position: 100% 50%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
    @keyframes rainbowanim {
        0% {
            background-position: 0% 50%;
        }
        50% {
            background-position: 100% 50%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
    .site {
        margin: 25px;
        border-style: solid;
        border-width: 5px;
        border-color: red;
        border-radius: 10px;
        padding: 10px;

        color: darkmagenta;
        background-color: lightblue;
    }
</style>

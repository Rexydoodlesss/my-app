<script lang="ts">
    import type { Todo } from "$lib/types";

    let tasks: Todo[] = [];
    let count = 0
    let color = "white";
    let color2 = "black";
    let colors = ["red", "orange", "yellow", "green", "blue"];
    let finished: string[] = [];
    let input = "";
    let randomized: string[] = [];
    let funnyrandom = "https://cultofthepartyparrot.com/parrots/parrot.gif";
    let parrots: string[] = ["bobrossparrot.gif", "portalparrot.gif", "pythonparrot.gif", "revertitparrot.gif", "rotatingparrot.gif", "ryangoslingparrot.gif", "schnitzelparrot.gif", "shipitparrot.gif", "shufflefurtherparrot.gif", "shufflepartyparrot.gif", "skiparrot.gif", "slomoparrot.gif", "sovjetparrot.gif", "stalkerparrot.gif", "standupparrot.gif", "tacoparrot.gif", "tripletsparrot.gif", "uparrowparrot.gif", "upvoteparrot.gif", "wave1parrot.gif", "wave2parrot.gif", "wave3parrot.gif", "wave4parrot.gif", "wave5parrot.gif", "wave6parrot.gif", "wave7parrot.gif", "wave8parrot.gif", "wave9parrot.gif", "chillparrot.gif", "coffeeparrot.gif", "cryptoparrot.gif", "dabparrot.gif", "darkbeerparrot.gif", "databaseparrot.gif", "deployparrot.gif", "dizzyparrot.gif", "docparrot.gif", "dreidelparrot.gif", "drupal_parrot.gif", "ethparrot.gif", "explodyparrot.gif", "fadingparrot.gif", "fidgetparrot.gif", "fiestaparrot.gif", "fixparrot.gif", "halalparrot.gif", "hamburgerparrot.gif", "harrypotterparrot.gif", "icecreamparrot.gif", "krakenparrot.gif", "loveparrot.gif", "luckyparrot.gif", "margaritaparrot.gif", "matrixparrot.gif", "mergedparrot.gif", "metalparrot.gif", "mongodbparrot.gif", "oldtimeyparrot.gif", "papalparrot.gif", "parrot.gif", "pear-parrots.gif", "pizzaparrot.gif", "asyncparrot.gif", "bananaparrot.gif", "blondesassyparrot.gif", "bluescluesparrot.gif",];
    function resetclick(){
        tasks.length = 0
        count == 0
    }
    function funnyfunction() {
        funnyrandom ="https://cultofthepartyparrot.com/parrots/" + parrots[Math.floor(Math.random() * parrots.length)];
        color = colors[Math.floor(Math.random() * colors.length)];
        color2 = colors[Math.floor(Math.random() * colors.length)];
        while (color == color2){
        color = colors[Math.floor(Math.random() * colors.length)];
        color2 = colors[Math.floor(Math.random() * colors.length)];}
        randomized.forEach((element) => {});
    }
    function handlefinish(taskToComplete: string) {
        count = count+1
        tasks.forEach((task) => {
            if ((task.task == taskToComplete)) {
                task.done = true;}});
        tasks = tasks}

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
                    ("0" + new Date().getDate()).slice(-2),});
            tasks = tasks;
            input = ""}}

   
if (tasks.length == 0){
tasks = JSON.parse(localStorage.getItem("tasks")||"");}
$: localStorage.setItem("tasks", JSON.stringify(tasks));
// count = localStorage.getItem("count")||"";
// localStorage.setItem("count", (count));
</script>

<title>Unimportant Title Lmao</title>
<div class="site">
    <h1><img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"/>Rex's Scuffed To Do List!<img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"/></h1><br/>
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
        <button style="background-color: {color2}; color: {color}" class="task" on:click={() => handlefinish(task.task)}
            >{task.task}</button><br>
        {/if}
    {/each}
    {#if count == tasks.length}
    <p><i>you have no tasks lol which either means your the most productive person in the world, or so lazy as to not even manage your todo list</i></p>
    {/if}
    <h1><img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot">Completed Tasks!<img style="height: 40px;" src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></h1>
    <br>
    {#each tasks as task}
        {#if task.done == true}
        <h4 style="font-size: 50px;">"{task.task}" is done! <img src={`https://cultofthepartyparrot.com/parrots/${task.parrotpath}`} alt = "partyparrot"/></h4>
        <p>Started on {task.date}</p>
        {/if}
    {/each}
    {#if count == 0}
        <p>get to work idiot</p>
    {/if}
    <button on:click = {resetclick}>Reset All Tasks <img src="https://cultofthepartyparrot.com/parrots/parrot.gif" alt="partyparrot"></button> <br><br><br><br>
	<button on:click = {funnyfunction}>Need to destress? Click here! <img src="{funnyrandom}" alt="woulda been a random partyparrot"></button>
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
    @-moz-keyframes rainbowanim {0% {background-position: 0% 50%;}50% {background-position: 100% 50%;}100% {background-position: 0% 50%;}}
    @keyframes rainbowanim {0% {background-position: 0% 50%;}50% {background-position: 100% 50%;}100% {background-position: 0% 50%;}}
    .site {
        margin: 25px;
        border-style: solid;
        border-width: 5px;
        border-color: red;
        border-radius: 10px;
        padding: 10px;
        color: darkmagenta;
        background-color: lightblue;}</style>
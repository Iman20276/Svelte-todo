<script>
	
	let taskLists = ["Get up", "Take a bath", "Breafast"];
	let inputTask = "";

	const submitTask = () => {
		if (taskLists.includes(inputTask)) return;
		taskLists.push(inputTask);
		taskLists = taskLists;
		inputTask = "";
	}
	const deleteTask = (task) => {
		taskLists = taskLists.filter(item => item !== task)
	}

</script>

<main>
	<div>
		<div>
			<label>Input Task :</label>
			<input type="text" bind:value={inputTask}>
		</div>
		<button on:click={() => submitTask()}>Submit</button>
	</div>
	<div class="taskList">
		<ol>
			{#each taskLists as taskList}
			<li>{(taskList)} 
				<span 
					on:click={() => deleteTask(taskList)}>
					x
				</span></li>
			{/each}
		</ol>
	</div>
</main>

<style>
	main {
		width: 70%;
		margin: 30px auto;
		display: flex;
		align-items: center;
		flex-direction: column;
	}
	input[type=text] {
		border: none;
		border-bottom: 2px solid grey;
		width: 100%;
		padding: 5px 2px;
		margin: 8px 0;
		box-sizing: border-box;
	}
	button {
		background-color: #04AA6D;
		border: none;
		color: white;
		padding: 8px 14px;
		margin: 4px 2px;
		cursor: pointer;
		width: 100%;
	}
	button:hover {
		background-color: green;
	}
	ol li {
		padding: 5px;
		display: flex;
		align-items: flex-start;
		justify-content: space-between;
	}
	span {
		margin-left: 30px;
		color: red;
		cursor: pointer;
	}

</style>
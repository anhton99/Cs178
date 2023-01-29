<!-- #Component ; in the form of <component_name>, helps with reusability and modularity -->
<script>
	let todos = [];
	function addTodo() {
		todos = [...todos, ''];
	}
	function remove(index){
		todos = [...todos.slice(0, index), ...todos.slice(index+1)];
	}
</script>

<!-- #loop ; iterate through items -->
{#each todos as todo, index}

<!-- #Component directive ; specify component's behavior -->
<input bind:value={todos[index]}>
<!-- #Element directive ; specify element's behavior -->
<button on:click={() =>
	remove(index)}>X
</button>
<br>
{/each}

<!-- #Element directive ; specify element's behavior -->
<button on:click={addTodo}>Add</button>

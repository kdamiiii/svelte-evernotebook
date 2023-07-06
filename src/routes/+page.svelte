<script>
	$: tabWidth = 200;
	$: notesTabFlex = `${tabWidth}px`;

	const handleDragEnd = (e) => {
		tabWidth = e.clientX;
	};

	const handleDrag = (e) => {
		console.log(e);
		tabWidth = e.clientX;
	};
</script>

<div class="container" style="--notes-tab-flex: {notesTabFlex}">
	<div class="notes-tab">
		<h1>Notes</h1>
		Hello World1
	</div>
	<div
		id="border"
		class="draggable"
		draggable="true"
		on:drag={handleDrag}
		on:dragend={handleDragEnd}
	>
		.
	</div>
	<div class="note-pad">Hello World 2</div>
</div>

<style>
	h1 {
		margin: 0;
	}
	.container {
		display: flex;
		flex-direction: row;
	}

	.notes-tab {
		flex-basis: var(--notes-tab-flex);
		flex-grow: 0;
		height: 100vh;
	}

	.draggable {
		height: 100vh;
		cursor: col-resize;
		content: '';
		background-color: lightgray;
	}

	.note-pad {
		flex-grow: 1;
		height: 100vh;
	}
</style>

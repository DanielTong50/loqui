<div class="main-content">
    <slot/>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');
	.main-content {
		font-family: "Inter", sans-serif;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		height: calc(0vh - 100px);
        padding: 50px;
	}
</style>
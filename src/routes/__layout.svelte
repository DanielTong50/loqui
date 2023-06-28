<div class="main-content">

	<!-- <img src="" alt="Splash Image" />
	<div class="button-description">
		<button>Press any key to get started!</button>
		<p>Brought to you by the UBC Geering-Up STEM Leadership Program</p>
	</div> -->
    <slot/>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

	.main-content {
		font-family: "Poppins", sans-serif;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		height: calc(0vh - 100px);
        padding: 50px;
	}
</style>
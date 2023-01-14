<div class="main-content">

	<!-- <img src="" alt="Splash Image" />
	<div class="button-description">
		<button>Press any key to get started!</button>
		<p>Brought to you by the UBC Geering-Up STEM Leadership Program</p>
	</div> -->
    <slot/>
</div>

<style>
	.main-content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		height: calc(0vh - 100px);
		font-family: 'Gill Sans', sans-serif;
        padding: 50px;
	}
</style>
<style>
	main {
	  text-align: center;
	  padding: 1em;
	  max-width: 240px;
	  margin: 0 auto;
	}
	@media (min-width: 640px) {
	  main {
		max-width: none;
	  }
	}

	h2 {
		color: #bdaad4;
		font-size: 4em;
		font-weight: 100;
	}
  </style>
  
  <script>
	import QuizArea from './QuizArea.svelte';
	let playerScore = 0;
	let visible = true;
  </script>
  
  <main>
	<ul>
		<h2>Music Trivia!</h2>
	</ul>

	{#if visible}
	  <p style="color: white; font-size: 24px">
		Score:
		<i>{playerScore} / 10</i>
	  </p>
	{/if}
  
	<QuizArea
	  on:score={e => {
		playerScore = e.detail.score;
	  }}
	  on:resultsScreen={e => {
		visible = e.detail.showScore;
	  }} />
  
  </main>

<script>
  import {FeedbackStore} from '../stores'

  $: count = $FeedbackStore.length
	$: average = $FeedbackStore.reduce((a, {rating}) => a + rating, 0) / $FeedbackStore.length
</script>

<div class="feedback-stats">
  <h4>{count} Reviews</h4>
  <h4>Ratings Average: {average.toFixed(1)}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
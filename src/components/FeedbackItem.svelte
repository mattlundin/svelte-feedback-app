<script>
  import {FeedbackStore} from '../stores'
  import Card from './Card.svelte'
  export let item

  const handleDelete = (itemId) => {
    FeedbackStore.update((currentFeedback) => {
      return currentFeedback.filter(item => item.id != itemId)
    })
  }
</script>

<Card>
  <div class="num-display">
    {item.rating}
  </div>
  <button class="close" on:click={() => handleDelete(item.id)}>X</button>
  <p class="text-display">
    {item.text}
  </p>
</Card>

<style>
  .num-display {
    position: absolute;
    top: -10px;
    left: -10px;
    text-align: center;
    height: 50px;
    width: 50px;
    padding: 10px;
    background: #ff6a95;
    color: #fff;
    font-size: 19px;
    border-radius: 50%;
  }

  .close {
    position: absolute;
    top: 10px;
    right: 20px;
    background: none;
    border: none;
    cursor: pointer;
  }
</style>
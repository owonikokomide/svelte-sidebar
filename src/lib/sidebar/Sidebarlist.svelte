<script>
  export let title;
  export let icon;
import Icon from "@iconify/svelte";
</script>
 
<div class="container">
  <div class="list">
    <div class="icon-text">
      <Icon {icon} />
      <p>{title}</p>
    </div>
    <div class="arrow">
      <!-- <Icon icon="mdi-light:down" /> -->
      <svg style="color:white" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="m7 10l5 5l5-5z"/></svg>
    </div>
  </div>
</div>


<style>
  .list{
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .list:hover{
    background-color:rgb(152, 158, 163);
    color: #1C2833;
    cursor: pointer;
    border-radius: 0.4rem;
  }
  .icon-text{
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

</style>

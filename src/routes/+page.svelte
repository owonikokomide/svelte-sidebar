<script>
import Sidebar from "$lib/sidebar/sidebars.svelte";
import Dashboard from "$lib/Dashboard/dashboard.svelte"
</script>
  


<div class="continer">
  <div class="board">
    <div class="sidebar">
      <Sidebar />
    </div>
    <div class="dashboard">
     <Dashboard />
    </div>
  </div>
</div>


<style>
 .board{
  display: flex;
  height: 97vh;
  padding: 0.3rem 0.3rem;
 }
 .sidebar{
  color: antiquewhite;
  width: 14vw;
  max-width: 30%;
  border: 1px solid black;
  background-color: #072541;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 0.1rem;
  font-size: 0.9rem;
 }
 .dashboard{
  flex: 1;
  border: 1px solid black;

 }
</style>




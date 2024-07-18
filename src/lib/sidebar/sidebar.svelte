<script>
// import Logo from "../../img/logo.png"
import Sidebarlist from '$lib/sidebar/Sidebarlist.svelte';
import Icon from "@iconify/svelte";

    import { onMount } from 'svelte'  
    
    let dropdownVisible = false;

    // Function to toggle dropdown visibility
    function toggleDropdown() {
        dropdownVisible = !dropdownVisible;
    }

     // Close dropdown when clicking outside of it
    function handleClickOutside(event) {
        const dropdown = document.querySelector('.dropdown');
        if (dropdown && !dropdown.contains(event.target)) {
            dropdownVisible = false;
        }
    }

    // Close dropdown on component mount
    onMount(() => {
        document.addEventListener('click', handleClickOutside);
        
        return () => {
            document.removeEventListener('click', handleClickOutside);
        };
    });

   // Create a new Date object
    let date = new Date();

    // Function to format the date as "dd/mm/yyyy"
    function formatDate(date) {
        let day = String(date.getDate()).padStart(2, '0');
        let month = String(date.getMonth() + 1).padStart(2, '0'); // Months are zero-indexed
        let year = date.getFullYear();

        return `${day}/${month}/${year}`;
    }

    // Function to format the time as "HH:MM:SS"
    function formatTime(date) {
        let hours = String(date.getHours()).padStart(2, '0');
        let minutes = String(date.getMinutes()).padStart(2, '0');
        let seconds = String(date.getSeconds()).padStart(2, '0');

        return `${hours}:${minutes}:${seconds}`;
    }

    // Convert the date and time to strings
    let dateString = formatDate(date);
    let timeString = formatTime(date);
</script>

<div class="sidebar-card">
  <div class="top-bar">
    <div class="top-container">
      <div class="logo">
        <center><h1>Logo</h1></center>
      </div>
      <div class="all-dash">
      <div class="dashs">
        <div class="icon-dash">
          <Icon icon="material-symbols-light:home-outline" />
        </div>
        <div class="icon-text-dash">
          Dashboard
        </div>
      </div>
      <div class="list">
       <!-- <Sidebarlist title="Dashboard" icon="material-symbols-light:home-outline"  /> -->
       <Sidebarlist title="Deposit Operation" icon="tabler:circle-plus-2"  />
       <Sidebarlist title="Withdrawal Request" icon="tabler:octagon-minus"   />
       <Sidebarlist title="Account Handling" icon="ri:menu-fold-2-line"  />
       <Sidebarlist title="Depositor Control" icon="ri:user-add-line" />
       <Sidebarlist title="Automated Action" icon="tabler:wave-triangle" />
       <Sidebarlist title="System Report"  icon="tabler:report"/>
       <Sidebarlist title="Account Report"  icon="carbon:report-data"/>
       <Sidebarlist title="Timeline Report" icon="fluent-mdl2:report-warning" />
       <Sidebarlist title="Operator Handling" icon="game-icons:ping-pong-bat" />
       <Sidebarlist title="Bridge Settng" icon="icon-park-outline:bridge-one" />
      </div>
      </div>
    </div>
  </div>
  <div class="bottom-bar">
    <div class="down">
      <div class="date">
        {dateString} {timeString}
      </div>
      <div class="down-icons">
       <div class="all-icons">
        <Icon style="background-color:#0066CC; color:white; padding:0.4rem" icon="f7:square-grid-2x2" />
        <Icon style="background-color:#0066CC; color:white; padding:0.4rem" icon="mdi:notification-settings-outline" />
        <Icon style="background-color:#0066CC; color:white; padding:0.4rem" icon="solar:moon-outline" />
        <Icon style="background-color:#0066CC; color:white; padding:0.4rem" icon="mdi-light:lock" />
        <Icon style="background-color:#0066CC; color:white; padding:0.4rem" icon="zondicons:search" />
       </div>
      </div>
    </div>
  </div>
</div>


<style>
.sidebar-card{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 94vh;
  color: aliceblue;
  padding: 0.5rem 0.5rem 0.5rem 0.5rem;
}
.top-bar{
  /* display: flex; */
  justify-content: flex-start;
}
.dashs{
  display: flex;
  gap: 0.4rem;
  align-items: center;
  margin-top: 0.5rem;
  padding: 0.4rem 0 ;
}
.dashs:hover{
  background-color:rgb(152, 158, 163) ;
    color: #1C2833;
    cursor: pointer;
    border-radius: 0.4rem;
}
.bottom-bar{
  /* display: flex; */
  align-items: flex-end;
  justify-content: flex-end;
}

.list{
  font-size: 0.8rem;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 0.4rem;
}
.date{
  color: #0066CC;
  padding: 0.4rem;
  border: 1px solid #0066CC;
  text-align: center;
}
.down{
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.all-icons{
  display: flex;
  justify-content: space-between;
}
.all-dash{
  line-height: 0.3rem;
}

</style>
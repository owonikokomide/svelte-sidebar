<script>

import Icon from "@iconify/svelte";

    let activeItem = null;

    function toggleDropdown(item) {
        activeItem = activeItem === item ? null : item;
    }

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



<div class="sidebar">
  <div class="logo">
    <h1>Logo</h1>
  </div>
  <div class="wrap-all">
  <div class="up-side">
  <div class="wrap-side">
    <div class="icon-side">
      <Icon style="font-size:1rem" icon="mdi:home-outline" />
    </div>
    <div class="sidebar-item" on:click={() => toggleDropdown('dashboard')}>Dashboard</div>
    </div>
    <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
      <Icon style="font-size:1rem" icon="tabler:circle-plus-2" />
        <div class="sidebar-item" on:click={() => toggleDropdown('operations')}>Deposit Operation</div>
       </div> 
       <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>  
      </div>
      <div class="all">
    <div class={`dropdown ${activeItem === 'operations' ? 'active' : ''}`}>
        <div class="sidebar-item small">Deposit</div>
        <div class="sidebar-item small">Withdraw</div>
    </div>
    </div>
    </div>
    <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="tabler:octagon-minus" />
    <div class="sidebar-item" on:click={() => toggleDropdown('requests')}>Withdrawal Request</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'requests' ? 'active' : ''}`}>
        <div class="sidebar-item small">Pending</div>
        <div class="sidebar-item small">Approved</div>
    </div>
    </div>
    </div>
    <!-- Add more sidebar items as needed -->
        <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="ri:menu-fold-2-line" />
    <div class="sidebar-item" on:click={() => toggleDropdown('account')}>Account Handling</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'account' ? 'active' : ''}`}>
        <div class="sidebar-item small">Opening</div>
        <div class="sidebar-item small">Closing</div>
    </div>
    </div>
    </div>
    <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="ri:user-add-line" />
    <div class="sidebar-item" on:click={() => toggleDropdown('deposit')}>Depositor Control</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'deposit' ? 'active' : ''}`}>
        <div class="sidebar-item small">Deposit</div>
        <div class="sidebar-item small">Edit Deposit</div>
    </div>
    </div>
    </div>
    <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="tabler:wave-triangle" />
    <div class="sidebar-item" on:click={() => toggleDropdown('action')}>Automated Action</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'action' ? 'active' : ''}`}>
        <div class="sidebar-item small">Edit Action</div>
        <div class="sidebar-item small">Automated List</div>
    </div>
    </div>
    </div>
    <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="tabler:report" />
    <div class="sidebar-item" on:click={() => toggleDropdown('system')}>System Report</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'system' ? 'active' : ''}`}>
        <div class="sidebar-item small">Edit Report</div>
        <div class="sidebar-item small"> List</div>
    </div>
    </div>
    </div>
    <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="carbon:report-data" />
    <div class="sidebar-item" on:click={() => toggleDropdown('accounts')}>Account Report</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'accounts' ? 'active' : ''}`}>
        <div class="sidebar-item small">Edit Account</div>
        <div class="sidebar-item small"> Account List</div>
    </div>
    </div>
    </div>
    <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="fluent-mdl2:report-warning" />
    <div class="sidebar-item" on:click={() => toggleDropdown('timeline')}>Timeline Report</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'timeline' ? 'active' : ''}`}>
        <div class="sidebar-item small">Edit Timeline</div>
        <div class="sidebar-item small"> Timeline List</div>
    </div>
    </div>
    </div>
     <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="game-icons:ping-pong-bat" />
    <div class="sidebar-item" on:click={() => toggleDropdown('operator')}>Operator Handling</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'operator' ? 'active' : ''}`}>
        <div class="sidebar-item small">Handling</div>
        <div class="sidebar-item small"> Operator List</div>
    </div>
    </div>
    </div>
         <div class="wrap-sides">
      <div class="icon-side">
        <div class="both">
       <Icon icon="icon-park-outline:bridge-one" />
    <div class="sidebar-item" on:click={() => toggleDropdown('bridge')}>Bridge Setting</div>
   </div>
   <div class="iconify">
        <Icon icon="ep:arrow-down" />
       </div>
  </div>
    <div class="all">
    <div class={`dropdown ${activeItem === 'bridge' ? 'active' : ''}`}>
        <div class="sidebar-item small">Setting</div>
        <div class="sidebar-item small"> Add Bridge List</div>
    </div>
    </div>
    </div>
    </div>
    <div class="down-side">
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
</div>



<style>

  .sidebar{
    padding: 0.5rem;
  }
    .small{
      font-size: 0.8rem;
    }
    
    .sidebar-item {
        cursor: pointer;
        padding: 10px 15px;
        margin: 5px 0;
    }
    /* .sidebar-item:hover {
        background-color: #7a7d85;
    } */
    .dropdown {
        display: none;
        margin-left: 20px;
    }
    .dropdown.active {
        display: block;
    }
    .wrap-side{
      display: flex;
      align-items: center;
    }
    .icon-side:hover{
      background-color:rgb(152, 158, 163) ;
    color: #1C2833;
    cursor: pointer;
    border-radius: 0.4rem;
    }
  
    .logo{
      display: flex;
      justify-content: center;
    }
    .both{
      display: flex;
      align-items: center;
    }
    .icon-side{
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .wrap-all{
      height: 90vh;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .up-side{
      margin-top: 2rem;
    }
    .date{
  color: #0066CC;
  padding: 0.6rem;
  border: 1px solid #0066CC;
  text-align: center;
}
.down{
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  padding: 0.7rem;
}
.all-icons{
  display: flex;
  justify-content: space-between;
}
.sidebar-item:hover{
  color: #1C2833;
  background-color: rgb(152, 158, 163);
  border-radius: 0.5rem;
}
.wrap-side:hover{
  color: #1C2833;
  background-color: rgb(152, 158, 163);
  border-radius: 0.5rem;
}
</style>
<script>
    import supabase from '$lib/db';
import { each, object_without_properties } from 'svelte/internal';

    async function logout() {
   	 const { error } = await supabase.auth.signOut();

   	 if (error) alert(error.message); // alert if error
    }





    let timetable = {
	Monday: [
  	{
    	name: "PH",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BI",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "R",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
	],
	Tuesday: [
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BI",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "E",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
	],
	Wednesday: [
  	{
    	name: "BC",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "H",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "PKS",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
	],
	Thursday: [
  	{
    	name: "SA",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "A",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
	],
	Friday: [
  	{
    	name: "BI",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "T",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "SA",
    	period: 2,
    	style: "",
  	},
	],
  };
</script>
<!-- Sign Out -->
<div class="container">
    <h1>MY DASHBOARD</h1>
<section class="container px-4 py-3 text-center">
    <button class="btn btn-secondary" on:click={logout}>Logout</button>
</section>

<table class="table table-striped text-center table-bordered">
    <thead class="table-dark">
      <tr>
        <th scope="col ">#</th>
        <th scope="col">1</th>
        <th scope="col">2</th>
        <th scope="col">3</th>
        <th scope="col">4</th>
        <th scope="col">-</th>
        <th scope="col">5</th>
        <th scope="col">6</th>
        <th scope="col">7</th>
        <th scope="col">8</th>
        <th scope="col">9</th>
        <th scope="col">10</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row" class="table-dark">Monday</th>
       {#each timetable.Monday as timeSlot }
         <td colspan= {timeSlot.period} class= {timeSlot.style}>
          <button class= "btn" type="button">
            {timeSlot.name}
          </button>
         </td>
       {/each} 
      </tr>

      <tr>
      <th scope="row" class="table-dark">Tuesday</th>
      {#each timetable.Tuesday as timeSlot }
         <td colspan= {timeSlot.period} class= {timeSlot.style}>
          <button class= "btn" type="button">
            {timeSlot.name}
          </button>
         </td>
       {/each}
      </tr>

      <tr>
      <th scope="row" class="table-dark">Wednesday</th>
      {#each timetable.Wednesday as timeSlot }
         <td colspan= {timeSlot.period} class= {timeSlot.style}>
          <button class= "btn" type="button">
            {timeSlot.name}
          </button>
         </td>
       {/each}
         
      </tr>

      <tr>
        <th scope="row" class="table-dark">Thursday</th>
        {#each timetable.Thursday as timeSlot }
         <td colspan= {timeSlot.period} class= {timeSlot.style}>
          <button class= "btn" type="button">
            {timeSlot.name}
          </button>
         </td>
       {/each}
      </tr>

      <tr>
        <th scope="row" class="table-dark">Friday</th>
        {#each timetable.Friday as timeSlot }
         <td colspan= {timeSlot.period} class= {timeSlot.style}>
          <button class= "btn" type="button">
            {timeSlot.name}
          </button>
         </td>
       {/each}
        
      </tr>

    </tbody>
  </table>
</div>


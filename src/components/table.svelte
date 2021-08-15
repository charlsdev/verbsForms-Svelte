<script>
	export let listVerbs = [];
   // console.log( listVerbs);

   const settings = { columnFilter: true }
</script>

<div class="container p-30">
   <div class="row">
      <div class="col-md-12 main-datatable">
         <div class="card_body">
            <div class="row d-flex">
                  <div class="col-sm-12 add_flex">
                     <div class="form-group searchInput">
                        <label for="email">Buscar:</label>
                        <input type="search" class="form-control" id="filterbox" placeholder=" ">
                     </div>
                  </div> 
            </div>

            <div class="overflow-x">
               <table style="width:100%;" id="filtertable" class="table cust-datatable dataTable no-footer" settings={settings} data={listVerbs}>
                  <thead>
                     <tr>
                        <th style="min-width:25px;">ID</th>
                        <th style="min-width:50px;">Tipo</th>
                        <th style="min-width:150px;">Simple Form</th>
                        <th style="min-width:100px;">Third Person</th>
                        <th style="min-width:100px;">Simple Past</th>
                        <th style="min-width:150px;">Past Participle</th>
                        <th style="min-width:150px;">Gerund</th>
                        <th style="min-width:150px;">Meaning</th>
                     </tr>
                  </thead>
                  <tbody>
                     {#each listVerbs as list, i}
                        <tr>
                           <td>{ i + 1 }</td>
                           <td><span class="mode mode_on">{ list.type }</span></td>
                           <td>{ list.simpleForm }</td>
                           <td>{ list.thirdPerson }</td>
                           <td>{ list.simplePast }</td>
                           <td>{ list.pastParticiple }</td>
                           <td>{ list.gerund }</td>
                           <td>{ list.meaning }</td>
                        </tr>
                     {/each}

                     <!-- <tr>
                        <td>Dummy</td>
                        <td>Dummy</td>
                        <td>asfdsafasd</td>
                        <td>Journey</td>
                        <td>17-Apr-2020</td>
                        <td><span class="mode mode_on">Active</span></td>
                        <td><span class="mode mode_on">Active</span></td>
                        <td><span class="mode mode_on">Active</span></td>
                     </tr>
                     <tr>
                        <td>Dummy</td>
                        <td>Dummy</td>
                        <td>sdfsafsadf</td>
                        <td>Journey</td>
                        <td>17-Apr-2020</td>
                        <td><span class="mode mode_on">Active</span></td>
                        <td><span class="mode mode_on">Active</span></td>
                        <td><span class="mode mode_on">Active</span></td>
                     </tr> -->

                  </tbody>
               </table>
            </div>
         </div>
      </div>
   </div>
</div>

<svelte:head>
	<script src="./libs/dataTables/configDataTables.min.js"></script>
</svelte:head>
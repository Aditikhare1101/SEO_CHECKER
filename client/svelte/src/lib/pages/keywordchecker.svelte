<script>

  import {Router ,Route ,Link } from "svelte-navigator";
  import axios from 'axios';
  let url="";
  let keyword="";
  let visible = false;
  
 let keywrdData ={};
          
	async function getData() {
		try {
	    const response = await axios.post('http://localhost:5000/api/keyword', {
		  // Data to be sent to the server
		  URL: url,
		  KEYWORD : keyword
	  });
	  //console.log(response.data);
  keywrdData = response.data;
    console.log(keywrdData)
    
    console.log(keywrdData.count)




    } catch (error) {
	    console.error(error);
    }

    visible = !visible
	}
</script>

<Route>
  <!-- Start the section of Enter url for SEO checker. -->
  <div class="container urlPicker">
    <div class="text-center">
      <p class="text-dark fs-1 text-center">Keyword optimization with Keyword Checker</p>
      <label for="Picker" class="form-label text-dark">Enter url : </label>
      <input type="url" placeholder="URL" bind:value={url} required />
      <br>
      <br>
      <label for="Picker" class="form-label text-dark">Keyword : </label>
      <input type="st" placeholder="keyword" bind:value={keyword} required />
      <br />
      <button class="btn btn-primary mt-3" on:click={getData} >Submit</button>
    </div>
  </div>
<!-- End the section of Enter the url for SEO checker. -->


</Route>

<!--The Result start -->

{#if visible}
<div class="container urlresult" >

    <h1 class="text-dark fs-1 text-center">Here are some results...</h1> 

    <div class="container" style="padding-bottom: 50px;">
      <div class="row">
        <div class="col-sm text-center">
          <div class="card" >
            <div class="card-body">
              <h2 class="card-title">KEYWORD COUNT</h2>
              <h4>{keywrdData.count}</h4>
            </div>
          </div>
        </div>
        <div class="col-sm text-center">
          <div class="card" >
            <div class="card-body">
              <h2 class="card-title">KEYWORD DENSITY</h2>
              <h4>{keywrdData.density}</h4>
    
            </div>
          </div>
        </div>
      </div>
    </div>




  </div>
{/if}


<style>
  
.urlPicker {
margin-top: 100px;
margin-bottom: 100px;
padding-top: 50px;
padding-bottom: 50px;
background: #f4fbfe;
border-radius: 10px;
font-family: "Dosis", sans-serif;
text-align: center;
}

.btn {
font-family: "Dosis", sans-serif;
font-weight: 500;
font-size: 16px;
letter-spacing: 1px;
display: inline-block;
padding: 8px 28px;
border-radius: 3px;
transition: 0.5s;
margin-top: 25px;
color: #fff;
background: #49b5e7;
text-transform: uppercase;
}

.btn:hover {
background: #76c7ed;
}

.urlPicker:hover {
font-size: large;
}

.urlresult {

background: #f4fbfe;
border-radius: 10px;
font-family: "Dosis", sans-serif;
height: fit-content;
}

</style>

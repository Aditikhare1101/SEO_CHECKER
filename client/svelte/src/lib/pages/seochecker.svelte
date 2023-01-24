<script>
    import {Router ,Route ,Link } from "svelte-navigator";
    import axios from 'axios';
  
    let url="";
    let visible = false;
    let output = {
  metaInfo: {},
  internalLinks: [],
  externalLinks: [],
  href: 0,
  structure: 0,
  design: 0
};

    async function myfun() {

      
      try {
	      const response = await axios.post('http://localhost:5000/api', {
		  // Data to be sent to the server
		    URL: url
	    });
	    //console.log(output);
	    

	    output=response.data;
      

      } catch (error) {
	      console.error(error);
      }
      visible = !visible
  } 

let m="<";
let n = ">"

</script>
<Route>



  		<!-- Start the section of Enter url for SEO checker. -->
      <div class="container urlPicker">
        <div class="text-center">
          <h2 class="text-dark fs-1 text-center">Test your Website with SEO checker..........!</h2>
          <label for="Picker" class="form-label text-dark">Enter url : </label>
          <input type="url"  placeholder="URL" bind:value={url} required />
          <br />
          <button class="btn btn-primary mt-3" on:click={myfun}>Submit</button>
        </div>
      </div>
    <!-- End the section of Enter the url for SEO checker. -->
  
</Route>

<!--The Result start -->


{#if visible}
<div class="container urlresult" >

    <h1 class="text-dark fs-1 text-center">Here are some results...</h1>

     
      <h2>Meta Information:</h2>
      <h3>Title:</h3>
      {#if output.metaInfo.title !== undefined && output.metaInfo.title !== null}
        <p>{output.metaInfo.title}</p>
      {:else}
        <p>You need to add this section in your website.</p>
      {/if}

      
      <h3>Here are total {output.structure} {m}p{n} or {m}br{n} tags used.</h3>
      <br>
      <h3>Here are total {output.design} {m}div{n} tags used.</h3>
      <br>

      <h3>Meta Description :</h3>
      {#if output.metaInfo.description !== undefined && output.metaInfo.description !== null}
        <p>{output.metaInfo.description}</p>
      {:else}
        <p>You need to add this section in your website.</p>
      {/if}

      <h3>Main Keywords:</h3>
      {#if output.metaInfo.keyworsd !== undefined && output.metaInfo.keyword !== null}
        <p>{output.metaInfo.keywords}</p>
      {:else}
        <p>You need to add this section in your website.</p>
      {/if}


      <h3>Open Graph Information:</h3>
  
      <h5>OG Title:</h5>
      {#if output.metaInfo.og_title !== undefined && output.metaInfo.og_title !== null}
        <p>{output.metaInfo.og_title}</p>
      {:else}
        <p>You need to add this section in your website.</p>
      {/if}

      <h5>OG url:</h5>
      {#if output.metaInfo.og_url !== undefined && output.metaInfo.og_url !== null}
        <p>{output.metaInfo.og_url}</p>
      {:else}
        <p>You need to add this section in your website.</p>
      {/if}

      <h5>OG Image:</h5>
      {#if output.metaInfo.og_img !== undefined && output.metaInfo.og_img !== null}
        <p>{output.metaInfo.og_img}</p>
      {:else}
        <p>You need to add this section in your website.</p>
      {/if}

      <h5>OG Type:</h5>
      {#if output.metaInfo.og_type !== undefined && output.metaInfo.og_type !== null}
        <p>{output.metaInfo.og_type}</p>

      {:else}
        <p>You need to add this section in your website.</p>
      {/if}

      <h5>OG Tag:</h5>
      {#if output.metaInfo.og_tag !== undefined && output.metaInfo.og_tag !== null}
        <p>{output.metaInfo.og_tag}</p> 

      {:else}
        <p>You need to add this section in your website.</p>
      {/if}

    <div>
      <h2>Link Structure:</h2>
      <br>
      <h3>There are total {output.href} links are present.</h3>
      <br>
      <h3>Internal Links:</h3>
      {#each output.internalLinks as link}
         <a href={link}>{link}</a>
         <br>
      {/each}

      <h3>External Links:</h3>
      {#each output.externalLinks as link}
         <a href={link}>{link}</a>
         <br>
      {/each}
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

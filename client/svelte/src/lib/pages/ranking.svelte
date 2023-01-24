<script>
  import {Router ,Route ,Link } from "svelte-navigator";
  let url="";
  let keyword="";
</script>

<Route>
  <!-- Start the section of Enter url for SEO checker. -->
  <div class="container urlPicker">
    <div class="text-center">
      <p class="text-dark fs-1 text-center">Create perfect content using the TF*IDF tool!</p>
      <label for="Picker" class="form-label text-dark">Enter url : </label>
      <input type="url" placeholder="URL" bind:value={url} required />
      <br> 
      <br>
      <label for="Picker" class="form-label text-dark">Keyword : </label>
      <input type="st" placeholder="(OPTIONAL)" bind:value={keyword} required />

      <br />
      <button class="btn btn-primary mt-3" >Submit</button>
    </div>
  </div>
<!-- End the section of Enter the url for SEO checker. -->
</Route>

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

</style>

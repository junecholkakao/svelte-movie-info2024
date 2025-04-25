<script>
    let searchText=''

    let alertText=""

    $:if (searchText.length > 16) alertText="입력한도 초과" 
      else alertText=""
</script>



<div class="search-box">
    <div class="input-group" >
        <input type="search" bind:value={searchText}>
        <button>검색</button>
    </div>
    <p class="text-center">현재 입력값: {searchText}</p>
    <p class='text-center alert-text'>{alertText}</p>

</div>


<style>
  .text-center {
    text-align:center;
  }

  .alert-text {
    color: red;
  }

    .search-box {
      padding: 0 20px;
      margin-top: 20px;

    }
  
    .input-group {
      width: 100%;
      border: 1px solid #ccc;
      position: relative;
      padding: 0 20px;
      margin-bottom: 20px;
    }
  
    .search-box input {
      width: 100%;
      border: none;
      outline: none;
      padding: 10px;
    }
  
    .search-box button {
      position: absolute;
      right: 0;
      top: 0;
      border: none;
      outline: none;
      background: #666;
      color: #fff;
      width: 5em;
      height: 100%;
      margin: 0;
    }
  </style>
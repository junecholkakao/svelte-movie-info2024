<script>
  // import { movies_data } from "../movie_data";
  export let movies_data =[]
  export let setSelectedMovie
  export let openModal
</script>

<main class="container">
  <h1>영화정보</h1>
  {#each movies_data as movie, i}
  <div class="item">
    <div class="image">
      <img src={movie.imgUrl} alt="" />
    </div>
    <div class="info">
      <h3 class="bg-yellow">{movie.title}</h3>
      <h3>{movie.title}</h3>
      <p>개봉: {movie.year}</p>
      <p>장르: {movie.category}</p>
      <button on:click={()=>{
        movie.likeCount+=1
        }}>좋아요 {movie.likeCount}</button>
      <button 
        on:click={()=>{
          setSelectedMovie(movie)
          openModal()
        }}
        class="btn btn-primary">상세보기</button>
    </div>
  </div>
  {/each} 
</main>

<style>
  .bg-yellow {
    background: gold;
    padding: 10px;
    color: #333;
  }
  .item {
    width: 100%;
    border: 1px solid #ddd;
    display: flex;
    margin-bottom: 20px;
    padding: 1rem;
  }
  .item .image {
    width: 30%;
    margin-right: 1rem;
  }

  .item img {
    width: 100%;
  }
  .item .info {
    width: 100%;
  }


</style>
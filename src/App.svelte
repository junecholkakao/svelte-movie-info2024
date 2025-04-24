<script>
  import { movies_data } from "./lib/movie_data";
  import Navbar from "./lib/components/Navbar.svelte";
  import Modal
   from "./lib/components/Modal.svelte";
  import Movies from "./lib/components/Movies.svelte";
  let isModal = false
  let selectedMovie

  const closeModal = () => {
    isModal = false
  }

  const openModal = () => {
    isModal = true
  }

  const setSelectedMovie = (movie) => {
    selectedMovie = movie
  }
</script>

<Navbar/>
<div class="event ">
  <p>NETFLIX 강렬한 운명의 드라마, 경기크리처</p>
  <button>X</button>
</div>
<Movies {setSelectedMovie} {openModal} {movies_data}/>

{#if isModal}
  <Modal {selectedMovie} {closeModal}/>
{/if}

<style>
 .event {
    width: 100%;
    background: #666;
    padding: 5px 1em;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #fff;
    text-align: center;
    margin-bottom: 1em;
    padding: 10px 20px;

    /* 창이 보이지 않게 */
    max-height: 0;
    opacity: 0;
    overflow: hidden;
    transition: all 0.4s;
  }

  /* 기본: 창이 보이게 */
  .show {
    opacity: 1;
    max-height: 100px;
  }

  .event button {
    padding: 2px;
  }

  .event p, .event button {
    margin: 0;
  }
  .event p {
    width: 100%;
  }
</style>

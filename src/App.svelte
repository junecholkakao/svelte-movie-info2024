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

  let isEvent = true

  import {fly, fade} from 'svelte/transition'
    import Events from "./lib/components/Events.svelte";
    import SearchBar from "./lib/components/SearchBar.svelte";
</script>

<Navbar/>
<Events/>

<SearchBar/>

<Movies {setSelectedMovie} {openModal} {movies_data}/>

{#if isModal}
  <Modal {selectedMovie} {closeModal}/>
{/if}



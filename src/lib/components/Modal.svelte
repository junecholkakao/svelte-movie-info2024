<script>
  // let {isModal, selectedMovie} = $props()
  export let selectedMovie
  export let closeModal
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div class="modal"
  on:click={closeModal}
  >
  <div class="inner">
    <h3>영화 상세정보</h3>
    <div class="item">
      <div class="image">
        <img src={selectedMovie?.imgUrl} alt="" />
      </div>
      <div class="info">
        <h3>{selectedMovie?.title}</h3>
        <p>개봉: {selectedMovie?.year}</p>
        <p>장르: {selectedMovie?.category}</p>
        <p>내용: {@html selectedMovie?.story}</p>
      </div>
    </div>
    <button 
      on:click={closeModal}
      class="btn-close">닫기</button>
  </div>
</div>

<style>
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
    .modal {
    background: rgba(0,0,0,0.7);
    position: fixed;
    left: 0;
    top:0;
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .modal .inner {
    background: #fff;
    width: 80%;
    padding: 20px;
    border-radius: 10px;
  }
</style>
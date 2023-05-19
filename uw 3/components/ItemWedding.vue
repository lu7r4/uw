<template>
    <div class="wrapper">

    <div class="flex-container">
      <div class="image-container">
        <img src="../assets/images/collection/collection_1.png" alt="collection_1" class="main-image">
      </div>
      <div class="text-container">
        <div class="title">Незабываемая <br> <span>и утончённая</span> свадебная <span>коллекция</span></div>
        <nuxt-link to="/example">
        <button>Перейти в каталог</button>
    </nuxt-link>
      </div>
      <div class="image-container">
        <img src="../assets/images/collection/collection_2.png" alt="collection_2" class="secondary-image">
      </div>
    </div>
</div>

  </template>

  <script>
  export default {
    name: 'ItemWedding'
  }
</script>
  
  <style scoped>

  .title {
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    font-size: 52px;
    color: #A3B18A;
    line-height: 62px;
    text-align: center;
  }
  .title span {
    color: #fff;
  }
  .wrapper {
    max-width: 1920px;
    width: 100%;
    margin: 100px auto;
    background-color: #11442A;
  }
  .flex-container {
    max-width: 1290px;
    width: 100%;

    margin: 0 auto;
    display: flex;
    height: 600px;
    background-color: #11442A;
  }
  
  .image-container {
    flex-grow: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .image-container:first-child img {
    width: 350px;
    height: 480px;
  }

  .image-container:last-child img {
    width: 500px;
    height: 700px;
  }
  .secondary-image {
    margin-top: -50px;
    margin-bottom: -50px;
    margin-right: -100px;
  }
  
  .text-container {
    padding: 0 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  button {
    margin-top: 47px;
    width: 350px;
    height: 61px;
    font-family: 'maximacyrtcy_lighcomp';
    color: #fff;
    text-transform: uppercase;
    font-size: 20px;
    letter-spacing: 0.025em;
    border: 1px solid #fff;
    background-color: transparent;
    cursor: pointer;
  }
  @media (max-width: 1366px) {
    .wrapper {
        max-width: 1366px;
    }
    .flex-container {
        width: 1280px;
    }
    .image-container:last-child img {
    width: 393px;
    height: 700px;
  }
    .secondary-image {
        margin-right: -50px;
        object-fit: cover;
    }
  }

  @media (min-width: 768px) and (max-width: 1365px) {
    .wrapper {
        min-width: 768px;
        max-width: 1365px;
        width: 100%;
    }
    .flex-container {
        width: 700px;
        
        gap: 20px;
    }
    .image-container:first-child {
        width: 340px;
    }
    .image-container:first-child img {
        width: 340px;
        object-fit: cover;

    }
    .image-container:last-child {
        display: none;
    }
    .text-container {
        padding-left: 0;
        padding-right: 0px;

    }
    .title {
        width: 340px;
    }
    button {
        width: 340px;
    }
  }
  @media (min-width: 360px) and (max-width: 767px) {
    .wrapper {
        min-width: 360px;
        max-width: 767px;
        width: 100%;
        height: 700px;
    }
    .flex-container {
        width: 360px;
        flex-direction: column;
        align-items: center;
        height: 700px;
        
    }
    .image-container:last-child {
        display: none;
    }
    .main-image {
        width: 360px;
    height: 480px;
    }
    .image-container:first-child img {
    width: 360px;
    height: 480px;
    object-fit: cover;
  }
  .text-container {
    width: 320px;
    height: 270px;

  }
  .title {
    width: 320px;
    font-size: 36px;
    line-height: 43px;
    letter-spacing: normal;
  }
  br {
    display: none;
  }
  button {
    width: 320px;
    margin-top: 20px;
  }
  }
  
  
  </style>
  
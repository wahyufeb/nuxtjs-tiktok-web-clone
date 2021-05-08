<template>
  <div class="search">
    <div class="searchInput">
      <input
        id="search"
        type="text"
        name="search"
        placeholder="Search accounts"
      />
      <span></span>
    </div>
    <button>
      <img src="~/assets/icons/search-icon.svg" alt="search icon" />
    </button>
  </div>
</template>

<script>
export default {
  name: 'NavbarSearch',
}
</script>

<style scoped>
.search {
  width: 100%;
  display: flex;
  justify-content: space-between;
  position: relative;
}

.searchInput {
  display: flex;
  justify-content: space-between;
}

.searchInput span {
  height: 30px;
  position: absolute;
  right: 36px;
  top: -7px;
  z-index: 3;
  border-left: 1px solid var(--silver-color);
}

.search button {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 43px;
  width: 50px;
  position: absolute;
  right: -14px;
  top: -14px;
  z-index: 2;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
}

.search button:focus,
.search button:hover {
  filter: brightness(0.95);
}

.search input {
  width: 280px;
  background-color: blue;
  border: none;
  background-color: transparent;
}

.search input::placeholder {
  font-size: 16px;
  font-family: 'ProximaLight';
}

.search input:focus {
  border: none !important;
  outline: none;
}
</style>

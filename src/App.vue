<script setup>
import { ref } from 'vue'

// This "holds" the text you type
const myText = ref('Initial Text');

// Function to handle the search
const handleSearch = () => {
  console.log("Soogle Search!")
}

// Function for the "I'm Feeling Lucky" button
const handleLucky = () => {
  console.log("Feeling lucky!")}
</script>

<template>
  <div class="google-home">
    <header class="nav-bar">
      <span>Gmail</span>
      <span>Images</span>
      <button class="apps-btn">⠿</button>
      <button class="profile-btn">G</button>
    </header>

    <main class="content">
      <h1 class="logo">
        <span class="blue">S</span><span class="red">o</span><span class="yellow">o</span><span class="blue">g</span><span class="green">l</span><span class="red">e</span>
      </h1>


      <div class="search-container">
        <div class="search-box">
          <span class="search-icon">+</span>
          <input 
            type="text" 
            v-model="searchQuery" 
            @keyup.enter="handleSearch"
            placeholder="Search Soogle or type a URL"
          />
        </div>

        <div class="button-group">
          <button @click="handleSearch">Soogle Search</button>
          <button @click="handleLucky">I'm Feeling Lucky</button>
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped>
/* Basic layout to center everything */
.google-home {
  font-family: Arial, sans-serif;
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.nav-bar {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 15px;
  gap: 15px;
  font-size: 13px;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 70px;
}

/* Logo Colors */
.logo { font-size: 70px; font-weight: 500; margin-bottom: 40px; letter-spacing: -3px; }
.blue { color: #4285F4; }
.red { color: #EA4335; }
.yellow { color: #FBBC05; }
.green { color: #34A853; }

/* Search Bar Styling */
.search-container { width: 100%; max-width: 584px; }

.search-box {
  display: flex;
  align-items: center;
  border: 1px solid #dfe1e5;
  border-radius: 24px;
  padding: 5px 15px;
  transition: box-shadow 0.2s;
}

.search-box:hover, .search-box:focus-within {
  box-shadow: 0 1px 6px rgba(32,33,36,.28);
  border-color: rgba(223,225,229,0);
}

input {
  flex: 1;
  border: none;
  height: 34px;
  font-size: 16px;
  outline: none;
  padding: 0 10px;
}

.button-group {
  margin-top: 25px;
  display: flex;
  justify-content: center;
  gap: 12px;
}

button {
  background: #f8f9fa;
  border: 1px solid #f8f9fa;
  border-radius: 4px;
  color: #3c4043;
  padding: 8px 16px;
  font-size: 14px;
  cursor: pointer;
}

button:hover {
  border: 1px solid #dadce0;
  box-shadow: 0 1px 1px rgba(0,0,0,0.1);
}
</style>
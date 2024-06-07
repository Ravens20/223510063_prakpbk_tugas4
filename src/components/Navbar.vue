<template>
    <nav>
      <ul>
        <li @click="navigate('Portfolio')">Home</li>
        <li @click="navigate('About')">About</li>
        <li @click="navigate('Projects')">Jadwal</li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    methods: {
      navigate(component) {
        this.$emit('navigate', component);
      },
    },
  };
  </script>
  
  <style>
  nav {
    background-color: #333;
    padding: 1rem 0;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  ul {
    list-style-type: none;
    display: flex;
    justify-content: center;
    margin: 0;
    padding: 0;
  }
  
  li {
    margin: 0 15px;
    color: white;
    cursor: pointer;
    font-size: 1.2em;
    transition: color 0.3s;
  }
  
  li:hover {
    color: #FFD700;
  }
  </style>
  
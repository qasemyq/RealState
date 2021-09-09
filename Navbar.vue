<template>
 <div>
  <b-navbar toggleable="lg" type="dark" variant="primary">
<div> 
  <b-img src="https://picsum.photos/1024/400/?image=41"  style="width: 150px; height: 50px;" fluid alt="Left image"></b-img>
</div>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item><router-link to="/about">Add Your Property</router-link> </b-nav-item>
 
      </b-navbar-nav> 

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
         
        <b-navbar-nav> 
          <b-nav-item href="#">Saved Property</b-nav-item>
        </b-navbar-nav>

        <b-navbar-nav>
          <b-nav-item href="#">Your Messages</b-nav-item>
        </b-navbar-nav>

        <b-navbar-nav>
          <b-button size="s" class="my-2 my-sm-0" type="submit">Subscription</b-button>
        </b-navbar-nav>

          <i class="fas fa-user fa-2x" style="color: lightgreen;"></i>
         <b-nav-item-dropdown text="Bob" right>
          <b-dropdown-item href="#">Your Profile</b-dropdown-item>
          <b-dropdown-item href="#">Your Subcribtion</b-dropdown-item>
          <b-dropdown-item href="#">RU</b-dropdown-item>
          <b-dropdown-item href="#">Log out</b-dropdown-item>
        </b-nav-item-dropdown>

      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>

<script setup>

</script>

<template>
  <nav class="navbar">
    <div class="navbar-left">
      <a href="#" class="logo">
        <img src="../assets/images/image (3).svg" alt="logo" />

      </a>
      <div class="country-selector">
        <img src="../assets/images/NigeriaFlag.svg" alt="NG" />
        <span>NG</span>
        <img src="../assets/images/image (5).svg" alt="dropdown" />
      </div>
    </div>

    <ul class="navbar-center ">
      <li class="products-dropdown">
        <a href="#">Products <img src="../assets/images/image (5).svg" alt="dropdown" /></a>
        <div class="dropdown-menu-products">
          <ul class="products-list">
            <li><a href="">Chowpass</a></li>
            <li><a href="">Relay</a></li>
          </ul>
        </div>
      </li>

      <li><a href="#">Company</a></li>
      <li><a href="#">FAQs</a></li>
      <li><a href="#">Blog</a></li>
      <li><a href="#">Contact</a></li>
    </ul>

    <div class="navbar-right">
      <div class="customers-dropdown">
        <a href="#">
          Customers <img src="../assets/images/image (5).svg" alt="dropdown" />
        </a>
        <div class="dropdown-menu">
          <ul>
            <li><a href="">Vendors</a></li>
            <li><a href="">Riders</a></li>
          </ul>

        </div>
      </div>
      <a href="#" class="cart-icon">
        <img src="../assets/images/image (7).svg" alt="Cart" />
      </a>
    </div>
  </nav>

</template>

<style scoped>
/* left part */
.logo {
  display: flex;
  align-items: center;
  background-color: #085012;
  padding: 8px 26px;
  border-radius: 26px;
}

.navbar-left {
  display: flex;
  gap: 20px;
}

.country-selector {
  background-color: white;
  padding: 8px 26px;
  border-radius: 26px;
  color: #085012;
}

/* central part */

.navbar-center {
  margin: 0px;
  padding: 0 20px;

  list-style: none;
  background-color: white;
  border-radius: 26px;
  display: flex;
  justify-content: space-between;
}

.navbar-center li {
  display: inline-block;
  position: relative;
}

.navbar-center li a {
  display: block;
  padding: 10px 16px;
}

.customers-dropdown:hover .dropdown-menu {
  display: block;
}

.products-dropdown {
  position: relative;
}

.products-dropdown:hover .dropdown-menu-products {
  display: block;
}



.dropdown-menu {
  display: none;
  position: absolute;
  top: 100%;
  right: 0;

  z-index: 1000;
  background-color: transparent;
  border: none;
}


.dropdown-menu ul {
  list-style: none;
  border-radius: 26px;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: flex-end;


}



.dropdown-menu ul li {
  display: inline-block;
  white-space: nowrap;
  padding: 8px 16px;
  background-color: white;
  border-radius: 26px;
  margin: 4px 0;
  border: 1px solid grey;
}



.customers-dropdown:hover .dropdown-menu {
  display: block;
}

/* right part */
.navbar-right {
  display: flex;
  gap: 10px;

}

.customers-dropdown {
  position: relative;
  background-color: white;
  padding: 8px 26px;
  border-radius: 26px;
}


.cart-icon {
  background-color: white;
  padding: 8px 8px;
  border-radius: 26px;
}


.dropdown-menu-products {
  display: none;
  position: absolute;
  top: 100%;
  right: 0;
  margin-top: 4px;
  z-index: 1000;
  background-color: transparent;
  border: none;
}


.dropdown-menu-products ul {
  list-style: none;
  border-radius: 26px;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: flex-end;


}

.dropdown-menu-products ul li {
  display: inline-block;
  white-space: nowrap;
  /* padding: 8px 16px; */
  background-color: white;
  border-radius: 26px;
  margin: 4px 0;
  border: 1px solid grey;
}
</style>

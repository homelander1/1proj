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
        <span> NG</span>
        <img src="../assets/images/image (5).svg" alt="dropdown" />
        <div class="dropdown-menu-lang">
          <ul class="products-list">
            <li><a href=""><img src="../assets/images/NigeriaFlag.svg" alt="NG" /> Ghana</a></li>
            <li><a href=""><img src="../assets/images/NigeriaFlag.svg" alt="NG" /> Nigeria</a></li>
          </ul>
        </div>
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
/* ─── Left Section ─── */
.navbar-left {
  display: flex;
  gap: 20px;
}

.logo {
  display: flex;
  align-items: center;
  background-color: #085012;
  padding: 8px 26px;
  border-radius: 26px;
}

.country-selector {
  position: relative;
  /* for its dropdown */
  cursor: pointer;
  /* indicates clickability */
  background-color: white;
  padding: 8px 26px;
  border-radius: 26px;
  color: #085012;
}

/* country-selector dropdown */
.country-selector:hover .dropdown-menu-lang {
  display: block;
}

.dropdown-menu-lang {
  display: none;
  position: absolute;
  top: 100%;
  right: 0;
  margin-top: 4px;
  z-index: 1000;
  background-color: transparent;
  border: none;
}

.dropdown-menu-lang .products-list {
  list-style: none;
  margin: 0;
  padding: 0;
  border-radius: 26px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.dropdown-menu-lang .products-list li {
  display: inline-block;
  white-space: nowrap;
  padding: 8px 26px;
  background-color: white;
  border: 1px solid grey;
  border-radius: 26px;
  margin: 4px 0;
}


/* ─── Center Section ─── */
.navbar-center {
  margin: 0;
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

/* products-dropdown */
.products-dropdown:hover .dropdown-menu-products {
  display: block;
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

.dropdown-menu-products .products-list {
  list-style: none;
  margin: 0;
  padding: 0;
  border-radius: 26px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.dropdown-menu-products .products-list li {
  display: inline-block;
  white-space: nowrap;
  /* padding: 8px 16px; */
  background-color: white;
  border: 1px solid grey;
  border-radius: 26px;
  margin: 4px 0;
}


/* ─── Right Section ─── */
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

.customers-dropdown:hover .dropdown-menu {
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
  margin: 0;
  padding: 0;
  border-radius: 26px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.dropdown-menu ul li {
  display: inline-block;
  white-space: nowrap;
  padding: 8px 16px;
  background-color: white;
  border: 1px solid grey;
  border-radius: 26px;
  margin: 4px 0;
}

.cart-icon {
  background-color: white;
  padding: 8px;
  border-radius: 26px;
}
</style>

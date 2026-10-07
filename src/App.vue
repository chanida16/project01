<template>
 <nav class="navbar navbar-expand-lg bg-primary-subtle">
  <div class="container">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavDropdown">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="/">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/about">about</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/contact">contact</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/grade">Grade</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Api
          </a>
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href="/golds">ราคาทองวันนี้</a></li>
            <li><a class="dropdown-item" href="/products_api">สินค้า</a></li>
             <li><a class="dropdown-item" href="/shop">แสดงรายการสินค้า</a></li>
            <li><a class="dropdown-item" href="/User">แสกงผู้ใช้งาน</a></li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</nav>
  <router-view/>
</template>


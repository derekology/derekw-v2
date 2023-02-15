<template>
  <nav>
    <div class="navbar navbar-dark bg-dark d-md-none">
      <button
        class="btn btn-primary ms-1"
        type="button"
        data-bs-toggle="offcanvas"
        data-bs-target="#sidebar-collapse"
        aria-controls="sidebar-collapse"
      >
        <span class="glyphicon glyphicon-menu-hamburger">Menu</span>
      </button>
    </div>
  </nav>
  <div
    class="offcanvas offcanvas-start"
    tabindex="-1"
    id="sidebar-collapse"
    aria-labelledby="sidebarLabel"
  >
    <div id="sidebar-collapse">
      <div
        class="d-flex flex-column flex-shrink-0 p-3 text-white bg-dark position-fixed;"
      >
        <button
          type="button"
          class="btn-close text-reset"
          data-bs-dismiss="offcanvas"
          aria-label="Close"
        ></button>
        <a
          href="/"
          class="d-flex align-items-center mb-3 mb-md-0 me-md-auto text-white text-decoration-none"
        >
        </a>
        <ul class="nav nav-pills flex-column mb-auto">
          <li class="nav-item">
            <a href="#" class="nav-link active" aria-current="page"> Home </a>
          </li>
          <li>
            <a href="#" class="nav-link text-white"> Dashboard </a>
          </li>
          <li>
            <a href="#" class="nav-link text-white"> Orders </a>
          </li>
          <li>
            <a href="#" class="nav-link text-white"> Products </a>
          </li>
          <li>
            <a href="#" class="nav-link text-white"> Customers </a>
          </li>
        </ul>
        <hr />
        <div class="dropdown">
          <a
            href="#"
            class="d-flex align-items-center text-white text-decoration-none dropdown-toggle"
            id="dropdownUser1"
            data-bs-toggle="dropdown"
            aria-expanded="false"
          >
            <img
              src="https://github.com/mdo.png"
              alt=""
              class="rounded-circle me-2"
              width="32"
              height="32"
            />
            <strong>mdo</strong>
          </a>
          <ul
            class="dropdown-menu dropdown-menu-dark text-small shadow"
            aria-labelledby="dropdownUser1"
          >
            <li><a class="dropdown-item" href="#">New project...</a></li>
            <li><a class="dropdown-item" href="#">Settings</a></li>
            <li><a class="dropdown-item" href="#">Profile</a></li>
            <li>
              <hr class="dropdown-divider" />
            </li>
            <li><a class="dropdown-item" href="#">Sign out</a></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
  <content class="row">
    <nav class="col-2 d-none d-md-block">
      <div id="sidebar">
        <div
          class="d-flex flex-column flex-shrink-0 p-3 text-white bg-dark position-fixed;"
        >
          <a
            href="/"
            class="d-flex align-items-center mb-3 mb-md-0 me-md-auto text-white text-decoration-none"
          >
          </a>
          <ul class="nav nav-pills flex-column mb-auto">
            <li class="nav-item">
              <a href="#" class="nav-link active" aria-current="page"> Home </a>
            </li>
            <li>
              <a href="#" class="nav-link text-white"> Dashboard </a>
            </li>
            <li>
              <a href="#" class="nav-link text-white"> Orders </a>
            </li>
            <li>
              <a href="#" class="nav-link text-white"> Products </a>
            </li>
            <li>
              <a href="#" class="nav-link text-white"> Customers </a>
            </li>
          </ul>
          <hr />
          <div class="dropdown">
            <a
              href="#"
              class="d-flex align-items-center text-white text-decoration-none dropdown-toggle"
              id="dropdownUser1"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              <img
                src="https://github.com/mdo.png"
                alt=""
                class="rounded-circle me-2"
                width="32"
                height="32"
              />
              <strong>mdo</strong>
            </a>
            <ul
              class="dropdown-menu dropdown-menu-dark text-small shadow"
              aria-labelledby="dropdownUser1"
            >
              <li><a class="dropdown-item" href="#">New project...</a></li>
              <li><a class="dropdown-item" href="#">Settings</a></li>
              <li><a class="dropdown-item" href="#">Profile</a></li>
              <li>
                <hr class="dropdown-divider" />
              </li>
              <li><a class="dropdown-item" href="#">Sign out</a></li>
            </ul>
          </div>
        </div>
      </div>
    </nav>
    <router-view class="col" />
  </content>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#sidebar,
#sidebar > div,
#sidebar-collapse,
#sidebar-collapse > div {
  height: 100vh;
}
</style>

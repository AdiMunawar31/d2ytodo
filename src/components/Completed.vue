<template>
  <div class="container">
    <div class="row d-flex justify-content-center">
      <div class="col-lg-8 col-sm-11">
        <div class="row p-3 shadow my-3 d-flex justify-content-center">
          <div class="col-sm-11 col-lg-11 py-3">
            <h4>Completed Todo</h4>
            <hr />
            <ul class="list-group">
              <li
                class="
                  list-group-item
                  d-flex
                  justify-content-between
                  align-items-center
                "
              >
                A list item
                <div class="d-flex">
                  <button class="btn btn-sm btn-primary rounded-pill shadow">
                    <i class="bi bi-arrow-repeat"></i>
                  </button>
                  <div class="mx-1"></div>
                  <button class="btn btn-sm btn-danger rounded-pill shadow">
                    <i class="bi bi-trash"></i>
                  </button>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
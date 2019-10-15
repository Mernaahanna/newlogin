<template>
  <div class="columns">
    <aside class="column is-1">
      <nav class="menu">
          <div class="box">
        <ul class="menu-list">
          <li>
            <nuxt-link
              to="/backend/orders"
              class="has-padding-40 has-padding-top-15 has-text-centered border-bottom"
            >
              <font-awesome-icon
                class="has-text-info has-margin-10"
                :icon="['fad', 'file-invoice-dollar']"
                size="2x"
              />
              <p>Orders</p>
            </nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/backend/products"
              class="has-padding-40 has-padding-top-15 has-text-centered border-bottom"
            >
              <font-awesome-icon class="has-text-warning has-margin-10" :icon="['fad', 'box']" size="2x" />
              <p>Products</p>
            </nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/backend/pages"
              class="has-padding-40 has-padding-top-15 has-text-centered border-bottom"
            >
              <font-awesome-icon class="has-text-link has-margin-10" :icon="['fad', 'folder-tree']" size="2x" />
              <p>Pages</p>
            </nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/backend/filemanager"
              class="has-padding-40 has-padding-top-15 has-text-centered border-bottom"
            >
              <font-awesome-icon
                class="has-text-primary has-margin-10"
                :icon="['fad', 'cabinet-filing']"
                size="2x"
              />
              <p>Filemanager</p>
            </nuxt-link>
          </li>
        </ul>
          </div>
      </nav>
    </aside>
  </div>
</template>
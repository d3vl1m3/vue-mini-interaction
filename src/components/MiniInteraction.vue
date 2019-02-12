<template>
  <div class="mini-interaction">
      <div class="mini-interaction__outer-container">
          <div class="mini-interaction__inner-container">

              <button class="mini-interaction__action" @click="toggleClicked()" v-bind:class="{'active': clicked, 'inactive': !clicked }" type="button">

                  <span class="mini-interaction__button-label">Actions</span>

                  <span class="icons__outer-container">

                      <span class="icons__inner-container">

                          <span class="dots-icon__container--arrow arrow-position">
                              <i class="fa fa-angle-up"></i>
                          </span>

                          <span class="dots-icon__container--dots dots-position">
                              <i class="dots-icon__dot fa fa-circle top-dot-animation"></i>
                              <i class="dots-icon__dot fa fa-circle"></i>
                              <i class="dots-icon__dot fa fa-circle bottom-dot-animation"></i>
                          </span>

                      </span>

                  </span>

              </button>

              <div class="actions-container">
                  <div class="actions__outer-container" v-bind:class="{'active': clicked, 'inactive': !clicked }">
                      <div class="actions__inner-container actions-container-animation">
                            <div class="actions__top-row">
                                <ul class="top-actions__list">
                                    <li>
                                        <button>
                                            <i class="fa fa-pencil"></i>
                                        </button>
                                    </li>
                                    <li>
                                        <button>
                                            <i class="fa fa-eye"></i>
                                        </button>
                                    </li>
                                    <li>
                                        <button>
                                            <i class="fa fa-times-circle"></i>
                                        </button>
                                    </li>
                                </ul>
                            </div>
                            <div class="actions__bottom-row">
                                <ul class="bottom-actions__list">
                                    <li>
                                        <a href="#">
                                            <span class="bottom-actions__title">Adjust Stock</span>
                                            <i class="fa fa-angle-right action-arrow"></i>
                                        </a>
                                    </li>
                                    <li>
                                        <a href="#">
                                            <span class="bottom-actions__title">Edit images / Gallery</span>
                                            <i class="fa fa-angle-right action-arrow"></i>
                                        </a>
                                    </li>
                                </ul>
                            </div>
                      </div>
                  </div>

              </div>
          </div>
      </div>
      <div>
          <h2>Text to show the overlay positioning when visible</h2>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores fugiat nam numquam omnis similique suscipit velit! Alias aut dolor illum provident temporibus tenetur vel! Architecto autem blanditiis, delectus, explicabo ipsum iure odio optio perspiciatis quasi recusandae reprehenderit saepe sapiente tempore? A ad alias aspernatur autem cupiditate deleniti dicta ducimus enim est facilis illum in incidunt ipsum laboriosam laborum magni minus molestiae molestias nemo neque numquam officia, omnis quasi quibusdam sint soluta suscipit voluptas! At dignissimos excepturi explicabo quae quasi rerum.</p>
      </div>
  </div>
</template>

<script>
    export default {
      name: 'MiniInteraction',
      data() {
        return {
            clicked: true,
            buttonAnimation: 'normal',
        }
      },
      methods: {
        toggleClicked: function() {
          this.clicked = !this.clicked;
        }
      }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    @import "../resources/scss/config";
    @import "../resources/scss/global";
    @import "../resources/scss/button";
    @import "../resources/scss/button-icons";
    @import "../resources/scss/actions-box";
    @import "../resources/scss/animations";

</style>

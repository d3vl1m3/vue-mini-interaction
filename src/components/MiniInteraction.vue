<template>
  <div class="mini-interaction">
      <div class="mini-interaction__outer-container">
          <div class="mini-interaction__inner-container">

              <button class="mini-interaction__action" @click="toggleClicked()" v-bind:class="{'active': clicked }" type="button">
                  <span class="mini-interaction__button-label">Actions</span>
                  <span class="icons__outer-container">
                      <span class="icons__inner-container">

                          <span class="dots-icon__container--arrow">
                              <i class="fa fa-angle-up"></i>
                          </span>

                          <span class="dots-icon__container--dots">
                              <i class="dots-icon__dot fa fa-circle"></i>
                              <i class="dots-icon__dot fa fa-circle"></i>
                              <i class="dots-icon__dot fa fa-circle"></i>
                          </span>

                      </span>
                  </span>
              </button>

              <div class="actions__outer-container" v-bind:class="{'visible': clicked}">
                  <div class="actions__inner-container actions-container">
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
      this.buttonAnimation = this.clicked ? 'normal' : 'reverse';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    $purple: #cd0274;
    $blue: #04a9fe;

    button {
        cursor: pointer;
    }

    .mini-interaction {

        &__inner-container {
            position: relative;
            width: 350px;
            margin: 0 auto;
        }

        &__action {
            background: $purple;
            border: 0;
            border-radius: 2em;
            color: white;
            display: flex;
            flex-wrap: wrap;
            font-size: 1.4rem;
            font-weight: 300;
            margin: 0 auto;
            padding: 0 1rem 0 2rem;
            position: relative;
            text-align: left;
            width: 200px;

            &::after {
                border: 17px solid transparent;
                border-top-color: $purple;
                color: white;
                content: '';
                left: calc(50% - 15px);
                position: absolute;
                top: calc(100% - 17px);
                transition: top 0.15s cubic-bezier(0.1, 0.9, 0.32, 1.6);
                width: 1px;
            }
        }

        &__button-label {
            flex-grow: 1;
            padding-top: 1.2rem;
            padding-bottom: 1.2rem;
        }
    }

    .icons {
        &__outer-container {
            min-height: 100%;
            width: 1.5em;
        }
        &__inner-container {
            display: flex;
            height: 100%;
            justify-content: center;
            overflow: hidden;
            position: relative;
        }
    }

    .dots-icon {

        &__container {

            &--arrow,
            &--dots {
                align-items: center;
                display: flex;
                height: 100%;
                flex-grow: 1;
                justify-content: center;
                position: absolute;
                top: 0;
                -webkit-transition: top 0.3s ease 0.2s;
                -moz-transition: top 0.3s ease 0.2s;
                -ms-transition: top 0.3s ease 0.2s;
                -o-transition: top 0.3s ease 0.2s;
                transition: top 0.3s ease 0.2s;
            }

            &--arrow {
                font-size: 1.1rem;
                top: -100%;
            }

            &--dots{
                width: 20px;
            }

        }

        &__dot {
            font-size: 0.65rem;
            position: absolute;
            padding-top: 0.825rem;
            padding-bottom: 0.825rem;

            &::after {
                content: ' ';
                width: 3px;
                height: 3px;
                background: orange;
            }

            transition: all 0.2s;

            &:first-of-type {
                margin-bottom: 1.8rem;
            }

            &:nth-of-type(3) {
                margin-top: 1.8rem;
            }

        }
    }

    .actions {
        &__inner-container {
            margin-top: 1.2rem;
            -webkit-box-shadow: 0 8px 8px 1px rgba(0,0,0,0.75);
            -moz-box-shadow: 0 8px 8px 1px rgba(0,0,0,0.75);
            box-shadow: 0 8px 8px 1px rgba(0,0,0,0.75);
        }
    }

    .top-actions {
        &__list {
            background: $blue;
            border-radius: 4px 4px 0 0;
            padding: 0.4rem 0;
            color: white;
            display: flex;
            flex-wrap: nowrap;
            list-style-type: none;
            margin: 0;

            li {

                flex-grow: 1;

                &:not(:last-of-type) {

                    button {
                        border-right: 1px solid rgba(white, 0.2);
                    }
                }

            }

            button {
                background: transparent;
                border: 0;
                color: white;
                display: block;
                font-size: 2.2rem;
                padding: 0.3rem 0;
                text-align: center;
                width: 100%;

            }
        }
    }

    .bottom-actions {
        &__list {
            text-align: left;
            display: flex;
            flex-wrap: wrap;
            flex-direction: column;
            font-size: 1.5rem;
            font-weight: 300;
            list-style-type: none;
            padding: 0 1.2rem;
            margin: 0;



            li {
                display: flex;
                &:not(:last-of-type) {
                    border-bottom: 1px solid rgba( #d3d3d3, 0.2);
                }
            }

            a {
                display: flex;
                width: 100%;
                padding: 2rem 0;
                text-decoration: none;
                color: #606060;
            }
        }

        &__title {
            flex-grow: 1;
        }
    }

    .action-arrow {
        color: #d9d9d9;
    }
</style>

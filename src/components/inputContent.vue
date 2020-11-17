<template>
    <div class="form">
      <div class="input-case">
        <span class="input__inner">
          <span
            class="input__top"
            :class="{ input__focused: (focused == true) || focused == false && lastName.length != 0 }"
          >
            {{placeholder}}
          </span>
          <span class="input__box">
            <input
              @focus="focused = true"
              @blur="focused = false"
              @input.prevent="handleInput"
              :value="lastName"
              class="input__control"
              autocomplete="off"
              name="lastName"
            />
          </span>
          <span class="input__sub">
            <div>{{inputSub}}</div>
          </span>
        </span>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
        focused: false,
        lastName: "",
    };
  },
  created() {
    console.log(this.lastName.length);
  },
  methods: {
    handleInput($event){
      this.lastName = $event.target.value;
      console.log(String($event.target.value));
      console.log(this.focused);
      console.log(this.lastName.length);
    }
  },
  computed: {

  },
  props: {
      placeholder : {
          type: String,
          default: () => {
              return ''
          }
      },
      inputSub: {
          type: String,
          default: () => {
              return ''
          }
      }
  }
};
</script>

<style lang="scss" scoped>
  // .form {
  //   box-sizing: border-box;

  //   .input-case {
  //     width: 100%;
  //     display: inline-block;
  //     position: relative;

  //     .input__inner {
  //       display: inline-table;
  //       position: relative;
  //       width: 100%;

  //       .input__top {
  //         overflow: hidden;
  //         position: absolute;
  //         line-height: 32px;
  //         font-size: 16px;
  //         top: 14px;
  //         right: 0;
  //         left: 0;
  //         text-overflow: ellipsis;
  //         white-space: nowrap;
  //         // color: rgba(11, 31, 53, 0.6);
  //         transition-duration: 0.2s;
  //         transform-origin: 0 100%;
  //         transition-property: color, transform, -webkit-transform;

  //         &.input__focused {
  //           transform: scale(0.8125) translateY(-38px);
  //         }
  //       }

  //       .input__box {
  //         overflow: hidden;
  //         position: relative;
  //         display: table-cell;
  //         // line-height: 40px;
  //         font-size: 16px;
  //         user-select: none;
  //         border-bottom-width: 1px;
  //         border-bottom-style: solid;
  //         border-bottom-color: rgba(11, 31, 53, 0.6);
  //         // height: 40px;

  //         .input__control {
  //           display: inline-block;
  //           position: relative;
  //           width: 100%;
  //           min-height: 100%;
  //           margin: 0;
  //           outline: none;
  //           // font-weight: 400;
  //           // font: inherit;
  //           line-height: inherit;
  //           border: none;
  //           border-radius: 0;
  //           background: none;
  //           color: rgba(11, 31, 53, 0.95);
  //           padding: 8px 0;
  //         }
  //       }

  //       .input__sub {
  //         display: table-caption;
  //         caption-side: bottom;
  //         padding-top: 5px;
  //         font-size: 13px;
  //         color: rgba(11, 31, 53, 0.6);
  //         // white-space: nowrap;
  //       }
  //     }
  //   }
  // }
</style>

<template>
  <div @click="toggleState" :class="[className, getIsActive]">
    <span class="switch-button-label">{{ getLabel }}</span>
    <span class="switch-button-max-label">{{ getMaxLabel }}</span>
    <div class="switch-button-knob"></div>
  </div>
</template>
<script>
export default {
  name: "toggleswitchbutton",
  props: {
    modelValue: Boolean,
    className: {
      type: String,
      default: "toggle-switch-button"
    },
    label: String
  },

  data() {
    return {
      curValue: this.modelValue ? true : false
    };
  },
  methods: {
    toggleState() {
      this.curValue = !this.curValue;
      this.$emit("update:modelValue", this.curValue);
    }
  },
  computed: {
    getIsActive() {
      return this.curValue ? "Active" : "";
    },
    getLabel() {
      if (this.label) {
        let labels = this.label.split("|");
        let label = labels[this.curValue ? 0 : 1];
        return label ? label : "";
      } else {
        return "";
      }
    },

    getMaxLabel() {
      let maxLabel = "";
      if (this.label) {
        let labels = this.label.split("|");
        labels.forEach(x => {
          if (maxLabel.length < x.length) {
            maxLabel = x;
          }
        });
      }
      return maxLabel;
    }
  }
};
</script>
<style>
.toggle-switch-button * {
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
  pointer-events: none;
}
.toggle-switch-button {
  box-sizing: border-box;
  display: inline-block;
  min-width: 50px;
  height: 20px;
  border: solid 1px black;
  border-radius: 11px;
  position: relative;
  transition: all 200ms ease-in-out;
  background-color: lightgray;
  color: black;
  font-size: 14px;
  line-height: 18px;
  text-align: right;
  padding: 0px 5px;
  cursor: pointer;
}
.toggle-switch-button.Active {
  background-color: green;
  text-align: left;
  color: white;
}
.toggle-switch-button .switch-button-knob {
  display: inline-block;
  width: 20px;
  height: 20px;
  border: solid 1px black;
  position: absolute;
  left: calc(0% - 1px);
  border-radius: 10px;
  transition: left 300ms ease-in-out;
  background-color: white;
  top: -1px;
}
.toggle-switch-button.Active .switch-button-knob {
  left: calc(100% - 20px);
}
.toggle-switch-button .switch-button-label {
  margin-left: 20px;
  margin-right: 0px;
  display: inline-block;
  position: absolute;
  opacity: 1;
}
.toggle-switch-button.Active .switch-button-label {
  margin-left: 0px;
  margin-right: 20px;
}
.toggle-switch-button .switch-button-max-label {
  margin-left: 20px;
  margin-right: 0px;
  opacity: 0;
}
</style>

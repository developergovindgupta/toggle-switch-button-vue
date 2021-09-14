# toggle-switch-button-vue
# VUE-3
## No Dependency  only single vue component file
### A vue component with two way binding via v-model a boolean value toggle true/false
### also label property shows label on button with '|' separated. As "ON|OFF" 




![](https://raw.githubusercontent.com/developergovindgupta/toggle-switch-button-vue/master/src/assets/toggleswitchbuttonoff.png)
![](https://raw.githubusercontent.com/developergovindgupta/toggle-switch-button-vue/master/src/assets/toggleswitchbuttonon.png)



## Properties

|props   | type | default | description | 
| ------------ | ------------ | ------------ | ------------ |
| v-model  | Boolean  | false | two way binding that toggle value true/false |
|label|string| | pipe separated value "ON&#124;OFF"|
|className|string|"toggle-switch-button"|custom css class name to change the UI layout|




## How to Install
copy following code and run on CLI

`npm install toggle-switch-button-vue`

# How to use 
Example Code 

[download from gitHub](https://github.com/developergovindgupta/toggle-switch-button-vue "download from gitHub")


## usase

**template sectioln**

    <div>
        <ToggleSwitchButton v-model="this.isActive" label="ON|OFF" />
    </div>
    <h1>{{ isActive }}</h1>


**script section**

    import ToggleSwitchButton from "toggle-switch-button-vue";

**components section**

    components: {
        ToggleSwitchButton
    },


**data section**

    data() {
        return {
          isActive: true
        };
    },
  

**methods section**

    methods: {
        
      }
	  
	  
## View Demo
[View Demo](https://codesandbox.io/s/toggle-switch-button-vue-ko6yz?file=/src/App.vue)

## License Free

## Author : Govind Prasad Gupta
### developergovindgupta
### email : govindprasadguptamca@gmail.com




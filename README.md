# cordova-plugin-keyboard2

> 在cordova 基础插件之上做了是否弹出输入法的判断. 
当输入法弹出的时候,可以通过keyboardDidShow keyboardDidHide 来判断.
也可以在回退事件中通过Keyboard.isVisible 来判断

#### Quick Example

      function onBackKeyDown(e) {
        e.preventDefault();
        if(!Keyboard.isVisible){
            //退出操作
        }
        e.stopPropagation();
    }
    function onkeyboardDidShow(e,result){
        e.preventDefault();
         // alert('keyboardDidShow');
        e.stopPropagation();
      
    }

    function onkeyboardDidHide(e){
        e.preventDefault();
        // alert('keyboardDidHide');
        e.stopPropagation();
        
    }
    function deviceReady() {
        $(window).bind("keyboardDidShow", onkeyboardDidShow);
        $(window).bind("keyboardDidHide", onkeyboardDidHide);
        $(document).bind("backbutton", onBackKeyDown);
    }
    

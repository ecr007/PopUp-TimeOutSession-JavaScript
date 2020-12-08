# PopUp-TimeOutSession-JavaScript

```
<?php if( isset($_SESSION['TTL_USER']['user_id']) && $_SESSION['TTL_USER']['user_id']!=''): ?>

    <style type="text/css">
        .timeout-expired{display:none;}.timeout-head {position: relative;margin-bottom: 25px;}.overlay-timeout{background:rgba(0,0,0,70%);width:100%;height:100%;position:fixed;top:0;left:0;right:0;z-index:100;display:none}.shoppingicon2{z-index:99!important}.timeout-alert{position:fixed;z-index:101;top:30%;width:300px;background:#fff;padding:16px;margin-left:auto;margin-right:auto;left:0;right:0;display:none}.timeout-alert .timeout-head h3{font-size:20px;margin-top:0}.timeout-alert .timeout-head .timeout-close{position:absolute;top:-2px;right:-2px;color:#d43f3a;background:transparent;border:none;font-size:22px;cursor:pointer}.timeout-body{margin-bottom:25px}.timeout-body p{font-size:16px;line-height: 25px;}.timeout-actions button{margin-right:20px;display:inline-block;margin-bottom:0;font-weight:400;text-align:center;white-space:nowrap;vertical-align:middle;-ms-touch-action:manipulation;touch-action:manipulation;cursor:pointer;background-image:none;border:1px solid transparent;padding:6px 12px;font-size:14px;line-height:1.42857143;border-radius:4px;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none}.timeout-expired,.timeout-ok{background:#3F3429;color:#fff}
    </style>
    
    <div class="overlay-timeout"></div>
    <div class="timeout-alert">
        <div class="timeout-head">
            <h3>No hay actividad reciente</h3>
            <button class="timeout-close" onclick="closeAlertTimeOut()">&times;</button>
        </div>
        
        <div class="timeout-body">
            <p></p>
        </div>
        
        <div class="timeout-actions">
            <button class="timeout-ok" onclick="extendTime();">Extender la sesión</a>
            <button class="timeout-expired" onclick="goToLoginTimeOut();">Ir al login</a>
            <button class="timeout-no-ok" onclick="closeAlertTimeOut()">Cancelar</a>
        </div>
    </div>
    <script>
        var txt26 = "Tu sesión está a punto de terminar. ¿Quiere extender su sesión actual?";
        var txt30 = "Tu sesión a terminado, debido a que han pasado mas de 30 minutos sin actividad por seguridad hemos terminado la sesión. Favor entrar nuevamente.";
        
        function extendTime(){
            document.location.reload();
        }
        
        function goToLoginTimeOut(){
            document.location.href="/sign-up.html";
        }
        
        function closeAlertTimeOut(){
            $('.overlay-timeout,.timeout-alert').hide();
        }
        
        function openAlertTimeOut(txt){
            $('.timeout-body p').text(txt)
            $('.overlay-timeout,.timeout-alert').show();
        }
        
        
        setTimeout(function(){
            $('.timeout-expired').hide();
            $('.timeout-ok,.timeout-no-ok,.timeout-close').show();
            openAlertTimeOut(txt26);
        },1560000); // 26 minutos
        
        setTimeout(function(){
            $('.timeout-ok,.timeout-no-ok,.timeout-close').hide();
            $('.timeout-expired').show();
            openAlertTimeOut(txt30);
        },1806000);
    </script>

<?php endif;?>
```

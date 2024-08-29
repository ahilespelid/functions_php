install bitrix code <br>
<code>
if(file_exists($ff = __DIR__.'/functions/init.php')){require_once $ff;}
spl_autoload_register(function($class){
    $exp = explode('\\', $class); $namespace = strtolower($exp[0]); $class = $exp[1];  
    if('service' == $namespace && in_array(count($exp), [2,3])){
        if('Traits' == $class){$namespace = 'trait'; $class = $exp[2];}
        include_once($p = __DIR__.DIRECTORY_SEPARATOR.$namespace.DIRECTORY_SEPARATOR.$class.'.php'); 
}});
</code>


<!-- La lista de lifecycle hooks se compone de 13 y son fases de la creacion de componentes. Esto nos puede servir para que en determinados momentos, nosotros decir exactamente que hacer y cuando. -->
<!-- CREATION -->
<!-- beforeCreate(es antes que se creen los metodos, data, etc.)
    created(es el mejor momento para hacer api calls,) 
-->
<!-- MOUNTING -->
<!-- Es cuando se crea el html y se monta el browser. -->
<!-- 
    beforeMounting()
    mounted() 
-->
<!-- UPDATING -->
<!-- Es el momento donde se modifican variables, ejecutan computed propertys, etc. -->
<!-- 
    beforeUpdate()
    updated() 
-->
<!-- UNMOUNTING -->
<!-- Son cosas necesarias al final de un proceso, por ejemplo un metodo de eliminar suscripcion o cosas similares, que terminan algun evento en particular. -->
<!--
    beforeUnmount()
    unmounted() 
-->
<!-- MISCELANEUS -->
<!-- 
    activated()
    deactivated()
    estan relacionados con el keepalive, se llaman por lo gral en caso de querer activar el keep alive y para desactivarlo.
    errorCaptured()    
    renderTracked()
    renderTriggered()
    Los ultimos 2 son para chequear y debuggear. 
-->
<!-- 
    el orden en caso de que tengamos 2 componentes seria el siguiente.
    parent beforeCreate()
    parent created()
    paren beforeMount()
    child beforeCreate()
    child created()
    child beforeMount()
    child mounted()
    parent mounted() 
-->
<!-- De esta forma podemos ver, como es orden basicamente, en este caso el padre seria app.vue y el hijo un componente, como podemos ver, el padre se crea, pero cortan antes de montar, ya que para poder avanzar tiene que ver que hace el hijo dentro, entonces ahi comienza a ejecutarse el child component, el cual realiza todo los pasos hasta estar montado, para luego el padre montarse. -->

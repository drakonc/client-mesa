<template>
    <div id="ini">
        <div class="container-fluid pt-3">
            <div class="row align-items-start">
                <div class="col-md-8 offset-md-2">
                    <div class="card border border-primary">
                        <div class="card-header text-center bg-primary">
                            <h2 class="card-title text-white text-uppercase">Bienvenido a la Mesa de Servicio</h2>
                        </div>
                        <div class="card-body">
                            <img src="@/assets/img/logo.jpg" height="450" class="card-img-top" alt="...">
                            <div class="pt-3">
                                <a href="/ticket" class="btn btn-primary btn-block text-white"><font-awesome-icon icon="ticket-alt" /> Crear Ticket</a>
                            </div>
                        </div>
                    </div>
                </div>
             </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ini'
    }
</script>

<style lang="css" scoped>

</style>
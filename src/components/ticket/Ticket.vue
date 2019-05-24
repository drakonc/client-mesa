<template>
    <div id="tick">
        <navTicket />
        <div class="container-fluid pt-5">
            <div class="row">
                <div class="col-md-10  offset-md-1">
                    <div class="card border border-primary">
                        <div class="card-header text-center">
                            <h5 class="card-title text-left"><font-awesome-icon icon="ticket-alt" /> Crear Ticket</h5>
                        </div>
                        <div class="card-body">
                            <form action="/">
                                <div class="container-fluid">
                                    <div class="row">
                                        <div class="col-md-6 pt-3">
                                            <div class="card border border-primary">
                                                <div class="card-header bg-primary text-white font-weight-bold"><font-awesome-icon icon="database" /> Datos Del Solicitantes</div>
                                                <div class="card-body">
                                                    <div class="form-group input-group mb-3">
                                                        <input type="text" name="nombre" class="form-control" placeholder="Nombre del Solicitante" aria-describedby="iusuario" autofocus>
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text" id="iusuario"><font-awesome-icon icon="user" /></span>
                                                        </div>
                                                    </div>
                                                    <div class="form-group input-group mb-3">
                                                        <input type="number" name="cedula" class="form-control" placeholder="Cedula del Solicitante" aria-describedby="icedula">
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text" id="icedula"><font-awesome-icon icon="address-card" /></span>
                                                        </div>
                                                    </div>
                                                    <div class="form-group input-group mb-3">
                                                        <input type="number" name="telefono" class="form-control" placeholder="Telefono del Solicitante" aria-describedby="itelefono">
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text" id="itelefono"><font-awesome-icon icon="phone-square" /></span>
                                                        </div>
                                                    </div>
                                                    <div class="form-group input-group mb-3">
                                                        <input type="email" name="correo" class="form-control" placeholder="Correo del Solicitante" aria-describedby="icorreo">
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text" id="icorreo"><font-awesome-icon icon="envelope" /></span>
                                                        </div>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="col-md-6 pt-3">
                                            <div class="card border border-primary">
                                                <div class="card-header bg-primary text-white font-weight-bold"><font-awesome-icon icon="cubes" /> Información Geneal</div>
                                                <div class="card-body">
                                                    <div class="form-group input-group mb-3">
                                                        <select id="stsolicitud" class="custom-select form-control" name="area" aria-describedby="itsolici" @change="onChange($event)">
                                                            <option selected>Tipo de Solicitud</option>
                                                            <option v-for="item in tsolicitud" :key="item.id" :value="item.id">{{ item.tsolicitud }}</option>
                                                        </select>
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text" id="itsolici"><font-awesome-icon icon="exclamation" /></span>
                                                        </div>
                                                    </div>
                                                    <div class="form-group input-group mb-3">
                                                        <select class="custom-select form-control" name="solicitud" aria-describedby="isolici">
                                                            <option selected>Problema</option>
                                                            <option value="1">Incidencia</option>
                                                            <option value="2">Solicitud</option>
                                                        </select>
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text" id="isolici"><font-awesome-icon icon="exclamation-triangle" /></span>
                                                        </div>
                                                    </div>
                                                    <div class="form-group input-group mb-3">
                                                        <select class="custom-select form-control" name="tecnico" aria-describedby="itecnico">
                                                          <option selected>Tecnico de Sistemas</option>
                                                          <option value="1">Incidencia</option>
                                                          <option value="2">Solicitud</option>
                                                        </select>
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text" id="itecnico"><font-awesome-icon icon="cogs" /></span>
                                                        </div>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="row align-items-center">
                                        <div class="col-md-6 pt-3">
                                            <div class="card border border-success">
                                                <div class="card-header bg-success text-white font-weight-bold"><font-awesome-icon icon="file-alt" /> Descripción</div>
                                                <div class="card-body">
                                                    <textarea name="descripcion" class="form-control"  rows="2"></textarea>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="col-md-6 pt-3">
                                            <button class="btn btn-primary btn-lg btn-block text-white"><font-awesome-icon icon="ticket-alt" /> Crear Ticket</button>
                                        </div>
                                    </div>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import navTicket from '@/components/ticket/navTicket.vue'
    import axios from 'axios'
    
    let API_URL = 'http://localhost:3000/api/'

    export default {
        name:'tick',
        data(){
            return {
                tsolicitud:[]
            }
        },
        components: {
            navTicket
        },
        mounted: function(){
            this.getDatos();
        },
        methods:{
            getDatos(){
                const url = `${API_URL}/tsolicitud`
                axios.get(url).then(res => this.tsolicitud = res.data)
            },
            onChange(event){
                console.log(event.target.value)
            }
        }
    }
</script>

<style lang="css" scoped>

</style>

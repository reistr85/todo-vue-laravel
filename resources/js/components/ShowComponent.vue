<template>
    <div class="container mt-3">
        <div class="row justify-content-center">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-header">Dados do Usuário</div>

                    <div class="card-body">

                        <router-link to="/users" class="btn btn-danger btn-sm mb-3"><i class="fa fa-reply-all"></i> voltar</router-link>

                        <div class="table-responsive">
                            <table class="table table-hover">
                                <thead class="bg-dark text-white">
                                    <tr>
                                        <th scope="col">#</th>
                                        <th scope="col">Nome</th>
                                        <th scope="col">E-mail</th>
                                        <th scope="col">Contato</th>
                                    </tr>
                                </thead>

                                <tbody v-if="loader == false">
                                    <tr>
                                        <th scope="row">{{ user.id }}</th>
                                        <td>{{ user.name }}</td>
                                        <td>{{ user.email }}</td>
                                        <td>{{ user.phone }}</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>

                        <div v-if="loader" class="d-flex justify-content-center">
                            <div class="spinner-border text-primary" role="status">
                                <span class="sr-only">Loading...</span>
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
        data: function () {
            return {
                user: [],
                loader: true
            }
        },
        mounted: function() {
            this.show();
        },
        methods: {
            show: function(){
                axios.get(this.$BASE_URL+"users/"+this.$route.params.id).then((response) => {
                    this.user = response.data;
                }).catch(error => {

                }).finally(()=>{
                    this.loader = false;
                });
            }
        }
    }
</script>

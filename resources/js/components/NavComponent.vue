<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <a class="navbar-brand" href="/">Desafio</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item">
                    <router-link to="/" class="nav-link">Início</router-link>
                </li>
                <li class="nav-item">
                    <router-link to="/users" class="nav-link">Usuários</router-link>
                </li>
                <li class="nav-item">
                    <router-link to="/todo" class="nav-link">Todo</router-link>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
    export default {

    }
</script>
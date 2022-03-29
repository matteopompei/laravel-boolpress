<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-light">
            <a class="navbar-brand" href="#">Boolpress</a>
            <button
                class="navbar-toggler"
                type="button"
                data-toggle="collapse"
                data-target="#navbarNav"
                aria-controls="navbarNav"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <router-link :to="{ name: 'home' }" class="nav-link"
                            >Home</router-link
                        >
                    </li>
                    <li class="nav-item">
                        <router-link :to="{ name: 'about' }" class="nav-link"
                            >About us</router-link
                        >
                    </li>
                </ul>
            </div>
            <div class="form-inline">
                <a class="btn" href="/login">Accedi</a>
                <a class="btn btn-success" href="/register">Registrati</a>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: "Header",
};
</script>

<style lang="scss" scoped>
nav {
    background: #fff !important;
}
</style>

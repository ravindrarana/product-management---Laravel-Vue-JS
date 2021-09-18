<template>
    <div class="container-fluid"> 
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <div class="collapse navbar-collapse d-flex justify-content-end">
                <div class="navbar-nav mt-3">
                    <router-link to="/" class="nav-item nav-link btn btn-sm btn-success text-white">Product List</router-link>
                    <router-link to="/create" class="nav-item nav-link btn btn-sm btn-primary mx-3 text-white">Create Product</router-link>
                </div>
            </div>
        </nav>

        <router-view> </router-view>
    </div>
</template>
 
<script>
    export default {}
</script>
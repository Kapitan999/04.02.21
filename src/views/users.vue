<template>
 <div>
     {{ $route.params.id }}
</div>
</template>

<script>
export default {
    props: [
        'user'
    ],
    mounted() {
        if(this.user == '') this.$router.push('/login');
    }
}
</script>
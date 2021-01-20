<template>
    <div>
        <h1 :style="{textDecoration: decoration}">Hello {{name}}</h1>
        <input type="text" v-model="name">
    </div> 
</template>

<script>
export default {
    data: () => ({
        
        name: 'Pedro',
        decoration: 'underline'
    })
}
</script>
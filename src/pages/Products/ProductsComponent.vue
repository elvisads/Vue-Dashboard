<template>
    <DashboardComponent>
        <div slot="slot-pages" class="content-pages">
        <header class="title_pages">
            <p>Produtos</p>
        </header>
        
        </div>
    </DashboardComponent>
</template>

<script>
import DashboardComponent from '../Dashboard/DashboardComponent';


export default {
    name: 'ProductsComponent',
    components : {
        DashboardComponent,
        
    }    
}
</script>
<style scoped>

</style> 

<style lang="scss" src="./style.scss" scoped />
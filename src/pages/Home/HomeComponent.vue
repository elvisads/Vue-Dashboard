<template>
    <DashboardComponent>
        <div slot="slot-pages" class="content-pages">
            <header class="title_pages">
                <p>Início</p>
            </header>
            <div>
                <div class="row">
                    <div class="col-12 col-md-3">
                        <CardsComponent :type="'Clientes'" :percentage="'7%'" :icon="'fa-users'" :qtd="'7590'" />
                    </div>
                    <div class="col-12 col-md-3">
                        <CardsComponent :type="'Produtos'" :percentage="'12%'" :icon="'fa-box'" :qtd="'350'" />
                    </div>
                    <div class="col-12 col-md-3">
                        <CardsComponent :type="'Serviços'" :percentage="'3%'" :icon="'fa-store'" :qtd="'270'" />
                    </div>
                    <div class="col-12 col-md-3">
                        <CardsComponent :type="'Relatórios'" :percentage="'25%'" :icon="'fa-chart-bar'" :qtd="'30'" />
                    </div>
                </div>
            </div>
            <div class="mt-5">
                <div class="row">
                    <div class="col-12 col-md-6">
                        <!--<ListsComponent :data="users" description="Clientes" :columns="['Nome', 'E-mail']"/>-->
                    </div>

                    <div class="col-12 col-md-6">
                        <!--<ListsComponent :data="users" description="Produtos" :columns="['Nome', 'E-mail']" />-->
                    </div>
                </div>
            </div>
        </div>
    </DashboardComponent>
</template>

<script>
/* eslint-disable*/
import DashboardComponent from '../Dashboard/DashboardComponent';
import CardsComponent from '../../components/CardsComponent';
import ListsComponent from '../../components/ListsComponents';
const axios = require('axios').default;

export default {
    name: 'HomeComponent',
    data() {
        return {
            clients: [],
            products: [],
        }
    },
    mounted() {
        this.getUsers();
    },
    methods: {
        async getUsers(){
            let response = await axios.get('/');

            if(response.status == 200){
                console.log(response.data);
                this.users = response.data;
            }else{
                console.error("Ocorreu um erro na API.");
            }
        }
    },
    components : {
        DashboardComponent,
        CardsComponent,
        ListsComponent,
    }
}    
</script>
<style lang="scss" scoped>
    
    .cards{
        display: flex;
        justify-content: space-between;
    }
</style> 
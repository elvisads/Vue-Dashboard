<template>
    <div class="lists">
        <div class="top">
            <p><strong>{{description}} <span class="badge badge-info">{{data.length}}</span></strong></p>
        </div>

        <div class="content">
            <table class="table table-triped my_table">
            <thead>
                <tr>
                <th scope="col">#</th>
                <th scope="col">{{ columns[0] }}</th>
                <th scope="col">{{ columns[1] }}</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in data" :key="user.id">
                <th scope="row">{{ user.id }}</th>
                <td><p class="users">{{ user.name }}</p></td>
                <td><p class="users">{{ user.email }}</p></td>
                </tr>
            </tbody>
            </table>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ListsComponent',
    props: {
        data: Array,
        description: String,
        columns: [],
    }
}
</script>

<style lang="scss" scoped>

.lists {
    width: 100%;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    background-color: #fff;
}

.users {
    font-size: 12px;
}

</style>
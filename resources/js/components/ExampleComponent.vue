<template>
    <div class="container">
        <div class="panel panel-success">
            <div class="panel-body">
                <div class="row container">
                    <table class="table table-striped">
                        <thead>
                        <th>Name</th>
                        <th>Nickname</th>
                        <th>Sex</th>
                        <th>Action</th>
                        </thead>

                        <tr v-for="intern in interns">
                            <td>{{ intern.name }}</td>
                            <td>{{ intern.nickname }}</td>
                            <td>{{ intern.sex }}</td>
                            <td><button class="btn btn-info" type="button" @click="loadView(intern.id)">View</button></td>
                        </tr>
                        <br>
                    </table>
                </div>
            </div>
        </div>
        <div class="panel panel-info" v-if="showView">
            <div class="panel-body">
                <div class="row container">
                    <h4>{{intern.name}}</h4>
                    <p>{{intern.nickname}}</p>
                    <p>{{intern.sex}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                interns: [
                    { id: 1, name: 'Joan Eneki', nickname: 'Cyborg', sex: 'F'},
                    { id: 2, name: 'Michael Mukolwe', nickname: 'kuku', sex: 'M' },
                    { id: 3, name: 'Emmanuel Ogoma', nickname: 'C-sharp', sex: 'M' }
                ],

                showView: false,

                intern: {}

            }
        },

        methods: {
            loadView: function (id) {
                // write an api to take the id and bring data save to intern{}
                // intern = data.response...then we display the intern on the hidden panel...
                // so onclick the id will change...if this method doesn't work you can use a watcher or computed property...

                this.showView = true;

                this.intern = {
                    id: 2, name: 'Michael Mukolwe', nickname: 'kuku', sex: 'M'
                }
            }
        }
    }
</script>

<template>
    <div id="content">
        <h1>{{title}}!</h1>
        <h2>{{msg}}!</h2>
        <input v-model="title" />
        <button v-on:click="greet(title)">Click for alert</button>
        <p v-if="showName">{{user.firstName}}</p>
        <p v-else="showName">{{user.lastName}}</p>
        <h4>{{fullName}}</h4>
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>

        <br />
        <input type="text" v-on:keyup="pressKey "v-on:keyup.enter="enterHit">
        <br />
        <a href="/">Back to front</a>
    </div>
</template>

<script>
    export default {
        name: 'components',
        props: {
            msg: {
                type: String,
                default: 'No passed value'
            }
        },
        data() {
            return {
                title: 'Title',
                user: {
                    firstName: 'Object 1',
                    lastName: 'Object 2'
                },
                showName: true,
                items: [
                    {title: 'Item one'},
                    {title: 'Item two'},
                    { title: 'Item three'}
                ]
            }
        },
        methods: {
            greet: function(input) {
                alert(input);
            },
            pressKey: function(e) {
                console.log(e.target.value);
            },
            enterHit: function() {
                console.log('You hit enter!');
                this.user.firstName = this.user.firstName + '!'
            }
        },
        computed: {
            fullName: function() {
                return this.user.firstName + ' ' + this.user.lastName;
            }
        }
    }
</script>


<style scoped>

</style>
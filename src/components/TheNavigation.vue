<template>
    <ul>
        <li>
            <router-link
                :to="{
                    name:'Home'
                }"            
            >
                Home
            </router-link>
        </li>
        
        <template v-if="authenticated">     
            <li>
                {{user.name}}
            </li>
            <li>
                <router-link
                    :to="{
                        name:'Dashboard'
                    }"            
                >
                    Dashboard
                </router-link>
            </li>
            <li>
                <a href="#" @click.prevent="signOut">Log out </a>
            </li>
        </template>
        <template v-else>
            <li>
                <router-link
                    :to="{
                        name:'Login'
                    }"            
                >
                    Log in
                </router-link>
            </li>
        </template>

    </ul>
</template>

<script>
    import { mapGetters, mapActions} from 'vuex'
    export default {
        computed: {
            ...mapGetters({
                authenticated: 'auth/authenticated',
                user: 'auth/user',
            })
        },

        methods: {
            ...mapActions({
                signOutAction:'auth/signOut'
            }),

            signOut(){
                this.signOutAction().then(()=>{
                    this.$router.replace({
                        name:'Home'
                    })
                })
            }
        }
    }
</script>
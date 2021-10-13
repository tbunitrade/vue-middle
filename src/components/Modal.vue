<template>
    <li class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale' }">
            <h1>{{header}}</h1>
         
            <p>
               {{text}}
            </p>

            <ul>
                <li>{{body}} </li>
            </ul>
            <button @click="closeModal">Close</button>
        </div>

    </li>
</template>
<script>


export default {
    props:[
        'header','text', 'body', 'theme'
    ],
    methods: {
        closeModal() {
            console.log('close not work this method')
            this.$emit('close');
            //this.showModal=false;
        }
    }


}
</script>


<style scoped>
    .modal {
        width: 400px;
        padding: auto;
        margin:100px auto;
        background:white;
        border-radius: 10px;
        padding: 1em;
    }

    .backdrop {
        top:0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }

    h2 {
        color: #03cfb4;
        border:none;
        padding: 0;
    }

    p {
        font-family: 'Montserrat';
        font-size: 1em;
        font-style: normal;
    }

    .modal.sale {
        background: crimson;
    }

    .modal.sale h1 {
        color: white;
    }

</style>
    <template>
        <div class="container">
            <v-card
        
        class="roundedCard"
        width="500"
        border-radius="100"
        margin-top="20px"
        hover
        v-bind="props"
        >
        <v-img
            class="align-end text-white"
            height="200"
            :src= "image"
            :alt="title"
            cover
        >
            <!-- <v-card-title>{{ title }}</v-card-title> -->
        </v-img>
        <div class="card">
            <v-card>
                <v-card-title class="pt-4">
                    {{ title }}
                </v-card-title>
            <v-card-text>
                <div>Author: {{ author }}</div>
            <div>{{ description }}</div>
        </v-card-text>
    <v-card-actions>
        <v-rating
            :model-value="rating"
            background-color="orange"
            class="me-2"
            color="orange"
            dense
            hover
            readonly
        ></v-rating>
        <v-container>
        <v-row justify="space-around">
        <v-col cols="12" md="6">
            <v-dialog
            transition="dialog-bottom-transition"
            width="auto"
            >
            <template v-slot:activator="{ props: activatorProps }">
                <v-btn
                v-bind="activatorProps"
                text="View Summary"
                block
                width="100%"
                ></v-btn>
            </template>

            <template v-slot:default="{ isActive }">
                <v-card
                class="roundedCard2"
                width="600"
                >
                <v-toolbar title="Summary"></v-toolbar>

                <v-card-text>
                    {{ summary }}
                </v-card-text>

                <v-card-actions class="justify-end">
                    <v-btn
                    text="Close"
                    @click="isActive.value = false"
                    ></v-btn>
                </v-card-actions>
                </v-card>
            </template>
            </v-dialog>
        </v-col>
        </v-row>
    </v-container>
</v-card-actions>
</v-card>
</div>        
</v-card>

</div>

    </template>
    <script>
    import { ref } from 'vue';
import Modal_View from './Modal_View.vue';
    
    export default {
  components: { Modal_View },
        name: 'Card',
        props: [
            'title',
            'author',
            'description',
            'summary',
            'image',
            'rating'
        ],
        setup(){
            let modalView = ref(false);
            //implement the toggle modal function
    const toggleModal =() =>{
        modalView = !modalView
    }
            return{
                toggleModal,
                modalView
            }
        }
    };

    </script>
    <style scoped>
    .card :hover{
        background-color: rgba(49, 204, 194, 0.679);
    }
    .container{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 400px;
        border-radius: 80px;
        margin-bottom: 50px;
        margin-top: 40px;
        margin-left: 90px;
    }
    .roundedCard{
        border-radius: 20px;
    }
    .roundedCard2{
        border-radius: 90px;
    }
    </style>

<template>
    <div>
        <h1>Create an event</h1>
        <form>

            <!-- <label>Select a category</label> -->
            <BaseSelect v-model="event.category" label="Select a category" :options="categories" />
            <h3>Name & describe your event</h3>

            <BaseInput v-model="event.title" label="Full name" type="text" />

            <BaseInput v-model="event.description" label="Description" type="text" />

            <h3>Where is your event?</h3>
            <BaseInput v-model="event.location" type="text" label="Location" />
            <div>{
                <p>Name: {{ event.title }}</p>
                <p>description: {{ event.description }}</p>
                <p>Location: {{ event.location }}</p>
                <p>Category: {{ event.category }}</p>
                <p>Pet Allowed?: <span v-if="event.pets">Yes</span> <span v-else>No</span></p>
                <br>
                }
            </div>
            <h3>Are pets allowed?</h3>
            <div>
                <BaseInput v-model="event.pets" type="radio" :value="1" label="Yes" name="pets" />
            </div>

            <div>
                <BaseInput v-model="event.pets" type="radio" :value="0" label="No" name="pets" />
            </div>

            <h3>Extras</h3>
            <div>
                <input type="checkbox" v-model="event.extras.catering" class="field" />
                <label>Catering</label>
            </div>

            <div>
                <input type="checkbox" v-model="event.extras.music" class="field" />
                <label>Live music</label>
            </div>

            <button class="button -fill-gradient" type="submit">Submit</button>
        </form>
    </div>
</template>
  
<script>
import BaseInput from '../components/BaseInput.vue';
import BaseSelect from '../components/BaseSelect.vue';

export default {
    data() {
        return {
            categories: [
                'sustainability',
                'nature',
                'animal welfare',
                'housing',
                'education',
                'food',
                'community'
            ],
            event: {
                category: '',
                title: '',
                description: '',
                location: '',
                pets: 1,
                extras: {
                    catering: false,
                    music: false
                },
                acceptedExtras:[]
            }
        };
    },
    components: { BaseInput, BaseSelect }
}
</script>
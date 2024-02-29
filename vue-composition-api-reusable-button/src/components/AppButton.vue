<template>
    <div class="button-container">

        <!-- Without Vue Dynamic components -->
        <!-- <a v-if="href" :href="href">
            <slot />
        </a>

        <button class="button" v-else>
            <slot />
        </button> -->

        <!-- With Dynamic components usage -->
        <component :is="buttonType" :href="href" class="button" :style="{color, backgroundColor: bgColor, width}">
            <slot/>
        </component>
    </div>
</template>

<script setup>
import {computed} from 'vue';

    const props = defineProps({
        href: {
            type: String,
            default: null
        },
        style: {
            type: Object,
            default() {
                return {
                    color: 'aliceblue',
                    bgColor: 'orange',
                    width: '150px',
                }
            } 
        }
    })

    const {color, bgColor, width} = props.style;
    const {href} = props

    const buttonType = computed(() => {
        if (href) {
            return 'a'
        } else {
            return 'button'
        }
    })
</script>

<style lang="scss" scoped>
.button-container {
    display: flex;
    justify-content: center;
}

.button {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 15px 25px;
    font-size: 1em;
    border: none;
    border-radius: 10px;
    text-transform: uppercase;
    font-weight: 600;
    cursor: pointer;
    letter-spacing: 0.03em;
    line-height: 1.2;
    transition: .3s;
    margin: 10px 0;
    text-overflow: ellipsis;
    max-width: 150px;


    &:hover {
        opacity: .5;
    }
}
</style>
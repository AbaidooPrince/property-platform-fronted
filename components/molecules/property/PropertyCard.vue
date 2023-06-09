<template>
    <div>
        <b-card :class="$style.propertyCard"  border-variant="light">
                <b-img fluid-grow center rounded :class="$style.propertyImage" :src="image" alt="Wookin Property"></b-img>
                <b-row cols="12" class="pt-3">
                    <b-col cols="auto" class="pr-1 text-center">
                    <b-avatar :src="agent.image ? agent.image : ''">  
                    </b-avatar>
                   
                    </b-col>
                    <b-col cols="" class="pl-0" >   
                        <p :class="$style.agentName">{{ agent.name ? agent.name : '' }}</p>                    
                    
                    <div :class="$style.agentWrapper">
                        <p :class="$style.agentPosition">Estate {{ 'agent.position' }}</p>
                        <span :class="$style.cardIcons">
                            <icon-phone></icon-phone>
                            <icon-message></icon-message>
                            <icon-menu></icon-menu>
                        </span>

                    </div>
                </b-col>
                </b-row>
        </b-card>
    </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import IconMessage from '~/icons/IconMessage.vue'
import IconPhone from '~/icons/IconPhone.vue'
import IconMenu from '~/icons/IconMenu.vue'

export default defineComponent({
    name: 'PropertyCard',
  components: { IconPhone, IconMessage, IconMenu },
    props: {
        image: {
            type: String,
            default: ''
        },
        agent: {
            type: Object,
            default: null
        }
    },
    setup() {
        
    },
})
</script>
<style module scoped>
.propertyCard {
    box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.2), 0 2px 10px 0 rgba(0, 0, 0, 0.052);
}
.agentWrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.agentName {
    margin-bottom: 0;
}

.agentPosition {
    font-size: 0.638rem;
    color: var(--gray);
    margin-bottom: 0;
}
.propertyImage {
    height: 150px;
    width: 100%;
    border-radius: 0.5rem;

}

.cardIcons {
    display: flex;
    align-items: center;
    /* justify-items: space-around; */
}
.cardFooter {
padding-top: 1.25rem;
display: flex;
width: 100%;
}
</style>


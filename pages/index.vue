<template>
    <div>
        <div class="cards">
            <div
                v-if="openIncidents.length > 0" 
                class="card incidents" 
            >
                <div
                    v-for="i in openIncidents"
                    :key="i.id"
                    class="incident_item"
                >
                    <nuxt-link :to="{ name: 'incident-id', params: {id: i.id}}">
                        <IncidentListItem :incident="i" />
                    </nuxt-link>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import IncidentListItem from '@/components/visitors/IncidentListItem.vue'
export default {
    components: { IncidentListItem },
    data: () => ({
        openIncidents: [
            {
                id: 1,
                title: 'Connectivity Issues',
                update_set: [
                    {
                        description: 'We have noticed some connectivity issues',
                        date: '2019-10-02 13:00:12',
                        status: 'Investigating' 
                    }
                ]
            }
        ]
    })
}
</script>

<style>
.cards {
  max-width: 700px;
  margin: -30px auto 20px;
}
.card {
  border-radius: 10px;
  background-color: white;
  padding: 15px 20px;
  box-shadow: 0 0 3px 1px rgba(163,163,163,0.30);
  -webkit-box-shadow: 0 0 3px 1px rgba(163,163,163,0.30);
  font-family: Montserrat;
  font-weight: 300;
}
.incidents > .incident_item {
  margin-bottom: 30px;
  margin-top: 10px;
}
.incidents > .incident_item:last-child {
  margin-bottom: 10px;
}
.incidents {
  margin-bottom: 30px;
}
</style>
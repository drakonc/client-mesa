<template>
  <div class="homeTicket">
    <Ticket/> 
  </div>
</template>

<script>
// @ is an alias to /src
import Ticket from '@/components/ticket/Ticket.vue'

export default {
  name: 'homeTicket',
  components: {
    Ticket
  }
}
</script>
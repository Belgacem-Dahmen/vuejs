<template>
  <button @click="toogleShowModal" > ADD TICKET</button>
  <div v-if="showModal">
    <modal :title=title :content=content @close="closeModal" />
  </div>
  <h1> {{ user.title }}</h1>
  <p>{{ user.nom }}</p>
  <button @click="toogleShowRole">show Role</button>
  <div v-if="showRole">
    <p> {{ user.role }}</p>
  </div>

  <div>
    <ul>
      <li v-for="ticket in filteredTickets ">

        <h3>{{ ticket.titre }}</h3>
        <p> {{ ticket.description }}</p>
        <button> edit </button>
        <button> delete </button>
      </li>

    </ul>

  </div>
</template>



<script>
import Modal from './components/Modal.vue';

export default {

  components: {
    Modal
  },
  data() {
    return {
      showRole: true,
      showModal: false,
      title: "add a Ticket",
      content:"Please fill the needed inputs",

      user: {
        title: "Testa",
        nom: "kacem",
        role: "user"
      },
      tickets: [
        { id: 1, titre: "travaux", type: "inscription", description: "lorem10" },
        { id: 2, titre: "inscription", type: "inscription", description: "lorem11" },
        { id: 3, titre: "use case", type: "inscription", description: "lorem12" },
        { id: 4, titre: "jeux de données ", type: "integration", description: "lorem13" },
        { id: 3, titre: "use case 2 ", type: "inscription", description: "lorem14" },

      ]

    }
  },
  methods: {
    toogleShowRole() {
      this.showRole = !this.showRole
    },
    toogleShowModal() {
      this.showModal = !this.showModal
    },
    closeModal (){
      this.showModal = false
    }
  },
  computed: {
    filteredTickets() {
      return this.tickets.filter((ticket) => ticket.type === "inscription")
    }
  }

}




</script>





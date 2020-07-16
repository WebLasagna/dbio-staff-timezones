<template>
  <div id="app">
    <div class="center">
      <h1>discord.bio staff timezones</h1>
      <h2 v-for="member in staff" :key="member.id"><span class="name">{{ member.name }}</span> - {{ member.time }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      staff: [
        {
          "name": "Lasagna",
          "timezone": "Europe/Paris"
        },
        {
          "name": "audn",
          "timezone": "Europe/Oslo"
        },
        {
          "name": "ven",
          "timezone": "Europe/London"
        },
        {
          "name": "alistair",
          "timezone": "Europe/London"
        },
        {
          "name": "jack!",
          "timezone": "America/New_York"
        },
        {
          "name": "Lina",
          "timezone": "America/Mexico_City"
        },
        {
          "name": "mattt",
          "timezone": "America/Vancouver"
        },
        {
          "name": "Flatbird",
          "timezone": "America/Vancouver"
        }
      ]
    }
  },
  mounted() {
    this.staff.forEach(member => {
      member.time = new Date().toLocaleTimeString('en-US', { timeZone: member.timezone })
    })
    setInterval(() => {
      this.staff.forEach(member => {
        member.time = new Date().toLocaleTimeString('en-US', { timeZone: member.timezone })
      })
    }, 1000)
  }
}
</script>

<style scoped>
h1 {
  font-size: 2.4rem;
  margin-bottom: 50px;
}
h2 {
  font-weight: 500;
}
.name {
  font-weight: 600;
}
</style>
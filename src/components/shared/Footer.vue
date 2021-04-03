<template>
  <footer class="footer">
    <div class="footer-logo">
      <img src="../../assets/images/logo-light.png" alt="ArcH" class="logo"/>
    </div>
    <div class="footer-contact">      
      <p v-for="contact in contactInfo" :key="contact.id" class="contact-info">
        <v-icon small color="#312F2F">{{contact.icon }}</v-icon> {{ contact.info }}
      </p>
    </div>
    <div class="footer-socialmedia">
      <a v-for="socialmedia in socialIcons" :key="socialmedia.name" :href="socialmedia.link" target="_blank" class="social-icon">
        <v-icon color="#312F2F">{{ socialmedia.icon }}</v-icon>
      </a>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data: () => ({
    socialIcons: [
      { name: "facebook", icon: "mdi-facebook", link: "https://www.facebook.com/pisani.da.arch" },
      { name: "youtube", icon: "mdi-youtube", link: "https://www.youtube.com/channel/UCveDIAq9X6cW9O5ZgbqcAAg" },
      { name: "instagram", icon: "mdi-instagram", link: "https://www.instagram.com/pisani.arch/" }
    ],
    contactInfo: [
      { id: 1, info: "Av. Marcos Penteado de Ulhoa Rodrigues, 939 - Torre Jacarandá, 8° andar, Sala 835 - Tamboré Barueri - SP, CEP: 06460-040", icon: "mdi-map-marker"},
      { id: 2, info: "(11) 2844-2272", icon: "mdi-phone"},
      { id: 3, info: "contato@archoffice.tech", icon: "mdi-email"}

    ]
  })
}
</script>

<style scoped>
  .footer {
    display: flex;
    flex-flow: column nowrap;
    justify-content: space-between;
    min-height: 10rem;
    padding: 2rem 6rem;
    font-size: 0.8rem;
    border-bottom: 3px solid #312F2F;
    background: #F1D77E;
    color: #312F2F;
  }
  .footer-logo {
    display: flex;
    justify-content: center;
  }
  .logo {
    width: 4rem;
    margin-bottom: 1.5rem;
    filter: brightness(0.2);
  }
  .footer-contact {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    text-align: center;
  }
  .contact-info {
    margin: 0.5rem 1rem;
  }
  .footer-socialmedia {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    margin-top: 1rem;
  }
  .social-icon {
    margin: 0 0.4rem;
  }
</style>
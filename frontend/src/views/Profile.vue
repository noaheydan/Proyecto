<template>
  <v-container>
    <NavbarP v-if="user.role=='professor'" :p_name="user.name"/>
    <NavbarS v-else :s_name="user.name"/>
  <!--   <v-row justify="center">
      <v-col md="6" sm="6">
        <v-card>
          <v-card-title class="text-uppercase">{{user.role}}</v-card-title>
          <v-card-text>
            <h2>Bienvenido</h2>
            <h4>{{user.email}}</h4>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row> -->
     <v-card
    class="mx-auto"
    max-width="900"
  >
    <v-img
      class="white--text align-end"
      height="300px"
      src="https://cuatro-cero.mx/wp-content/uploads/2020/05/The-Growth-of-IoT-and-Enterprise-DNS.jpg"
    >
      <v-card-title class="justify-center">SISTEMA DE EVALUACIÓN DE SEGURIDAD PARA SOLUCIONES IoT</v-card-title>
    </v-img>

    <v-card-subtitle class="pb-0">
     <h1>Información</h1>
    </v-card-subtitle>
<div></div>
    <v-card-text class="text--primary">
      <div>
        <h4>El internet de las cosas es uno de los temas tecnológicos actuales más importantes debido a que diversos usuarios adquieren e implementan la infraestructura en distintas áreas sin comprender el riesgo de la seguridad a la que están expuestos o el nivel de confianza en la que se encuentran los dispositivos y/o servicios IOT.
Este trabajo propone un modelo para realizar una evaluación del nivel de seguridad de información de dichos dispositivos o servicios por medio de una lista de verificación integral abordando aspectos de seguridad.
Con este modelo se pretende mapear los estándares de seguridad de las organizaciones multinacionales.
En este proyecto vamos a realizar el desarrollo e implementación de un sistema la cual deberá obtener un resultado sobre el nivel de seguridad del dispositivo IoT, caso contrario, si no existe aun la solución, se deberá de cargar manualmente, posteriormente se debe de actualizar automáticamente la nueva solución a todos los usuarios. Con el desarrollo de este proyecto pretende ayudar a varias entidades interesadas en mejorar el nivel de seguridad de la información.
        </h4>
    </div>
    </v-card-text>
  </v-card>
  </v-container>
</template>

<script>
import NavbarP from "@/components/NavbarP";
import NavbarS from "@/components/NavbarS";

export default {
  data: () => ({
    user: { role: "", name: "", email: "" }
  }),
  created: function() {
    this.user = JSON.parse(sessionStorage.getItem("session"));
    if (this.user == null) {
      this.$router.push("/");
    }
  },
    components: {
    NavbarP,
    NavbarS
  }
};
</script>
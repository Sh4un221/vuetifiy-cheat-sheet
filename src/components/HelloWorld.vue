<template>
  <v-app>
    <v-main>
      <div class="container">
        <h1 class="mb-8">Cheat Sheet de Vuetify v2 para Vue 2</h1>

        <h2 class="mb-4">Configuración inicial</h2>
        <v-card class="mb-8">
          <v-card-text>
            <ol>
              <li>Instala Vue CLI y Vuetify:
                <pre><code>npm install -g @vue/cli
vue create my-app
cd my-app
vue add vuetify</code></pre>
              </li>
              <li>Selecciona la opción "Default (recommended)" cuando se te pregunte por el estilo de Vuetify.</li>
              <li>Agrega la siguiente configuración a <code>vue.config.js</code> para hacer que Vuetify funcione con Node 12.18:
                <pre><code>module.exports = {
  transpileDependencies: [
    'vuetify'
  ]
}</code></pre>
              </li>
            </ol>
          </v-card-text>
        </v-card>

        <h2 class="mb-4">Componentes principales</h2>
        <v-row>
          <v-col cols="12" sm="6" md="4" v-for="component in components" :key="component.title">
            <v-card class="component-card">
              <v-card-title>{{ component.title }}</v-card-title>
              <v-card-text class="text-center">
                <p>{{ component.description }}</p>
                <div v-if="component.example" class="mt-4">
                  <h3 class="mb-2">Ejemplo</h3>
                  <pre><code>{{ component.example }}</code></pre>
                </div>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <h2 class="mb-4">Otros componentes útiles</h2>
        <v-row>
          <v-col cols="12" sm="6" md="4" v-for="component in otherComponents" :key="component.title">
            <v-card class="component-card">
              <v-card-title>{{ component.title }}</v-card-title>
              <v-card-text class="text-center">
                <p>{{ component.description }}</p>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <h2 class="mb-4">Uso de Flexbox y Grid</h2>
        <v-card class="mb-8">
          <v-card-text>
            <h3 class="mb-2">Flexbox</h3>
            <p>Vuetify proporciona un sistema de Flexbox basado en clases de utilidad que puedes usar para controlar la disposición de tus elementos. Algunas clases útiles son:</p>
            <ul>
              <li><code>d-flex</code>: Aplica un display de tipo Flexbox</li>
              <li><code>flex-row</code>, <code>flex-column</code>: Establece la dirección del Flexbox</li>
              <li><code>justify-*</code>: Controla el alineamiento horizontal de los elementos</li>
              <li><code>align-*</code>: Controla el alineamiento vertical de los elementos</li>
              <li><code>flex-grow-*</code>, <code>flex-shrink-*</code>: Controla el crecimiento y encogimiento de los elementos</li>
            </ul>
            <div class="flexbox-example">
              <div class="d-flex flex-row justify-center align-center" style="height: 200px;">
                <div class="pa-4 bg-primary white--text">Elemento 1</div>
                <div class="pa-4 bg-secondary white--text">Elemento 2</div>
                <div class="pa-4 bg-primary white--text">Elemento 3</div>
              </div>
            </div>

            <h3 class="mb-2">Grid</h3>
            <p>Vuetify también incluye un sistema de Grid basado en Bootstrap. Puedes usar las siguientes clases para crear una cuadrícula:</p>
            <ul>
              <li><code>v-row</code>: Contenedor de la fila</li>
              <li><code>v-col</code>: Columna individual</li>
              <li><code>cols="*"</code>: Establece el ancho de la columna en pantallas pequeñas</li>
              <li><code>sm="*"</code>, <code>md="*"</code>, <code>lg="*"</code>, <code>xl="*"</code>: Establece el ancho de la columna en diferentes tamaños de pantalla</li>
              <li><code>offset-*</code>: Agrega un margen izquierdo a la columna</li>
            </ul>
            <div class="grid-example">
              <v-row>
                <v-col cols="12" sm="6" md="4" class="pa-2">
                  <div class="bg-primary white--text pa-4">Columna 1</div>
                </v-col>
                <v-col cols="12" sm="6" md="4" class="pa-2">
                  <div class="bg-secondary white--text pa-4">Columna 2</div>
                </v-col>
                <v-col cols="12" sm="6" md="4" class="pa-2">
                  <div class="bg-primary white--text pa-4">Columna 3</div>
                </v-col>
              </v-row>
            </div>
          </v-card-text>
        </v-card>
      </div>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'VuetifyCheatSheet',
  data() {
    return {
      components: [
        {
          title: 'v-app',
          description: 'Componente contenedor principal de la aplicación. Debe envolver todo el contenido.'
        },
        {
          title: 'v-app-bar',
          description: 'Barra de navegación superior. Permite agregar botones, menús, iconos, etc.'
        },
        {
          title: 'v-main',
          description: 'Área de contenido principal. Debe estar dentro de "v-app".'
        },
        {
          title: 'v-card',
          description: 'Contenedor con estilos de tarjeta. Puede contener títulos, imágenes, texto, etc.'
        },
        {
          title: 'v-btn',
          description: 'Botón con estilos de Vuetify. Admite modificadores para cambiar su aspecto.',
          example: '<v-btn color="primary">Click me</v-btn>'
        },
        {
          title: 'v-icon',
          description: 'Muestra un icono de Material Design. Usa prefijo "mdi-" para los iconos.',
          example: '<v-icon>mdi-home</v-icon>'
        },
        {
          title: 'v-form',
          description: 'Contenedor para formularios con validación integrada.'
        },
        {
          title: 'v-text-field',
          description: 'Campo de entrada de texto con estilos de Vuetify. Admite validación, máscaras, etc.',
          example: '<v-text-field label="Nombre" v-model="name"></v-text-field>'
        }
      ],
      otherComponents: [
        {
          title: 'v-navigation-drawer',
          description: 'Drawer o menú lateral'
        },
        {
          title: 'v-footer',
          description: 'Pie de página de la aplicación'
        },
        {
          title: 'v-list',
          description: 'Lista con estilos de Vuetify'
        },
        {
          title: 'v-dialog',
          description: 'Cuadro de diálogo modal'
        },
        {
          title: 'v-snackbar',
          description: 'Notificación emergente'
        },
        {
          title: 'v-progress-circular',
          description: 'Indicador de progreso circular'
        }
      ]
    }
  }
}
</script>

<style>
.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 2rem;
}
.component-card {
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  background-color: #F5F5F5;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}
.component-card:hover {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}
.component-card .v-card__title {
  font-size: 18px;
  font-weight: bold;
  color: #1976D2;
  margin-bottom: 8px;
}
.component-card .v-card__text {
  font-size: 16px;
  color: #555;
}
pre {
  background-color: #F5F5F5;
  padding: 12px;
  border-radius: 4px;
  font-size: 14px;
  overflow-x: auto;
}
.flexbox-example, .grid-example {
  background-color: black;
  padding: 16px;
  border-radius: 4px;
}
</style>
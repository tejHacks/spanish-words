
<template>
  <div class="app-container">
    <h1 class=""title> Learn Spanish Words</h1>
    <div class="word-card" v-if="currentWord">
      <p class="spanish-word">{{ currentWord.word }}</p>
      <p class="english-translation">{{ currentWord.translation }}</p>
      <button @click="previousWord">⏮️ Previous Word</button>
      <button @click="speakWord">🔊 Pronounce</button>
      <button @click="nextWord">⏭️ Next Word</button>
    </div>
  </div>
</template>

<script>

export default{
data(){
  return{
    words: [
  { word: "Hola", translation: "Hello" },
  { word: "Gracias", translation: "Thank you" },
  { word: "Amigo", translation: "Friend" },
  { word: "Comida", translation: "Food" },
  { word: "Baile", translation: "Dance" },
  { word: "Agua", translation: "Water" },
  { word: "Casa", translation: "House" },
  { word: "Libro", translation: "Book" },
  { word: "Sol", translation: "Sun" },
  { word: "Luna", translation: "Moon" },
  { word: "Árbol", translation: "Tree" },
  { word: "Flor", translation: "Flower" },
  { word: "Perro", translation: "Dog" },
  { word: "Gato", translation: "Cat" },
  { word: "Coche", translation: "Car" },
  { word: "Ciudad", translation: "City" },
  { word: "País", translation: "Country" },
  { word: "Música", translation: "Music" },
  { word: "Tiempo", translation: "Time" },
  { word: "Trabajo", translation: "Work" },
  { word: "Dinero", translation: "Money" },
  { word: "Familia", translation: "Family" },
  { word: "Padre", translation: "Father" },
  { word: "Madre", translation: "Mother" },
  { word: "Hermano", translation: "Brother" },
  { word: "Hermana", translation: "Sister" },
  { word: "Niño", translation: "Child" },
  { word: "Mujer", translation: "Woman" },
  { word: "Hombre", translation: "Man" },
  { word: "Ropa", translation: "Clothes" },
  { word: "Zapatos", translation: "Shoes" },
  { word: "Sombrero", translation: "Hat" },
  { word: "Mesa", translation: "Table" },
  { word: "Silla", translation: "Chair" },
  { word: "Puerta", translation: "Door" },
  { word: "Ventana", translation: "Window" },
  { word: "Calle", translation: "Street" },
  { word: "Playa", translation: "Beach" },
  { word: "Montaña", translation: "Mountain" },
  { word: "Río", translation: "River" },
  { word: "Mar", translation: "Sea" },
  { word: "Cielo", translation: "Sky" },
  { word: "Nube", translation: "Cloud" },
  { word: "Lluvia", translation: "Rain" },
  { word: "Nieve", translation: "Snow" },
  { word: "Viento", translation: "Wind" },
  { word: "Fuego", translation: "Fire" },
  { word: "Tierra", translation: "Earth" },
  { word: "Corazón", translation: "Heart" },
  { word: "Cabeza", translation: "Head" },
  { word: "Mano", translation: "Hand" },
  { word: "Pie", translation: "Foot" },
  { word: "Ojo", translation: "Eye" },
  { word: "Boca", translation: "Mouth" },
  { word: "Nariz", translation: "Nose" },
  { word: "Oreja", translation: "Ear" },
  { word: "Pelo", translation: "Hair" },
  { word: "Piel", translation: "Skin" },
  { word: "Salud", translation: "Health" },
  { word: "Enfermo", translation: "Sick" },
  { word: "Feliz", translation: "Happy" },
  { word: "Triste", translation: "Sad" },
  { word: "Cansado", translation: "Tired" },
  { word: "Hambre", translation: "Hunger" },
  { word: "Sed", translation: "Thirst" },
  { word: "Calor", translation: "Heat" },
  { word: "Frío", translation: "Cold" },
  { word: "Dormir", translation: "Sleep" },
  { word: "Despertar", translation: "Wake up" },
  { word: "Comprar", translation: "Buy" },
  { word: "Vender", translation: "Sell" },
  { word: "Abrir", translation: "Open" },
  { word: "Cerrar", translation: "Close" },
  { word: "Entrar", translation: "Enter" },
  { word: "Salir", translation: "Exit" },
  { word: "Subir", translation: "Go up" },
  { word: "Bajar", translation: "Go down" },
  { word: "Ir", translation: "Go" },
  { word: "Venir", translation: "Come" },
  { word: "Tener", translation: "Have" },
  { word: "Ser", translation: "Be" },
  { word: "Estar", translation: "Be (location/condition)" },
  { word: "Hacer", translation: "Do/Make" },
  { word: "Decir", translation: "Say" },
  { word: "Ver", translation: "See" },
  { word: "Oír", translation: "Hear" },
  { word: "Pensar", translation: "Think" },
  { word: "Saber", translation: "Know" },
  { word: "Poder", translation: "Can" },
  { word: "Querer", translation: "Want" },
  { word: "Dar", translation: "Give" },
  { word: "Tomar", translation: "Take" },
  { word: "Poner", translation: "Put" },
  { word: "Llamar", translation: "Call" },
  { word: "Buscar", translation: "Search" },
  { word: "Encontrar", translation: "Find" },
  { word: "Ayudar", translation: "Help" },
  { word: "Preguntar", translation: "Ask" },
  { word: "Responder", translation: "Answer" },
  { word: "Hablar", translation: "Speak" },
  { word: "Escuchar", translation: "Listen" },
  { word: "Leer", translation: "Read" },
  { word: "Escribir", translation: "Write" },
  { word: "Aprender", translation: "Learn" },
  { word: "Enseñar", translation: "Teach" },
  { word: "Viajar", translation: "Travel" },
  { word: "Jugar", translation: "Play" },
  { word: "Cocinar", translation: "Cook" },
  { word: "Limpiar", translation: "Clean" },
  { word: "Amar", translation: "Love" },
  { word: "Odiar", translation: "Hate" },
  { word: "Reír", translation: "Laugh" },
  { word: "Llorar", translation: "Cry" },
  { word: "Correr", translation: "Run" },
  { word: "Caminar", translation: "Walk" },
  { word: "Saltar", translation: "Jump" },
  { word: "Nadar", translation: "Swim" },
  { word: "Volar", translation: "Fly" },
  { word: "Conducir", translation: "Drive" },
  { word: "Cortar", translation: "Cut" },
  { word: "Pegar", translation: "Stick" },
  { word: "Romper", translation: "Break" },
  { word: "Construir", translation: "Build" },
  { word: "Reparar", translation: "Repair" },
  { word: "Cambiar", translation: "Change" },
  { word: "Guardar", translation: "Save" },
  { word: "Perder", translation: "Lose" },
  { word: "Ganar", translation: "Win" },
  { word: "Empezar", translation: "Start" },
  { word: "Terminar", translation: "End" },
  { word: "Continuar", translation: "Continue" },
  { word: "Recordar", translation: "Remember" },
  { word: "Olvidar", translation: "Forget" },
  { word: "Mostrar", translation: "Show" },
  { word: "Hablar", translation: "Speak" },
  { word: "Escuchar", translation: "Listen" },
  { word: "Leer", translation: "Read" },
  { word: "Escribir", translation: "Write" },
  { word: "Aprender", translation: "Learn" },
  { word: "Enseñar", translation: "Teach" },
  { word: "Viajar", translation: "Travel" },
  { word: "Jugar", translation: "Play" },
  { word: "Cocinar", translation: "Cook" },
  { word: "Limpiar", translation: "Clean" },
  { word: "Amar", translation: "Love" },
  { word: "Odiar", translation: "Hate" },
  { word: "Reír", translation: "Laugh" },
  { word: "Llorar", translation: "Cry" },
  { word: "Correr", translation: "Run" },
  { word: "Caminar", translation: "Walk" },
  { word: "Saltar", translation: "Jump" },
  { word: "Nadar", translation: "Swim" },
  { word: "Volar", translation: "Fly" },
  { word: "Conducir", translation: "Drive" },
  { word: "Cortar", translation: "Cut" },
  { word: "Pegar", translation: "Stick" },
  { word: "Romper", translation: "Break" },
  { word: "Construir", translation: "Build" },
  { word: "Reparar", translation: "Repair" },
  { word: "Cambiar", translation: "Change" },
  { word: "Guardar", translation: "Save" },
  { word: "Perder", translation: "Lose" },
  { word: "Ganar", translation: "Win" },
  { word: "Empezar", translation: "Start" },
  { word: "Terminar", translation: "End" },
  { word: "Continuar", translation: "Continue" },
  { word: "Recordar", translation: "Remember" },
  { word: "Olvidar", translation: "Forget" },
  { word: "Mostrar", translation: "Show" },
  { word: "Esconder", translation: "Hide" },
  { word: "Creer", translation: "Believe" },
  { word: "Dudar", translation: "Doubt" },
  { word: "Esperar", translation: "Wait/Hope" },
  { word: "Necesitar", translation: "Need" },
  { word: "Usar", translation: "Use" },
  { word: "Dejar", translation: "Leave/Let" },
  { word: "Llevar", translation: "Carry/Wear" },
  { word: "Traer", translation: "Bring" },
  { word: "Sentir", translation: "Feel" },
  { word: "Doler", translation: "Hurt" },
  { word: "Gustar", translation: "Like" },
  { word: "Preferir", translation: "Prefer" },
  { word: "Permitir", translation: "Allow" },
  { word: "Prohibir", translation: "Forbid" },
  { word: "Aceptar", translation: "Accept" },
  { word: "Rechazar", translation: "Reject" },
  { word: "Elegir", translation: "Choose" },
  { word: "Decidir", translation: "Decide" },
  { word: "Intentar", translation: "Try" },
  { word: "Lograr", translation: "Achieve" },
  { word: "Conseguir", translation: "Get" },
  { word: "Ofrecer", translation: "Offer" },
  { word: "Recibir", translation: "Receive" },
  { word: "Compartir", translation: "Share" },
  { word: "Añadir", translation: "Add" },
  { word: "Quitar", translation: "Remove" },
  { word: "Aumentar", translation: "Increase" },
  { word: "Disminuir", translation: "Decrease" },
  { word: "Explicar", translation: "Explain" },
  { word: "Comprender", translation: "Understand" },
  { word: "Record", translation: "Remember" },
  { word: "Olvidar", translation: "Forget" },
  { word: "Conocer", translation: "Know (people/places)" },
  { word: "Adivinar", translation: "Guess" },
  { word: "Descubrir", translation: "Discover" },
  { word: "Inventar", translation: "Invent" },
  { word: "Proteger", translation: "Protect" },
  { word: "Atacar", translation: "Attack" },
  { word: "Defender", translation: "Defend" },
  { word: "Luchar", translation: "Fight" },
  { word: "Ganar", translation: "Win" },
  { word: "Perder", translation: "Lose" },
  { word: "Celebrar", translation: "Celebrate" },
  { word: "Disfrutar", translation: "Enjoy" },
  { word: "Preocuparse", translation: "Worry" },
  { word: "Relajarse", translation: "Relax" },
  { word: "Descansar", translation: "Rest" },
  { word: "Divertirse", translation: "Have fun" },
  { word: "Aburrirse", translation: "Get bored" },
  { word: "Sorprender", translation: "Surprise" },
  { word: "Asustar", translation: "Scare" },
  { word: "Molestar", translation: "Bother" },
  { word: "Ayudar", translation: "Help" },
  { word: "Apoyar", translation: "Support" },
  { word: "Confiar", translation: "Trust" },
  { word: "Mentir", translation: "Lie" },
  { word: "Prometer", translation: "Promise" },
  { word: "Cumplir", translation: "Fulfill" },
  { word: "Organizar", translation: "Organize" },
  { word: "Planificar", translation: "Plan" },
  { word: "Construir", translation: "Build" },
  { word: "Destruir", translation: "Destroy" },
  { word: "Investigar", translation: "Investigate" },
  { word: "Analizar", translation: "Analyze" },
  { word: "Evaluar", translation: "Evaluate" },
  { word: "Comparar", translation: "Compare" },
  { word: "Medir", translation: "Measure" },
  { word: "Calcular", translation: "Calculate" },
  { word: "Resolver", translation: "Solve" },
  { word: "Solucionar", translation: "Solve" },
  { word: "Arreglar", translation: "Fix" },
  { word: "Diseñar", translation: "Design" },
  { word: "Crear", translation: "Create" },
  { word: "Producir", translation: "Produce" },
  { word: "Distribuir", translation: "Distribute" },
  { word: "Exportar", translation: "Export" },
  { word: "Importar", translation: "Import" },
  { word: "Negociar", translation: "Negotiate" },
  { word: "Acordar", translation: "Agree" },
  { word: "Discutir", translation: "Discuss" },
  { word: "Argumentar", translation: "Argue" },
  { word: "Convencer", translation: "Convince" },
  { word: "Influir", translation: "Influence" },
  { word: "Motivar", translation: "Motivate" },
  { word: "Inspirar", translation: "Inspire" },
  { word: "Guiar", translation: "Guide" },
  { word: "Dirigir", translation: "Direct" },
  { word: "Administrar", translation: "Manage" },
  { word: "Controlar", translation: "Control" },
  { word: "Supervisar", translation: "Supervise" },
  { word: "Revisar", translation: "Review" },
  { word: "Corregir", translation: "Correct" },
  { word: "Aprobar", translation: "Approve" },
  { word: "Rechazar", translation: "Reject" },
  { word: "Firmar", translation: "Sign" },
  { word: "Enviar", translation: "Send" },
  { word: "Recibir", translation: "Receive" },
  { word: "Entregar", translation: "Deliver" },
  { word: "Recoger", translation: "Pick up" },
  { word: "Almacenar", translation: "Store" },
  { word: "Probar", translation: "Test" },
  { word: "Experimentar", translation: "Experiment" },
  { word: "Observar", translation: "Observe" },
  { word: "Notar", translation: "Notice" },
  { word: "Reconocer", translation: "Recognize" },
  { word: "Identificar", translation: "Identify" },
  { word: "Clasificar", translation: "Classify" },
  { word: "Organizar", translation: "Organize" },
  { word: "Planificar", translation: "Plan" },
  { word: "Programar", translation: "Schedule" },
  { word: "Reservar", translation: "Reserve" },
  { word: "Cancelar", translation: "Cancel" },
  { word: "Confirmar", translation: "Confirm" },
  { word: "Aceptar", translation: "Accept" },
  { word: "Rechazar", translation: "Reject" },
  { word: "Permitir", translation: "Allow" },
  { word: "Prohibir", translation: "Forbid" },
  { word: "Exigir", translation: "Demand" },
  { word: "Requerir", translation: "Require" },
  { word: "Sugerir", translation: "Suggest" },
  { word: "Recomendar", translation: "Recommend" },
  { word: "Aconsejar", translation: "Advise" },
  { word: "Informar", translation: "Inform" },
  { word: "Comunicar", translation: "Communicate" },
  { word: "Expresar", translation: "Express" },
  { word: "Indicar", translation: "Indicate" },
  { word: "Señalar", translation: "Point out" },
  { word: "Demostrar", translation: "Demonstrate" },
  { word: "Probar", translation: "Prove" },
  { word: "Justificar", translation: "Justify" },
  { word: "Excusar", translation: "Excuse" },
  { word: "Perdonar", translation: "Forgive" },
  { word: "Agradecer", translation: "Thank" },
  { word: "Felicitar", translation: "Congratulate" },
  { word: "Criticar", translation: "Criticize" },
  { word: "Alabar", translation: "Praise" },
  { word: "Admirar", translation: "Admire" },
  { word: "Respetar", translation: "Respect" },
  { word: "Ignorar", translation: "Ignore" },
  { word: "Despreciar", translation: "Despise" },
  { word: "Confiar", translation: "Trust" },
  { word: "Desconfiar", translation: "Distrust" },
  { word: "Apoyar", translation: "Support" },
  { word: "Oponerse", translation: "Oppose" },
  { word: "Colaborar", translation: "Collaborate" },
  { word: "Cooperar", translation: "Cooperate" },
  { word: "Compartir", translation: "Share" },
  { word: "Distribuir", translation: "Distribute" },
  { word: "Reunir", translation: "Gather" },
  { word: "Separar", translation: "Separate" },
  { word: "Unir", translation: "Unite" },
  { word: "Conectar", translation: "Connect" },
  { word: "Desconectar", translation: "Disconnect" },
  { word: "Integrar", translation: "Integrate" },
  { word: "Excluir", translation: "Exclude" },
  { word: "Adaptar", translation: "Adapt" },
  { word: "Ajustar", translation: "Adjust" },
  { word: "Modificar", translation: "Modify" },
  { word: "Transformar", translation: "Transform" },
  { word: "Evolucionar", translation: "Evolve" },
  { word: "Desarrollar", translation: "Develop" },
  { word: "Crecer", translation: "Grow" },
  { word: "Madurar", translation: "Mature" },
  { word: "Mejorar", translation: "Improve" },
  { word: "Empeorar", translation: "Worsen" },
  { word: "Avanzar", translation: "Advance" },
  { word: "Retroceder", translation: "Retreat" },
  { word: "Progresar", translation: "Progress" },
  { word: "Estancar", translation: "Stagnate" },
  { word: "Acelerar", translation: "Accelerate" },
  { word: "Frenar", translation: "Brake/Slow down" },
  { word: "Mantener", translation: "Maintain" },
  { word: "Conservar", translation: "Preserve" },
  { word: "Proteger", translation: "Protect" },
  { word: "Defender", translation: "Defend" },
  { word: "Atacar", translation: "Attack" },
  { word: "Invadir", translation: "Invade" },
  { word: "Resistir", translation: "Resist" },
  { word: "Rendirse", translation: "Surrender" },
  { word: "Liberar", translation: "Liberate" },
  { word: "Capturar", translation: "Capture" },
  { word: "Escapar", translation: "Escape" },
  { word: "Esconder", translation: "Hide" },
  { word: "Revelar", translation: "Reveal" },
  { word: "Descubrir", translation: "Discover" },
  { word: "Ocultar", translation: "Conceal" },
  { word: "Mostrar", translation: "Show" },
  { word: "Demostrar", translation: "Demonstrate" },
  { word: "Probar", translation: "Prove" },
  { word: "Examinar", translation: "Examine" },
  { word: "Inspeccionar", translation: "Inspect" },
  { word: "Investigar", translation: "Investigate" },
  { word: "Analizar", translation: "Analyze" },
  { word: "Sintetizar", translation: "Synthesize" },
  { word: "Clasificar", translation: "Classify" },
  { word: "Categorizar", translation: "Categorize" },
  { word: "Ordenar", translation: "Order" },
  { word: "Organizar", translation: "Organize" },
  { word: "Planificar", translation: "Plan" },
  { word: "Programar", translation: "Schedule" },
  { word: "Ejecutar", translation: "Execute" },
  { word: "Implementar", translation: "Implement" },
  { word: "Realizar", translation: "Perform" },
  { word: "Completar", translation: "Complete" },
  { word: "Finalizar", translation: "Finalize" },
  { word: "Culminar", translation: "Culminate" },
  { word: "Iniciar", translation: "Initiate" },
  { word: "Empezar", translation: "Begin" },
  { word: "Terminar", translation: "End" },
  { word: "Continuar", translation: "Continue" },
  { word: "Interrumpir", translation: "Interrupt" },
  { word: "Reanudar", translation: "Resume" },
  { word: "Suspender", translation: "Suspend" },
  { word: "Cancelar", translation: "Cancel" },
  { word: "Confirmar", translation: "Confirm" },
  { word: "Verificar", translation: "Verify" },
  { word: "Validar", translation: "Validate" },
  { word: "Aprobar", translation: "Approve" },
  { word: "Rechazar", translation: "Reject" },
  { word: "Permitir", translation: "Allow" },
  { word: "Prohibir", translation: "Forbid" },
  { word: "Exigir", translation: "Demand" },
  { word: "Requerir", translation: "Require" },
  { word: "Sugerir", translation: "Suggest" },
  { word: "Recomendar", translation: "Recommend" },
  { word: "Aconsejar", translation: "Advise" },
  { word: "Informar", translation: "Inform" },
  { word: "Comunicar", translation: "Communicate" },
  { word: "Expresar", translation: "Express" },
  { word: "Indicar", translation: "Indicate" },
  { word: "Señalar", translation: "Point out" },
  { word: "Demostrar", translation: "Demonstrate" },
  { word: "Probar", translation: "Prove" },
  { word: "Justificar", translation: "Justify" },
  { word: "Excusar", translation: "Excuse" },
  { word: "Perdonar", translation: "Forgive" },
  { word: "Agradecer", translation: "Thank" },
  { word: "Felicitar", translation: "Congratulate" },
  { word: "Criticar", translation: "Criticize" },
  { word: "Alabar", translation: "Praise" },
  { word: "Admirar", translation: "Admire" },
  { word: "Respetar", translation: "Respect" },
  { word: "Ignorar", translation: "Ignore" },
  { word: "Despreciar", translation: "Despise" },
  { word: "Confiar", translation: "Trust" },
  { word: "Desconfiar", translation: "Distrust" },
  { word: "Apoyar", translation: "Support" },
  { word: "Oponerse", translation: "Oppose" },
  { word: "Colaborar", translation: "Collaborate" },
  { word: "Cooperar", translation: "Cooperate" },
  { word: "Compartir", translation: "Share" },
  { word: "Distribuir", translation: "Distribute" }
  ],
  currentIndex:0
  };
},
computed: {
  currentWord(){
    return this.words[this.currentIndex];
  }
},
methods:{
// the speakWord function goes here and allows the user to hear the word
speakWord() {
  window.speechSynthesis.cancel(); // Clear any ongoing speech
  const utterance = new SpeechSynthesisUtterance(this.words[this.currentIndex].word);
  utterance.lang = "es-ES";
  window.speechSynthesis.speak(utterance);
}
,
// get the next word in the list
nextWord() {
this.currentIndex = (this.currentIndex + 1) % this.words.length;
},
previousWord() {
  this.currentIndex = (this.currentIndex - 1 + this.words.length) % this.words.length;
}

}
};
</script>

<!-- the styles -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Lobster&family=Bebas+Neue&family=Righteous&display=swap');

body {
  background: url('your-guitar-image.jpg') no-repeat center center fixed;
  background-size: cover;
  font-family: 'Lobster', cursive;
  color: #1E1E1E;
  text-align: center;
  background: url('/guitar.jpg') cover no-repeat fixed;
  /* @/assets/guitar-image.jpg') no-repeat center center fixed; */
}

h1 {
  font-family: 'Righteous', sans-serif;
  color: #D72638;
  font-size: 48px;
  text-transform: uppercase;
}

span {
  color: #F8C537;
}

button {
  background: linear-gradient(135deg, #D72638, #FF6600);
  border: none;
  color: white;
  font-size: 20px;
  font-family: 'Bebas Neue', sans-serif;
  padding: 10px 20px;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.3s;
  margin:3px;
}

button:hover {
  background: linear-gradient(135deg, #FF6600, #D72638);
  transform: scale(1.1);
}

</style>
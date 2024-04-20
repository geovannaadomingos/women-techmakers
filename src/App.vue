<template>
  <div id="app">
    <header>
      <img alt="Vue logo" src="./assets/WTM-IWD-2024.png">
      <h1>Oficina de Vue.js do International Women's Day 2024</h1>
      <p>Essa é uma página criada durante a oficina do International Women's Day 2024 para praticar Vue.js.
        Aqui, mostraremos o perfil de algumas mulheres que impactaram ou impactam o ecossistema de tecnologia</p>
      <button @click="toggleList">Clique aqui para conferir</button>
    </header>

    <main>
      <div v-if="showList" class="profile-cards">
        <ProfileComponent v-for="woman in women" :key="woman.id" :woman="woman" />
      </div>
    </main>

    <footer>
      <p>&copy; 2024 Geovanna Domingos</p>
    </footer>
  </div>
</template>

<script>
import ProfileComponent from './components/ProfileComponent.vue'

export default {
  name: 'App',
  components: {
    ProfileComponent
  },
  data() {
    return {
      showList: false,
      women: [
        { id: 1, name: 'Kizzy Terra', position: 'Professora', company: 'Inteli - Instituto de Tecnologia e Liderança', bio: 'Cientista de Dados e co-criadora do canal Programação Dinâmica no YouTube. Bacharel em Engenharia de Computação pelo Instituto Militar de Engenharia (IME). mestre em Matemática Aplicada pela FGV-RJ. e doutoranda no TIDD(PUC-SP). Além disso, trabalhei como analista de dados de utilidade pública na Fundacao Getulio Vargas e no Instituto de Pesquisa Econômica Aplicada, e fui cientista de dados sênior na Cyberlabs.', photo: 'https://wpcdn.idp.edu.br/idpsiteportal/2021/05/kizzy-terra.jpg' },
        { id: 2, name: 'Camila AChutti', position: 'CEO', company: 'Mastertech', bio: 'Camila Achutti é Fundadora da Mastertech, uma startup de educação eleita como a mais atraente do país em 2018. Criadora do portal “Mulheres na Computação”, uma das primeiras e mais importantes e influentes iniciativas de inclusão das mulheres no cenário contemporâneo de tecnologia.', photo: 'https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQiXBYV0Q37WeRIS41nIwYyf_L9n-y8PkEnyZR542cJxZIbkFQW' },
        { id: 3, name: 'Silvana Bahia', position: 'Codiretora executiva', company: 'Olabi', bio: 'Silvana Helena Gomes Bahia, também conhecida como Sil Bahia, é comunicadora social e empreendedora social. Importante nome nas áreas de tecnologia e inovação, Sil Bahia é codiretora executiva do Olabi, organização social focada em inovação social, tecnologia e diversidade.', photo: 'https://pbs.twimg.com/media/Efzgf-qWoAIsuIM.jpg' },
        { id: 4, name: 'Nina da Hora', position: 'Escritora', company: 'MIT Technology Review', bio: 'Conhecida como Nina da Hora, ela integrou a Comissão de Transparência das Eleições (CTE) 2022, do Tribunal Superior Eleitoral (TSE) e faz parte do conselho de segurança da rede social TikTok no Brasil. Também está presente na mídia especializada, como o periódico MIT Technology Review Brasil e o site UOL tilt, como colunista sobre temas relacionados à IA e ética.', photo: 'https://conteudo.imguol.com.br/c/noticias/47/2020/07/12/ana-carolina-da-hora-hackear-o-racismo-1594591816588_v2_1x1.jpg' },
        { id: 2, name: 'Soraya Roberta', position: 'MSc - PhD Student', company: 'Universidade Federal de Pernambuco', bio: 'Doutoranda no Programa de Pós-graduação em Ciência da Computação no Centro de Informática da Universidade Federal de Pernambuco. Mestre em Inovação em Tecnologias Educacionais pelo Instituto Metrópole Digital. Graduada em Bacharelado em Sistemas de Informação pela Universidade Federal do Rio Grande do Norte. Técnica em Informática formada pelo Instituto Federal de Educação, Ciência e Tecnologia do Rio grande do Norte.', photo: 'https://media.licdn.com/dms/image/D4D03AQHgmIqJZhtxWA/profile-displayphoto-shrink_200_200/0/1675471580757?e=2147483647&v=beta&t=TGwbq-6hiXT2RkjTCQbVcW4aSnogDAon-YPOP6gm35w' },
      ]
    }
  },
  methods: {
    toggleList() {
      this.showList = !this.showList;
    }
  }
}
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: 'Arial', sans-serif;
  text-align: center;
  color: #202124;
}

header {
  background-color: #54a7ed;
  padding: 40px 0;
  color: #fff;
}

header h1 {
  font-size: 32px;
  margin-bottom: 20px;
}

header p {
  font-size: 18px;
  margin-bottom: 30px;
}

header img {
  width: 180px;
}

main {
  flex: 1;
  top: 0;
  padding: 100px 0;
}

footer {
  background-color: #d1ece3;
  padding: 20px 0;
  bottom: 0;
  width: 100%;
  z-index: 1000;
}

button {
  background-color: #00b698;
  color: #fff;
  border: none;
  padding: 10px 20px;
  font-size: 18px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

button:hover {
  background-color: #0f7c67;
}

.profile-cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}
</style>

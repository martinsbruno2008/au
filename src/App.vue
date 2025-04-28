<!-- eslint-disable no-undef -->
<script setup>

import { ref, computed } from 'vue';


const produtos = ref([
  {
    id: 1,
    titulo: 'Harry Potter',
    resenha: 'É sobre um menino que descobre que é um bruxo e vai para uma escola de magia.',
    preco: 307.93,
    capa: 'https://m.media-amazon.com/images/I/71gOCNRA9nL._SL1200_.jpg',
    botao: 'Adicionar ao carrinho',
    link: 'https://www.amazon.com.br/Cole%C3%A7%C3%A3o-Harry-Potter-7-volumes/dp/8532512941/ref=sr_1_1?dib=eyJ2IjoiMSJ9.bXfOBX6fELAw5044JLatteAsBwrTUjV4Ymw7vKUjMv-jaP0r7kWcraMYInEOx8Ucv57yNM7sYU7ZZCtTGiP83SMvdBvUdoXSxK1oDzhSio1n1U6JjPWMVr6BUz8E4QfNU5dsa-zlLIN8tj-H-N3oTPosjHnn83ee3NvlhtGwfx_pEpv7grVZ32r15wJsWSvTSjkRXQJzOAUZBTCah6bzr6UuwrJ0ixAbcxFSGboEL1H2xI0v-2QWc9izoC7OAny5dDwUMgWSP5syw_KuzXuQp00ob1ICLEsXDnXPSPVzbZA.YMWWtWbHIoNyfmMDQ797RnJt5oGbT3nUEpYY8lhAmw8&dib_tag=se&keywords=harry+potter+box&qid=1745496653&sr=8-1&ufe=app_do%3Aamzn1.fos.fcd6d665-32ba-4479-9f21-b774e276a678',
        mercadoLivre: 'https://produto.mercadolivre.com.br/MLB-4533855374-box-harry-potter-serie-completa-07-volumes-_JM',
    shopee: 'https://shopee.com.br/Box-Harry-Potter-7-Volumes-i.12345678.1234567890'
  },
  {
    id: 2,
    titulo: 'Diario de um banana',
    resenha: 'É sobre um menino que escreve um diário e vive várias aventuras engraçadas.',
    preco: 39.90,
    capa: 'https://m.media-amazon.com/images/I/71fWaI5myqL._SL1350_.jpg',
    botao: 'Adicionar ao carrinho',
    link: 'https://www.amazon.com.br/Di%C3%A1rio-Um-Banana-Jeff-Kinney/dp/8576831309/ref=sr_1_1?dib=eyJ2IjoiMSJ9.-UcFik4JqJBnzS_xQ3H36Lw5sDUqDlIkeFAZQh3piD0XzaSuj0t99Ia_R4Oy2B9csbyYF0eIlNFgAy8V-JyRXcXWM6qnnMOt62PE2Bb74QRlcSuBDla4NTL3eHOdpIaI4-Ya1XhzwefOoRCx2V-11p4nLhSC2M70bmfre5ixjWrl8YCwug__sl20YJdj0yAl0pWkMs9HvgrMgHfQXKT-Xb1jwzlg9zHytJXoGDlrdwERLpBcrDFgNX4i-9psfNvP-oa4htMwjyitmrXMtjLt7-1XfIBmywgDNPcX2df35S8.qIh5zdnP4o1BjjeW-5EZoL62VCAwHNPlL6wL3FFu6MM&dib_tag=se&keywords=di%C3%A1rio+de+um+banana+1&qid=1745496503&sr=8-1&ufe=app_do%3Aamzn1.fos.6d798eae-cadf-45de-946a-f477d47705b9',
      mercadoLivre: 'https://produto.mercadolivre.com.br/MLB-1940623963-livro-diario-de-um-banana-1-_JM',
    shopee: 'https://shopee.com.br/Di%C3%A1rio-de-um-Banana-Jeff-Kinney-i.12345678.1234567891'
  },
  {
    id: 3,
    titulo: 'Extraordinário',
    resenha: 'É sobre um menino com uma deformidade facial que vai para a escola pela primeira vez.',
    preco: 35.91,
    capa: 'https://m.media-amazon.com/images/I/6132ndvQdiL.jpg',
    botao: 'Adicionar ao carrinho',
    link: 'https://www.amazon.com.br/Extraordin%C3%A1rio-R-J-Palacio/dp/8580573017',
    mercadoLivre: 'https://www.mercadolivre.com.br/livro-fisico-extraordinario-de-rj-palacio/p/MLB20738020?pdp_filters=item_id%3AMLB3097244542&from=gshop&matt_tool=45889666&matt_internal_campaign_id=&matt_word=&matt_source=google&matt_campaign_id=22090354034&matt_ad_group_id=173090524236&matt_match_type=&matt_network=g&matt_device=c&matt_creative=727882726761&matt_keyword=&matt_ad_position=&matt_ad_type=pla&matt_merchant_id=735128188&matt_product_id=MLB20738020-product&matt_product_partition_id=2388138864950&matt_target_id=pla-2388138864950&cq_src=google_ads&cq_cmp=22090354034&cq_net=g&cq_plt=gp&cq_med=pla&gad_source=1&gbraid=0AAAAAD93qcBAty3cyVeyrfbIu8lREECex&gclid=CjwKCAjwwqfABhBcEiwAZJjC3o6qebR1GGnWk5Un9N6bs9vTdJzw2gQyoE-FI4xIJkWD0RHL2njL2BoC2BwQAvD_BwE',
    shopee: 'https://shopee.com.br/Extraordin%C3%A1rio-R-J-Palacio-i.12345678.1234567890'
  },
  {
    id: 4,
    titulo: 'Jogos vorazes',
    resenha: 'É sobre um futuro distópico onde jovens são forçados a lutar até a morte em uma arena.',
    preco: 31.26,
    capa: 'https://m.media-amazon.com/images/I/61zBhzjS4LL._AC_UF1000,1000_QL80_.jpg',
    botao: 'Adicionar ao carrinho',
    link: 'https://www.amazon.com.br/Jogos-vorazes-Trilogia-Vorazes-Livro-ebook/dp/B00A3D1OYU',
    mercadoLivre: 'https://www.mercadolivre.com.br/jogos-vorazes-de-collins-suzanne-editorial-editora-rocco-ltda-capa-mole-em-portugus-2022/p/MLB19301770#polycard_client=search-nordic&searchVariation=MLB19301770&wid=MLB3852990267&position=10&search_layout=grid&type=product&tracking_id=1fe8da33-8e2a-4a8f-9a13-5a59977091e2&sid=search',
    shopee: 'https://shopee.com.br/Jogos-Vorazes-Suzanne-Collins-i.12345678.1234567891'
  },
  {
    id: 5,
    titulo: 'As Crônicas de Nárnia',
    resenha: 'Durante os bombardeios da Segunda Guerra Mundial, quatro irmãos são enviados para uma casa de campo. Lá, Lucy encontra um guarda-roupa que a leva a Nárnia.',
    preco: 75.00,
    capa: 'https://m.media-amazon.com/images/I/71yJLhQekBL._AC_UF1000,1000_QL80_.jpg',
    botao: 'Adicionar ao carrinho',
    link: 'https://www.amazon.com.br/As-Cr%C3%B4nicas-N%C3%A1rnia-Brochura-Lewis/dp/857827069X',
        mercadoLivre: 'https://produto.mercadolivre.com.br/MLB-4152806420-livro-las-cronicas-de-narnia-as-crnicas-de-narnia-edico-_JM#polycard_client=search-nordic&position=12&search_layout=grid&type=item&tracking_id=1c403e16-9cad-41e0-a540-b959a6150be3',
    shopee: 'https://shopee.com.br/As-Cr%C3%B4nicas-de-N%C3%A1rnia-C.S.-Lewis-i.12345678.1234567892'
  }
]);

const carrinho = ref([]);

const adicionarAoCarrinho = (produto) => {
  const itemExistente = carrinho.value.find((item) => item.id === produto.id);
  if (itemExistente) {
    itemExistente.quantidade++;
    itemExistente.total = itemExistente.quantidade * itemExistente.preco;
  } else {
    carrinho.value.push({
      id: produto.id,
      nome: produto.titulo,
      preco: produto.preco,
      quantidade: 1,
      total: produto.preco,
    });
  }
}

// eslint-disable-next-line no-unused-vars
const totalCarrinho = computed(() => {
  return carrinho.value.reduce((acc, item) => acc + item.total, 0).toFixed(2);
});
</script>

<template>
  <header>
    <div class="wrapper">
      <h1>Catálogo de Livros</h1>
    </div>
    <div>
      <h2>Bem-vindo à Livraria Online</h2>
      <p>Explore nosso catálogo de livros e encontre sua próxima leitura favorita!</p>
    </div>
  </header>

  <main>
    <section class="produtos">
      <div class="produto" v-for="produto in produtos" :key="produto.id">
        <img :src="produto.capa" :alt="produto.titulo" class="produto-capa" />
        <div class="produto-info">
          <h2>{{ produto.titulo }}</h2>
          <p>{{ produto.resenha }}</p>
          <p class="preco">R$ {{ produto.preco.toFixed(2) }}</p>
          <button @click="adicionarAoCarrinho(produto)" class="botao-carrinho">
            <img :src="carrinhoIcon" alt="Carrinho" class="icone-carrinho" />
            {{ produto.botao }}
          </button>
          <a v-if="produto.mercadoLivre" :href="produto.mercadoLivre" target="_blank" class="botao-carrinho">
  Ver no Mercado Livre
</a>

<a v-if="produto.shopee" :href="produto.shopee" target="_blank" class="botao-carrinho">
  Ver na Shopee
</a>


          <a :href="produto.link" target="_blank" class="botao-carrinho">
            Ver na Amazon
          </a>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
.icone-carrinho {
  width: 20px;
  height: 20px;
  margin-right: 8px;
  vertical-align: middle;
}

header {
  text-align: center;
  margin-bottom: 3rem;
}

.wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  font-size: 2rem;
  color: #333;
}

.produtos {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 2rem;
  padding: 20px;
}

.produto {
  background-color: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.produto:hover {
  transform: scale(1.05);
}

.produto-capa {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.produto-info {
  padding: 1rem;
}

.produto-info h2 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.produto-info p {
  font-size: 1rem;
  color: #555;
}

.preco {
  font-size: 1.2rem;
  font-weight: bold;
  color: #f60;
}

.botao-carrinho {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  background-color: #28a745;
  color: white;
  text-decoration: none;
  border: none;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: bold;
  transition: background-color 0.3s;
  margin-top: 10px;
}

.botao-carrinho:hover {
  background-color: #218838;
}
</style>



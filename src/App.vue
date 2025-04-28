<template>
  <div class="flex flex-col min-h-screen">
    <!-- Navbar -->
    <header class="bg-white shadow p-4 flex justify-between items-center">
      <div class="flex items-center space-x-2">
        <img src="./assets/logo.svg" alt="Logo" class="h-8" />
        <span class="font-bold text-green-600 text-xl">Ficcus</span>
      </div>

      <div class="flex items-center space-x-6">
        <button @click="tela = 'home'" class="text-gray-700 hover:text-green-600">Home</button>
        <button @click="tela = 'carrinho'" class="relative">
          <img src="./assets/carrinhoicon.jpg" alt="Carrinho" class="h-8 w-8" />
        </button>
      </div>
    </header>

    <!-- Conteúdo -->
    <main class="flex-1 bg-gray-50 p-8">
      <!-- Tela Home -->
      <div v-if="tela === 'home'">
        <h1 class="text-3xl font-bold mb-6 text-green-600">Lançamentos</h1>

        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6">
          <div
            v-for="livro in livros"
            :key="livro.id"
            class="bg-white p-4 rounded shadow hover:shadow-lg flex flex-col"
          >
            <img :src="livro.imagem" alt="Livro" class="h-48 object-cover mb-4 rounded" />
            <h3 class="font-bold text-lg">{{ livro.titulo }}</h3>
            <p class="text-gray-600">{{ livro.autor }}</p>
            <p class="text-green-600 font-bold mt-2">R$ {{ livro.preco.toFixed(2) }}</p>
            <button
              @click="adicionarAoCarrinho(livro)"
              class="mt-auto bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600 mt-4"
            >
              Comprar
            </button>
          </div>
        </div>
      </div>

      <!-- Tela Carrinho -->
      <div v-else>
        <h1 class="text-3xl font-bold mb-8 text-green-600">Carrinho</h1>

        <div class="grid md:grid-cols-3 gap-8">
          <div class="md:col-span-2 space-y-6">
            <div
              v-for="item in carrinho"
              :key="item.id"
              class="flex bg-white p-4 rounded shadow justify-between items-center"
            >
              <div class="flex items-center space-x-4">
                <img :src="item.imagem" alt="Livro" class="h-24 w-20 object-cover rounded" />
                <div>
                  <h2 class="font-bold">{{ item.titulo }}</h2>
                  <p class="text-gray-600">{{ item.autor }}</p>
                  <p class="text-green-600 font-bold">R$ {{ item.preco.toFixed(2) }}</p>
                </div>
              </div>

              <div class="flex items-center space-x-2">
                <button @click="diminuir(item)" class="bg-gray-300 p-2 rounded">-</button>
                <span>{{ item.quantidade }}</span>
                <button @click="aumentar(item)" class="bg-gray-300 p-2 rounded">+</button>
              </div>

              <div class="font-bold text-gray-700">
                R$ {{ (item.preco * item.quantidade).toFixed(2) }}
              </div>
            </div>
          </div>

          <div class="bg-white p-6 rounded shadow">
            <h2 class="text-xl font-bold mb-4">Resumo</h2>
            <div class="flex justify-between border-b py-2">
              <span>Produtos</span>
              <span>R$ {{ totalProdutos.toFixed(2) }}</span>
            </div>
            <div class="flex justify-between border-b py-2">
              <span>Frete</span>
              <span>Grátis</span>
            </div>
            <div class="flex justify-between font-bold py-2">
              <span>Total</span>
              <span>R$ {{ totalProdutos.toFixed(2) }}</span>
            </div>
            <button class="mt-6 w-full bg-green-500 text-white px-6 py-3 rounded hover:bg-green-600">
              Finalizar Compra
            </button>
          </div>
        </div>
      </div>
    </main>

    <!-- Rodapé -->
    <footer class="bg-green-600 text-white p-8 text-center">
      <div>© Ficcus 2025 - Todos os direitos reservados</div>
    </footer>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const tela = ref('home');

const livros = ref([
  {
    id: 1,
    titulo: 'Chain of Iron Volume 2',
    autor: 'Cassandra Clare',
    preco: 62.24,
    imagem: './assets/livros/livro1.jpeg',
  },
  {
    id: 2,
    titulo: 'Chain of Thorns',
    autor: 'Cassandra Clare',
    preco: 69.32,
    imagem: './assets/livros/livro2.jpg',
  },
]);

const carrinho = ref([]);

function adicionarAoCarrinho(livro) {
  const itemExistente = carrinho.value.find((item) => item.id === livro.id);
  if (itemExistente) {
    itemExistente.quantidade++;
  } else {
    carrinho.value.push({ ...livro, quantidade: 1 });
  }
  tela.value = 'carrinho';
}

function aumentar(item) {
  item.quantidade++;
}

function diminuir(item) {
  if (item.quantidade > 1) {
    item.quantidade--;
  }
}

const totalProdutos = computed(() =>
  carrinho.value.reduce((acc, item) => acc + item.preco * item.quantidade, 0)
);
</script>






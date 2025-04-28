<script setup>
import { ref, computed } from 'vue';

// Lista de produtos
const produtos = ref([
  {
    id: 1,
    titulo: 'Chain of Iron: Volume 2',
    resenha: 'Uma história épica de fantasia e mistério.',
    preco: 62.24,
    capa: 'https://m.media-amazon.com/images/I/91bYsX41DVL.jpg',
  },
  {
    id: 2,
    titulo: 'Chain of Thorns',
    resenha: 'A conclusão emocionante da série.',
    preco: 65.24,
    capa: 'https://m.media-amazon.com/images/I/81eB+7+CkUL.jpg',
  },
  {
    id: 3,
    titulo: 'City of Fallen Angels',
    resenha: 'Uma nova aventura no mundo das sombras.',
    preco: 45.15,
    capa: 'https://m.media-amazon.com/images/I/91HHqVTAJQL.jpg',
  },
  {
    id: 4,
    titulo: 'Clockwork Princess',
    resenha: 'O desfecho de uma trilogia inesquecível.',
    preco: 49.14,
    capa: 'https://m.media-amazon.com/images/I/81U6zN2D+JL.jpg',
  },
  {
    id: 5,
    titulo: 'Nona the Ninth',
    resenha: 'Uma história de ficção científica intrigante.',
    preco: 55.14,
    capa: 'https://m.media-amazon.com/images/I/81a4kCNuH+L.jpg',
  },
]);

// Carrinho de compras
const carrinho = ref([]);

// Variável para controlar a visibilidade do carrinho
const mostrarCarrinho = ref(false);

// Função para adicionar um produto ao carrinho
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
};

// Função para remover um item do carrinho
const removerDoCarrinho = (produtoId) => {
  carrinho.value = carrinho.value.filter((item) => item.id !== produtoId);
};

// Função para calcular o total do carrinho
const totalCarrinho = computed(() => {
  return carrinho.value.reduce((acc, item) => acc + item.total, 0).toFixed(2);
});
</script>

<template>
  <header class="header">
    <div class="header-content">
      <h1>Livraria Online</h1>
      <p>Frete grátis para todo o Brasil em compras acima de R$50!</p>
      <button @click="mostrarCarrinho = !mostrarCarrinho" class="botao-carrinho">
        🛒 Carrinho ({{ carrinho.length }})
      </button>
    </div>
  </header>

  <main>
    <!-- Destaque -->
    <section class="destaque">
      <div class="destaque-info">
        <h2>Eric-Emanuel Schmitt</h2>
        <p>Descubra o novo livro do autor best-seller Eric-Emanuel Schmitt.</p>
        <button @click="adicionarAoCarrinho(produtos[0])" class="botao-destaque">
          Adicionar ao carrinho
        </button>
      </div>
      <img
        src="https://m.media-amazon.com/images/I/81eB+7+CkUL.jpg"
        alt="Livro em destaque"
        class="destaque-capa"
      />
    </section>

    <!-- Lista de produtos -->
    <section class="produtos">
      <h2>Lançamentos</h2>
      <div class="produtos-grid">
        <div class="produto" v-for="produto in produtos" :key="produto.id">
          <img :src="produto.capa" :alt="produto.titulo" class="produto-capa" />
          <div class="produto-info">
            <h3>{{ produto.titulo }}</h3>
            <p class="preco">R$ {{ produto.preco.toFixed(2) }}</p>
            <button @click="adicionarAoCarrinho(produto)" class="botao-carrinho">
              Comprar
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Carrinho de compras -->
    <section v-if="mostrarCarrinho" class="carrinho">
      <h2>Carrinho de Compras</h2>
      <div v-if="carrinho.length === 0">
        <p>O carrinho está vazio.</p>
      </div>
      <div v-else>
        <div class="item" v-for="item in carrinho" :key="item.id">
          <h3>{{ item.nome }}</h3>
          <p>Quantidade: {{ item.quantidade }}</p>
          <p>Total: R$ {{ item.total.toFixed(2) }}</p>
          <button @click="removerDoCarrinho(item.id)" class="botao-remover">
            Remover
          </button>
        </div>
        <h3>Total do Carrinho: R$ {{ totalCarrinho }}</h3>
      </div>
    </section>
  </main>

  <footer class="footer">
    <p>&copy; 2025 Livraria Online. Todos os direitos reservados.</p>
  </footer>
</template>

<style scoped>
/* Estilo do cabeçalho */
.header {
  background-color: #f8f9fa;
  padding: 20px;
  text-align: center;
  margin-bottom: 20px;
}

.header-content h1 {
  font-size: 2.5rem;
  color: #333;
}

.header-content p {
  font-size: 1.2rem;
  color: #555;
}

.botao-carrinho {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
}

.botao-carrinho:hover {
  background-color: #0056b3;
}

.botao-remover {
  background-color: #dc3545;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 0.9rem;
}

.botao-remover:hover {
  background-color: #c82333;
}

/* Estilo do carrinho */
.carrinho {
  margin-top: 20px;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f8f9fa;
}

.carrinho h2 {
  font-size: 1.8rem;
  margin-bottom: 20px;
}

.item {
  margin-bottom: 15px;
}

.item h3 {
  font-size: 1.2rem;
  margin-bottom: 5px;
}

/* Estilo dos produtos */
.produtos {
  padding: 20px;
}

.produtos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 20px;
}

.produto {
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.produto-capa {
  width: 100%;
  height: 150px; /* Altura fixa para imagens menores */
  object-fit: cover; /* Ajusta a imagem para caber no espaço */
  border-bottom: 1px solid #ddd;
}

.produto-info {
  padding: 10px;
}

.produto-info h3 {
  font-size: 1.2rem;
  margin-bottom: 10px;
}

.preco {
  font-size: 1.2rem;
  font-weight: bold;
  color: #28a745;
  margin-bottom: 10px;
}

.botao-carrinho {
  background-color: #28a745;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
}

.botao-carrinho:hover {
  background-color: #218838;
}
</style>
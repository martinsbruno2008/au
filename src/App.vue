
<template>
  <div class="app-container">
    <!-- Cabeçalho -->
    <header class="header">
      <nav class="navbar">
        <a href="#" class="logo">Livraria</a>
        <ul class="nav-links">
          <li><a href="#">Início</a></li>
          <li><a href="#">Ajuda</a></li>
          <li><a href="#">Sobre</a></li>
          <li><a href="#">Contato</a></li>
        </ul>
        <div class="nav-icons">
          <i class="icon">👤</i>
          <i class="icon">🛒</i>
        </div>
      </nav>
    </header>

    <!-- Seção principal -->
    <main class="main">
      <!-- Destaque inicial -->
      <section class="highlight">
        <h1>Eric-Emanuel Schmitt</h1>
        <p>Eric-Emanuel Schmitt tem mais de 20 prêmios e seus livros foram traduzidos para mais de 50 países.</p>
        <button class="btn">Acessar página do livro</button>
      </section>

      <!-- Lançamentos -->
      <section class="releases">
        <h2>Lançamentos</h2>
        <div class="book-grid">
          <div class="book-card">

            <h3>Chain of Iron</h3>
            <p>Autor: Cassandra Clare</p>
            <p>Preço: R$ 62,24</p>
            <button class="btn">Comprar</button>
          </div>
          <div class="book-card">
         
            <h3>Chain of Thorns</h3>
            <p>Autor: Cassandra Clare</p>
            <p>Preço: R$ 62,24</p>
            <button class="btn">Comprar</button>
          </div>
          <!-- Adicione mais livros aqui -->
        </div>
      </section>

      <!-- Livros Populares -->
      <section class="popular-books">
        <h2>Livros Populares</h2>
        <div class="book-grid">
          <div class="book-card">
            ">
            <h3>Harlem Shuffle</h3>
            <p>Autor: Colson Whitehead</p>
            <p>Preço: R$ 62,24</p>
            <button class="btn">Comprar</button>
          </div>
          <div class="book-card">
           
            <h3>Two Old Women</h3>
            <p>Autor: Velma Wallis</p>
            <p>Preço: R$ 115,34</p>
            <button class="btn">Comprar</button>
          </div>
          <!-- Adicione mais livros aqui -->
        </div>
      </section>
    </main>

    <!-- Carrinho -->
    <section class="cart">
      <h2>Carrinho</h2>
      <div class="cart-item">
        
        <h3>Chain of Iron</h3>
        <p>Autor: Cassandra Clare</p>
        <p>Preço: R$ 64,48</p>
        <p>Quantidade: 2</p>
        <p>Subtotal: R$ 128,96</p>
      </div>
      <button class="btn">Ir para o pagamento</button>
    </section>
  </div>
</template>

<style>
/* Estilos gerais */
.app-container {
  font-family: Arial, sans-serif;
  margin: 0 auto;
  padding: 1rem;
}
.header, .footer {
  background-color: #343a40;
  color: white;
  padding: 1rem;
  text-align: center;
}
.main {
  padding: 2rem;
}
.book-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
}
.book-card img {
  width: 100px;
  height: 150px;
  margin-bottom: 0.5rem;
}
.cart-item img {
  width: 100px;
  height: 150px;
  margin-bottom: 0.5rem;
}
.btn {
  background-color: #007bff;
  color: white;
  padding: 0.5rem 1rem;
  border: none;
  cursor: pointer;
}
</style>







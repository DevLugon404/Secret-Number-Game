# Secret-Number-Game
let participantes = [];

// Função para adicionar nome à lista
function adicionarAmigo() {
    const input = document.getElementById('amigo');
    const nome = input.value.trim();
    if (nome) {
        participantes.push(nome);
        atualizarLista();
        input.value = '';
    }
}

// Atualiza a lista de nomes na tela
function atualizarLista() {
    const lista = document.getElementById('listaAmigos');
    lista.innerHTML = '';
    participantes.forEach((nome) => {
        const item = document.createElement('li');
        item.textContent = nome;
        lista.appendChild(item);
    });
}

// Função para sortear um nome aleatoriamente
function sortearAmigo() {
    if (participantes.length === 0) {
        alert('Adicione pelo menos um nome!');
        return;
    }
    const sorteado = participantes[Math.floor(Math.random() * participantes.length)];
    const resultado = document.getElementById('resultado');
    resultado.innerHTML = `<li>Sorteado: ${sorteado}</li>`;
}

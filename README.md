# 🍔 Smash It - Pro Contagem

![Versão](https://img.shields.io/badge/version-1.0.0-yellow)
![Plataforma](https://img.shields.io/badge/platform-Web%20%7C%20Mobile%20Ready-brightgreen)
![Licença](https://img.shields.io/badge/license-MIT-blue)

> **Gestão de stock profissional** com modo edição, envio por WhatsApp e persistência local. Ideal para restaurantes, food trucks, cozinhas comerciais e hamburguerias.

![Preview do Smash It](https://via.placeholder.com/800x400?text=Smash+It+-+Gestão+de+Stock)

---

## 📋 Índice

- [Sobre](#sobre)
- [Funcionalidades](#funcionalidades)
- [Tecnologias](#tecnologias)
- [Como usar](#como-usar)
- [Estrutura de dados](#estrutura-de-dados)
- [Comandos e atalhos](#comandos-e-atalhos)
- [Personalização](#personalização)
- [Limitações](#limitações)
- [Contribuição](#contribuição)

---

## 🧠 Sobre

**Smash It - Pro Contagem** é uma aplicação web progressiva (PWA‑ready) que permite controlar inventários de forma simples, visual e rápida. Com um design inspirado no universo *smash burger*, oferece:

- Contagem de itens por categoria
- Edição completa de categorias e itens
- Pesquisa em tempo real
- Modo de gestão com CRUD
- Geração de relatório formatado para envio via WhatsApp
- Armazenamento **offline‑first** (localStorage)

---

## ✨ Funcionalidades

| Funcionalidade | Descrição |
|----------------|-------------|
| 📦 **Inventário por categorias** | Pães, proteínas, vegetais, queijos – tudo organizado. |
| ➕ **CRUD completo** | Criar/editar/apagar categorias e itens (modo gestão). |
| 🔍 **Pesquisa dinâmica** | Filtra por nome de item ou categoria. |
| ✏️ **Edição inline** | Renomeie itens ou categorias sem perder contagens. |
| 🧹 **Limpar contagens** | Zera todas as quantidades de uma só vez. |
| 🔄 **Reset de fábrica** | Restaura categorias padrão, apaga personalizações e notas. |
| 📝 **Bloco de notas** | Observações adicionais no relatório. |
| 📱 **Envio WhatsApp** | Gera um relatório limpo com quantidades > 0 e notas. |
| 💾 **Persistência local** | Dados salvos automaticamente no navegador. |
| 🌓 **Interface adaptativa** | Funciona em desktop, tablet ou telemóvel. |

---

## 🛠 Tecnologias

- **HTML5** – estrutura semântica
- **Tailwind CSS** – estilização rápida e responsiva
- **Font Awesome 6** – ícones
- **JavaScript (ES6)** – toda a lógica de negócio
- **localStorage** – persistência de dados no cliente

---

## 🚀 Como usar

### 1. Executar localmente
Basta abrir o ficheiro `index.html` em qualquer navegador moderno (Chrome, Firefox, Safari, Edge). Não é necessário servidor web.

### 2. Estrutura inicial predefinida
Ao carregar pela primeira vez, o sistema cria 4 categorias com itens típicos de uma hamburgueria:

- 🍔 **Pães Artesanais** (Pão Batata, Pão Pimenta, Esmagadinho, Outros)
- 🥩 **Proteínas Smash** (Carne 100g, Blend de Queijos, Frango Empanado, Bacon)
- 🥬 **Frescos & Veg** (Alface, Tomate, Cebola Caramelizada, Pickles, Veggie, Futuro)
- 🧀 **Queijos e Molhos** (Cheddar, Prato, Molho Gravy, Heinzen, Pimenta, Maionese)

### 3. Modo normal vs Modo gestão
- **Modo normal** – apenas adicionar/subtrair quantidades e enviar relatório.
- **Modo gestão** – ative com o ícone ⚙️ no topo. Permite criar/editar/apagar categorias e itens.

---

## 📁 Estrutura de dados (localStorage)

A aplicação guarda três chaves no `localStorage`:

| Chave | Tipo | Descrição |
|-------|------|-------------|
| `smash_inventory_pro` | `Array` | Lista de categorias e respetivos itens. |
| `smash_counts_pro` | `Object` | Mapeia `"idCategoria-nomeItem"` → quantidade (inteiro ≥0). |
| `smash_notes_pro` | `string` | Texto do bloco de notas. |

Exemplo de inventário:
```json
[
  {
    "id": 101,
    "name": "🍔 Pães Artesanais",
    "items": ["Pão Batata", "Pão Pimenta"]
  }
]

🎮 Comandos e atalhos
Ação	Como fazer
Aumentar quantidade	Clique no botão + ao lado do item.
Diminuir quantidade	Clique no botão - (não fica negativo).
Definir valor exato	Escreva diretamente no campo numérico.
Ativar modo gestão	Botão ⚙️ no cabeçalho.
Criar categoria	No modo gestão → "Criar nova categoria".
Editar categoria	Modo gestão → clique "Editar" na categoria.
Apagar categoria	Modo gestão → "Apagar" (remove todos os itens e contagens).
Adicionar item	Modo gestão → "Item" na categoria desejada.
Renomear item	Modo gestão → "✎ Renomear" abaixo do item.
Remover item	Modo gestão → "🗑 Remover" abaixo do item.
Limpar todas contagens	Botão 🧹 (eraser) – zera quantidades mas mantém estrutura.
Reset completo	Botão 🔄 (seta circular) – restaura dados originais.
Pesquisar	Campo de pesquisa – filtra por nome de item ou categoria.
Gerar relatório	Botão verde "GERAR RELATÓRIO & ENVIAR".

const DEFAULT_CATEGORIES = [
  { id: 101, name: "🥤 Bebidas", items: ["Coca-Cola", "Água", "Sumo"] },
  // ... outras categorias
];


---

### ✨ Notas finais

Este README foi escrito assumindo que o ficheiro HTML será colocado num repositório público ou partilhado. Se desejar, pode adicionar um **screenshot** real da aplicação (substitua o `placeholder` por uma imagem capturada). Adapte os contactos e a licença conforme a sua necessidade.

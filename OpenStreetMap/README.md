# **Documento do Projeto: Mapa Interativo com React e OpenStreetMap**

## **📌 Visão Geral**

Aplicação React com TypeScript que exibe um mapa full-screen usando OpenStreetMap (Leaflet) e Nominatim para geocoding.
Inclui:
✅ Barra de pesquisa com debounce (2s)
✅ Resultados flutuantes animados
✅ Tema light/dark
✅ SplashScreen até carregamento total
✅ Pin com coordenadas no clique
✅ Otimizado para mobile (sem blur)

---

## **🛠 Stack Tecnológica**

Categoria Tecnologia
Framework React (Vite)
Linguagem TypeScript
Gerenciador Bun
Mapa Leaflet + OpenStreetMap
Geocoding Nominatim API
Estilos styled-components
Fonte Manrope (local)
Normalize normalize.css personalizado

---

## **📂 Estrutura do Projeto**

src/
├── assets/
│ └── fonts/ # Manrope (woff2)
├── components/
│ ├── Map/ # Componente do mapa
│ │ ├── Map.tsx # Lógica do mapa
│ │ └── Map.styles.ts # Estilos do mapa
│ ├── SearchBar/ # Barra de pesquisa
│ │ ├── SearchBar.tsx
│ │ └── SearchBar.styles.ts
│ └── SplashScreen/ # Tela de carregamento
│ ├── SplashScreen.tsx
│ └── SplashScreen.styles.ts
├── hooks/
│ ├── useDebounce.ts # Debounce para pesquisa
│ └── useTheme.ts # Toggle light/dark
├── styles/
│ ├── global.ts # Estilos globais
│ └── normalize.css # Reset CSS
├── types/
│ └── nominatim.d.ts # Tipos da API
└── themes.ts # Cores light/dark

---

## **🎨 Design System (Variáveis CSS)**

```
// themes.ts
export const lightTheme = {
colors: {
background: '#eeeeee',
text: '#1b1b1b',
gray: '#5c5c5c',
accent: '#fe6937',
card: '#ffffff',
},
baseUnit: 'min(1vw, 1vh)', // Unidade responsiva
};

export const darkTheme = {
colors: {
background: '#1b1b1b',
text: '#eeeeee',
gray: '#5c5c5c',
accent: '#fe6937',
card: '#292929',
},
baseUnit: 'min(1vw, 1vh)',
};
```

---

## **⚙️ Funcionalidades**

1. Mapa (Leaflet)

- Full-screen, otimizado para mobile (preferCanvas: true).
- Pin customizado ao clicar em um resultado.
- Alerta com coordenadas no clique do pin.

2. Barra de Pesquisa

- Posição fixa (centro inferior).
- Animação de entrada (slide-up).
- Debounce de 2 segundos após digitar.

3. Resultados da Pesquisa

- Exibidos acima da barra (scroll se necessário).
- Desaparecem se a busca estiver vazia.
- Nome do local selecionado preenche a barra.

4. SplashScreen

- Some após carregamento do mapa + fontes.
- Animação de fade-out.

5. Tema Light/Dark

- Alternância via ThemeProvider.
- Persistência no localStorage.

---

## **🔧 Fluxo de Implementação**

- Setup Inicial (bun create vite)
- SplashScreen (Componente auto-contido)
- Mapa Leaflet (Otimização mobile)
- Barra de Pesquisa (Debounce + Animação)
- Integração Nominatim (Fetch + Tipagem)
- Temas (styled-components + localStorage)
- Otimizações Finais (Performance, A11y)

---

## **✅ Critérios de Aceitação**

- Performance: >90 no Lighthouse.
- Mobile: Mapa nítido, toque responsivo.
- Acessibilidade: ARIA labels, foco gerenciado.
- Código: Componentes isolados, tipagem rigorosa.

---

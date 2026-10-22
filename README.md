# Duo Quest: Lovers' Edition

Jogo web para casais, em um único arquivo `index.html`. Roda 100% no navegador: sem backend, sem Node.js, sem banco de dados.

## Modos

- **Mesmo celular (Pass & Play):** os dois jogam no mesmo aparelho, no sofá ou na mesa.
- **Dois celulares (P2P):** um cria a sala e gera um código de 4 caracteres; o outro entra com o código. A conexão é WebRTC direta via PeerJS. O servidor público do PeerJS só é usado no aperto de mão inicial.

## Jogos

1. **Sintonia do Casal:** perguntas "Quem é mais provável que...?". Cada um escolhe em segredo; combinar rende pontos.
2. **Heart Sync:** arcade cooperativo. Os dois tocam para manter o coração na zona do amor por 15 segundos.
3. **Jogo da Velha dos Apaixonados:** coração contra estrela, com placar contínuo e sons de vitória e empate.
4. **Roleta do Amor:** prêmios e prendas românticas, com animação de giro.

Extras: placar de sintonia (%), modo aconchego (tons quentes e brasas, ativado à noite) e mensagens de feedback ao fim de cada rodada. O som é sintetizado com Web Audio API, sem arquivos externos.

## Tecnologias

- Tailwind CSS via CDN (`cdn.tailwindcss.com`)
- Lucide Icons via CDN (unpkg, versão fixada)
- PeerJS 1.5.4 via CDN (unpkg)
- Google Fonts (Fraunces e DM Sans)

## Rodar localmente

Abra `index.html` no navegador. Para testar o modo P2P entre dois aparelhos, sirva a pasta por HTTP na mesma rede, por exemplo:

```bash
npx serve .
```

## Deploy na Vercel

1. Suba a pasta para um repositório no GitHub.
2. Na Vercel, clique em **Add New > Project** e importe o repositório.
3. Em **Framework Preset**, escolha **Other**. Não há build command nem output directory.
4. Clique em **Deploy**.

## Observações

- Nenhum dado do jogo é salvo no servidor. Nomes e preferências ficam só no `localStorage` do aparelho.
- O modo P2P precisa dos dois aparelhos com internet para o aperto de mão inicial. Depois disso, o tráfego do jogo vai direto entre eles.

# ⚡ Amber Trade — Plataforma Multichain de Tokenização de Energia

Amber Trade é uma **plataforma descentralizada de tokenização e negociação de energia**, desenvolvida sobre uma **arquitetura híbrida multichain**, integrando as redes **Stellar (Soroban)** e **Ethereum (EVM)**.

O objetivo do projeto é **representar energia elétrica real (kWh)** como ativos digitais rastreáveis (RWA – Real World Assets), permitindo **liquidez global**, **governança descentralizada** e **lastro físico comprovado**.

---

## 🧭 Visão Geral

Amber Trade conecta o mercado real de energia ao ecossistema blockchain, transformando kWh gerados em tokens digitais lastreados, negociáveis globalmente.  
A plataforma viabiliza:
- Rastreabilidade do lastro físico,
- Liquidez em stablecoins e ativos digitais,
- Governança descentralizada sobre regras de mercado,
- Proteção de dados sensíveis com ZK-Proofs,
- Interoperabilidade entre redes Stellar e Ethereum via Amber Bridge.

---

## 🪙 Lastro e Compliance Regulatória

Cada **1 AMBR = 1 kWh** de energia elétrica **real e certificada**.

- A medição da geração é feita via **medidores IoT homologados**, integrados a oráculos descentralizados.
- A certificação é validada com base nas regras do **mercado livre de energia (CCEE)** e diretrizes da **ANEEL**.
- Cada token emitido é vinculado a um registro de geração, validado por prova de conhecimento zero.
- Quando o kWh é consumido, o token correspondente é **queimado**, retirando-o definitivamente de circulação.
- Essa lógica garante **supply controlado**, **lastro real** e **transparência auditável**.

---

## 🧩 Arquitetura Técnica

### 🔹 Camada Stellar (Soroban)
- **Linguagem:** Rust + WebAssembly
- **Função:** Emissão de tokens AMBR lastreados em kWh reais
- **ZK-Proofs:** Provas de geração de energia sem exposição de dados sensíveis
- **Contrato principal:** `energy_rwa.rs`
- **Ação principal:** Mint de tokens AMBR correspondentes à energia gerada

### 🔹 Amber Bridge (Cross-Chain)
- **Linguagem:** Rust + Solidity
- **Função:** Sincronizar eventos e liquidez entre Stellar e Ethereum
- **Validação:** ZK + Oráculo descentralizado
- **Mecânica:** Bloqueia tokens AMBR na Stellar → Mint de AMBR espelhados na Ethereum → Burn sincronizado na liquidação

### 🔹 Camada Ethereum (EVM)
- **Linguagem:** Solidity
- **Função:** Garantir liquidez dos tokens AMBR no mercado cripto
- **ZK-Proofs:** Provas de integridade de transações e privacidade do usuário
- **Contrato principal:** `exchange.sol`
- **Ação principal:** Interação com DEX, pools de liquidez e governança

---

## 💰 Token AMBR (ERC-20 + Stellar Asset)

- **Símbolo:** AMBR  
- **Nome:** Amber Energy Token  
- **Tipo:** Token ERC-20 (Ethereum) e Asset nativo (Stellar)  
- **Lastro:** 1 AMBR = 1 kWh certificado

### 🔸 Funções do Token
- Representação digital de energia real;
- Interoperabilidade entre Stellar ↔ Ethereum via Amber Bridge;
- Votação em propostas de governança do ecossistema;
- Participação em pools de liquidez e programas de staking;
- Ativo de investimento lastreado em energia renovável.

### 🔸 Supply Control
- Mint inicial: Stellar (com base em geração validada)
- Bridge: Bloqueio em Stellar ↔ Mint em Ethereum
- Burn: Queima em ambas as redes ao consumir energia
- Auditoria pública de supply

---

## 🪫 Precificação e Liquidação

- O preço de referência do AMBR será **indexado ao PLD (Preço de Liquidação das Diferenças)**, definido pela **CCEE**.
- Opcionalmente, AMBR poderá ser pareado com stablecoins (USDC / BRL) para liquidez internacional.
- A liquidação ocorre de três formas:
  1. **Revenda no mercado cripto (DEX)**
  2. **Manter em carteira como investimento**
  3. **Troca pelo ativo real (energia)** → **queima automática** do token

---

## 🔐 Privacidade e ZK-Proofs

Amber Trade utiliza **Zero-Knowledge Proofs (ZK)** em duas camadas:

1. **ZK-Geração:** prova de geração em Stellar, garantindo lastro sem expor dados sensíveis como localização e volume;
2. **ZK-Transação:** anonimato e integridade nas operações de compra, venda e liquidação em Ethereum.

Ferramentas utilizadas:
- `snarkjs`, `circom`, `halo2`, `zkInterface`.

---

## 🔗 Fluxo Operacional


1. Geração de energia real → Medição IoT
2. Registro ZK da produção → Rede Stellar
3. Mint de tokens AMBR lastreados (1:1 kWh)
4. Envio Cross-Chain via Amber Bridge
   - Stellar: token bloqueado
   - Ethereum: token mintado
5. Liquidação:
   - Revenda no mercado cripto
   - Investimento em carteira
   - Troca por energia → queima do token nas duas redes


## 🧭 Governança

O ecossistema AMBR é gerido por uma DAO de governança híbrida.

- Holders podem votar em:

- Atualizações da Bridge

- Indexadores de preço

- Taxas de transação

- Programas de incentivo para energia renovável

A governança tem como objetivo alinhar mercado energético físico e financeiro descentralizado.


## 🧑‍💻 Desenvolvedores Principais

Roberto da Rocha Pimentel Junior
Blockchain Engineer | Especialista em ZKPs e Tokenização de Ativos
Líder técnico do Amber Trade, responsável pela arquitetura multichain, integrações oraculares e ZK Proofs.

Eduardo Ferreira da Silva
Especialista em Mercado de Energia & Compliance Regulatória
Responsável pela adequação do projeto às normas da CCEE, ANEEL e expansão internacional.


## 🏆 Premiações

🎖️ 4ª colocação — Hackathon HackMeridian (Stellar)
🏅 6ª colocação — Hackathon O Grande Código (ZKVerify)


## 📜 Licença

Este projeto é licenciado sob Apache 2.0, com sub-licenças MIT e CC BY 4.0, conforme descrito em LICENSE.md

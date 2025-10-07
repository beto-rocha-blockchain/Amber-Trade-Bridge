# Em construção - Under constuction

# ⚡ Amber-Trade - Plataforma Multichain de Tokenização de Energia

Amber Trade é uma **plataforma descentralizada de tokenização e negociação de energia**, desenvolvida sobre uma **arquitetura híbrida multichain**, integrando as redes **Stellar (Soroban)** e **Ethereum (EVM)**.

O objetivo do projeto é **representar energia elétrica real (kWh)** como ativos digitais rastreáveis (RWA – Real World Assets), possibilitando **liquidez global e governança descentralizada**.

---

## 🧩 Arquitetura Técnica

### 🔹 Camada Stellar (Soroban)
- **Linguagem:** Rust + WebAssembly
- **Função:** Emissão de tokens RWA (EnerTokens) lastreados em energia real gerada;
- **ZK-Proofs:** Garantia de privacidade sobre dados sensíveis de geração (produção, geolocalização, volume e tipo de energia).
- **Contrato principal:** `energy_rwa.rs`

### 🔹 Camada Ethereum (EVM)
- **Linguagem:** Solidity
- **Função:** Liquidez dos tokens e interação com o mercado de criptoativos;
- **ZK-Proofs:** Provas de integridade e privacidade sobre dados do usuário e transações;
- **Contrato principal:** `exchange.sol`

### 🔹 Bridge Cross-Chain (Amber Bridge)
- **Linguagem:** Rust + Solidity
- **Função:** Sincronizar eventos e liquidez entre Stellar e Ethereum via protocolo seguro;
- **Validação:** ZK + Oráculo descentralizado (para leitura de geração real).

---

## 💠 Token AMBR (ERC-20 + Governança)
- **Tipo:** Token ERC-20 e de governança (modelo híbrido);
- **Uso:**
  - Votação em propostas de governança;
  - Participação em pools de liquidez;
  - Recompensas por geração e staking de energia limpa;
  - Interoperabilidade com EnerTokens (RWA).

---

## 🔒 Privacidade e Provas de Conhecimento Zero (ZK)
Amber Trade utiliza **provas ZK (Zero-Knowledge)** em duas camadas:
1. **ZK-Geração:** valida a geração de energia sem expor dados sensíveis (em Stellar);
2. **ZK-Transação:** garante anonimato e integridade nas trocas de tokens (em Ethereum).

Ferramentas:
- `snarkjs`, `circom`, `zkInterface` e `halo2` (dependendo do circuito e da rede).

---

## 🔗 Fluxo Operacional Simplificado

1. **Geração de Energia Real** → capturada via IoT/oráculo;
2. **Registro ZK da Produção** → prova de geração em Stellar (Rust + WASM);
3. **Tokenização RWA (EnerToken)** → emissão do ativo digital;
4. **Envio Cross-Chain** → via Amber Bridge para a rede Ethereum;
5. **Liquidez no Mercado Cripto** → troca de EnerToken ↔ AMBR ou outras moedas;
6. **Consumidor Final / Governança** → uso, voto e staking de AMBR.

![Fluxograma do Sistema](docs/img/fluxo_amber_trade.png)

---

## ⚙️ Estrutura do Repositório

amber-trade/
│
├── LICENSE.md  
├── README.md  
├── docs/  
│ ├── architecture.md  
│ ├── tokenomics.md  
│ ├── roadmap.md  
│ └── img/  
│ └── fluxo_amber_trade.png  
│  
├── contracts/  
│ ├── stellar/  
│ └── ethereum/  
│  
├── circuits/  
├── bridge/  
└── frontend/  

---

## 🧑‍💻 Desenvolvedor Principal
**Roberto da Rocha Pimentel Junior**  
Blockchain Engineer | Especialista em ZKPs e Tokenização  
6ª colocação — Hackaton **O Grande Código 2025 (ZKVerify)**  
4ª colocação — Hackathon **HackMeridian 2025 (Stellar)**  

---

## 📄 Licença  
Este projeto é licenciado sob a **Apache 2.0**, com sub-licenças **MIT** e **CC BY 4.0** conforme descrito em [`LICENSE.md`](LICENSE.md).

---

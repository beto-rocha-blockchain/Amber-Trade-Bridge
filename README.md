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

## 🧑‍💻 Desenvolvedores Principais
**Roberto da Rocha Pimentel Junior** 
  
Blockchain Engineer | Especialista em ZKPs e Tokenização 📟  
Profissional com sólida experiência em desenvolvimento de soluções blockchain, atuando em projetos que envolvem contratos inteligentes, tokenização de ativos reais (RWA) e provas de conhecimento zero (ZKPs).
Possui domínio técnico em Solidity, Rust, WebAssembly e integração de oráculos, com foco em segurança, escalabilidade e interoperabilidade entre redes.
Atuou como Engenheiro Blockchain e líder técnico em projetos premiados, incluindo o Ambar Trade, que conquistou a 4ª colocação no Hackathon HackMeridian (Stellar, 2024), destacando-se pela aplicação de tecnologia de oráculos e tokens lastreados em XLM.
Especialista em arquiteturas multichain e soluções descentralizadas de energia, é responsável pela concepção técnica e estratégica da Amber Trade, unindo inovação, privacidade e governança em um ecossistema global de energia digital.  

**Eduardo Ferreira da Silva**  
Especialista em Mercado de Energia & Compliance Regulatória ⚡  
Profissional com sólida trajetória no mercado de negociação de ativos de energia elétrica, com atuação prática em modelos de comercialização, gestão de contratos e análise de risco em ambientes regulados e livres.

Reconhecido por seu profundo domínio das normas e diretrizes da ANEEL e da CCEE, é responsável por garantir a conformidade jurídica e regulatória da tokenização de energia no projeto, assegurando que a transição entre o mercado físico e o digital ocorra dentro dos parâmetros legais.

Além de sua expertise técnica, contribui com a visão estratégica de expansão do modelo para diferentes mercados internacionais, conectando o ecossistema de energia tradicional ao universo blockchain de forma segura, escalável e transparente.  
  
## 🏆 Premiações do projeto 🏆
🎯 🏅 6ª colocação — Hackaton **O Grande Código 2025 (ZKVerify)**  
🎯 🎖️ 4ª colocação — Hackathon **HackMeridian 2025 (Stellar)**  

---

## 📄 Licença  
Este projeto é licenciado sob a **Apache 2.0**, com sub-licenças **MIT** e **CC BY 4.0** conforme descrito em [`LICENSE.md`](LICENSE.md).

---

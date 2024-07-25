# DIO BINANCE Token 🚀

Bem-vindo ao projeto do token DIO BINANCE (DIO-BINANCE)! Este projeto é um contrato inteligente implementado em Solidity que segue o padrão ERC20. Ele inclui funcionalidades básicas de um token ERC20, bem como funcionalidades adicionais de queima (burn) e mint.

## Descrição

O DIO BINANCE Token (símbolo: DIO-BINANCE) é um token ERC20 com as seguintes características:

- Nome: DIO BINANCE Coin
- Símbolo: DIO-BINANCE
- Decimais: 2
- Suprimento total inicial: 100,000.00 DIO-BINANCE

## Funcionalidades

### Funcionalidades Básicas

- `totalSupply` 🌐: Retorna o suprimento total de tokens.
- `balanceOf` 📊: Retorna o saldo de um endereço específico.
- `transfer` 💸: Transfere tokens para um endereço.
- `approve` ✅: Aprova um endereço para gastar uma quantidade específica de tokens em nome do proprietário.
- `allowance` 📄: Retorna a quantidade de tokens que um endereço está autorizado a gastar em nome do proprietário.
- `transferFrom` 🔄: Transfere tokens de um endereço para outro usando a autorização prévia.

### Funcionalidades Adicionais

- `burn` 🔥: Permite que os usuários queimem (destroy) seus tokens, reduzindo o suprimento total.
- `mint` 🪙: Permite ao proprietário do contrato criar novos tokens, aumentando o suprimento total.

## Implementação

O contrato é implementado em Solidity e utiliza a biblioteca `SafeMath` para operações seguras com números inteiros. Ele também inclui verificações para evitar o uso de endereços zero.

### SafeMath

Utilizamos a biblioteca `SafeMath` para prevenir problemas de overflow e underflow, garantindo operações matemáticas seguras.

### Verificação de Endereço Zero

Adicionamos verificações para garantir que endereços zero não sejam utilizados nas funções `transfer`, `approve` e `transferFrom`.

## Eventos

- `Transfer` 🔄: Emitido quando tokens são transferidos.
- `Approval` ✅: Emitido quando um endereço é aprovado para gastar tokens em nome do proprietário.

## Como Usar

### Compilar

Compile o contrato usando o compilador Solidity versão ^0.8.7.

### Implantar

Implante o contrato em uma rede Ethereum compatível.

### Interagir

Você pode interagir com o contrato usando qualquer carteira compatível com Ethereum ou através de uma interface como o Remix.

## Exemplo de Uso

Aqui está um exemplo de como você pode interagir com o contrato:

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.7;

import "./DIOBINANCEToken.sol";

contract ExampleUsage {
    DIOBINANCEToken public token;

    constructor(address tokenAddress) {
        token = DIOBINANCEToken(tokenAddress);
    }

    function transferTokens(address to, uint256 amount) public {
        require(token.transfer(to, amount), "Transfer failed");
    }
}

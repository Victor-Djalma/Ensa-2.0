# Ensa-2.0

ENSA 2.0 – Network Security Analyzer

O ENSA 2.0 é uma aplicação web local desenvolvida para realizar análises de rede e detecção de vulnerabilidades utilizando Nmap, Flask, Nginx, Bind9 e uma interface web em HTML, CSS e JavaScript.
O projeto foi dividido em dois servidores — frontend e backend — que se correlacionam para permitir operações completas de análise sem expor comandos diretamente ao usuário.

🚀 Arquitetura do Projeto
📌 Frontend

O servidor de frontend utiliza:

Nginx (servidor web)

Bind9 (DNS local)

HTML, CSS e JavaScript (interface)

Exibição dinâmica dos resultados

Consumo da API Flask em tempo real

A interface permite ao usuário escolher entre dois tipos de varredura (Stealth e Completa) e visualizar os resultados ao vivo.

📌 Backend

O backend é responsável por toda a lógica de varredura e execução do Nmap:

Construído em Python com Flask

Executa os comandos do Nmap internamente

Retorna os resultados em formato JSON

Envia a resposta à interface via HTTP

Mantém comunicação direta com o frontend (sem exposição de IPs aqui)

🔍 Tipos de Varredura Implementados
1️⃣ Varredura Stealth (Scan Básico)

Executa internamente o comando:

nmap -sS <IP> <máscara>


✔ Identifica portas abertas
✔ Mais rápido e silencioso
✔ Pode ser usado para IPs isolados ou redes completas

2️⃣ Varredura Completa (Scan Avançado)

Executa:

nmap -sV -T3 --script=vulners <IP_ou_Alvo>


✔ Coleta versões de serviços
✔ Executa script vulners para capturar CVEs
✔ Utiliza agressividade T3 para melhor detecção
✔ Ideal para análise profunda de hosts e serviços

🌐 Fluxo Interno de Funcionamento

O usuário acessa o site e escolhe o tipo de scan

A interface envia a requisição para a API Flask

O backend executa o Nmap

Os resultados são convertidos em JSON

O frontend recebe e exibe os resultados em tempo real por meio do JavaScript

📄 Documentação Completa

A documentação oficial do projeto pode ser acessada no arquivo PDF que acompanha este repositório.

📥 Download da documentação:
O PDF gerado contém detalhes sobre arquitetura, comunicação entre servidores, funcionamento dos scans e estrutura da aplicação.

🛠️ Tecnologias Utilizadas

Frontend

HTML5

CSS3

JavaScript

Nginx

Bind9

Backend

Python

Flask

Nmap (executado via backend)

📌 Objetivo

O ENSA 2.0 foi criado como uma ferramenta educacional e técnica para estudos em:

Segurança de redes

Análise de vulnerabilidades

Automação de scans

Integração frontend-backend

Estruturação de ferramentas de auditoria local

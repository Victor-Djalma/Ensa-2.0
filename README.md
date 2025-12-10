# 🛡️ ENSA 2.0: Network Security Analyzer

O **ENSA 2.0** (Network Security Analyzer) é uma aplicação web local projetada para realizar **análises de rede** e **detecção de vulnerabilidades** de forma eficiente e segura. Utilizando uma arquitetura robusta baseada em **Nmap**, **Flask**, **Nginx** e **Bind9**, o projeto oferece uma interface web intuitiva em HTML, CSS e JavaScript para simplificar o processo de auditoria de segurança.

O principal diferencial do ENSA 2.0 é a sua divisão em dois servidores distintos — **Frontend** e **Backend** — que se correlacionam para permitir operações completas de análise, garantindo que os comandos de varredura nunca sejam expostos diretamente ao usuário final.

---

## 🚀 Arquitetura do Projeto

A aplicação é estruturada em uma arquitetura de dois servidores, otimizada para segurança e desempenho em um ambiente de rede local.

### 📌 Frontend

O servidor de Frontend é o ponto de contato do usuário e é responsável pela apresentação e interação.

| Componente | Função |
| :--- | :--- |
| **Nginx** | Servidor web para servir a interface estática. |
| **Bind9** | Serviço de DNS local para resolução de nomes. |
| **HTML, CSS, JS** | Interface de usuário (UI) para seleção de varreduras e exibição de resultados. |

**Características:**
*   **Exibição Dinâmica:** Apresentação dos resultados em tempo real.
*   **Consumo de API:** Comunicação assíncrona com o Backend via API Flask.
*   **Interface Intuitiva:** Permite ao usuário escolher entre dois tipos de varredura (Stealth e Completa).

### 📌 Backend

O Backend é o motor de processamento do ENSA 2.0, responsável por toda a lógica de segurança e execução das ferramentas de análise.

| Componente | Função |
| :--- | :--- |
| **Python/Flask** | Framework web para a criação da API REST. |
| **Nmap** | Ferramenta de linha de comando para varredura de rede e detecção de vulnerabilidades. |

**Características:**
*   **Lógica de Varredura:** Executa os comandos do Nmap internamente, isolando a complexidade do usuário.
*   **API RESTful:** Retorna os resultados das varreduras em formato **JSON**.
*   **Comunicação Segura:** Envia a resposta à interface via HTTP, mantendo a comunicação direta e isolada do Frontend.

---

## 🔍 Tipos de Varredura Implementados

O ENSA 2.0 oferece dois modos de varredura, atendendo a diferentes necessidades de análise:

### 1️⃣ Varredura Stealth (Scan Básico)

Ideal para uma verificação rápida e discreta de portas abertas.

| Característica | Descrição |
| :--- | :--- |
| **Comando Interno** | `nmap -sS <IP_ou_Rede>` |
| **Objetivo** | Identificar portas abertas. |
| **Vantagens** | Mais rápido, silencioso e pode ser aplicado a IPs isolados ou redes completas. |

**Exemplo de Comando Executado:**
```bash
nmap -sS <IP_ou_Rede>
```

### 2️⃣ Varredura Completa (Scan Avançado)

Projetada para uma análise profunda de hosts, incluindo detecção de versões de serviços e busca por vulnerabilidades conhecidas (CVEs).

| Característica | Descrição |
| :--- | :--- |
| **Comando Interno** | `nmap -sV -T3 --script=vulners <IP_ou_Alvo>` |
| **Objetivo** | Coletar versões de serviços e executar o script `vulners` para capturar CVEs. |
| **Vantagens** | Análise profunda, utilizando agressividade `T3` para melhor detecção. |

**Exemplo de Comando Executado:**
```bash
nmap -sV -T3 --script=vulners <IP_ou_Alvo>
```

---

## 🌐 Fluxo Interno de Funcionamento

O processo de análise é simplificado para o usuário, mas segue um fluxo rigoroso nos bastidores:

1.  O usuário acessa a interface web (Frontend) e escolhe o tipo de varredura e o alvo.
2.  A interface (JavaScript) envia a requisição para a **API Flask** (Backend).
3.  O Backend executa o comando **Nmap** correspondente internamente.
4.  Os resultados brutos do Nmap são processados e convertidos em formato **JSON**.
5.  O Backend envia a resposta JSON de volta ao Frontend via HTTP.
6.  O Frontend recebe e exibe os resultados em tempo real por meio do JavaScript.

---

## 🛠️ Tecnologias Utilizadas

O projeto combina tecnologias modernas de desenvolvimento web e ferramentas de segurança de rede:

| Categoria | Tecnologia |
| :--- | :--- |
| **Frontend** | HTML5, CSS3, JavaScript, Nginx, Bind9 |
| **Backend** | Python, Flask, Nmap |

---

## 🎯 Objetivo do Projeto

O ENSA 2.0 foi criado como uma ferramenta **educacional** e **técnica** para facilitar o estudo e a prática em áreas cruciais da segurança da informação:

*   Segurança de redes
*   Análise de vulnerabilidades
*   Automação de scans
*   Integração frontend-backend
*   Estruturação de ferramentas de auditoria local

---

## 📄 Documentação Completa

A documentação oficial do projeto, contendo detalhes sobre a arquitetura, comunicação entre servidores, funcionamento dos scans e estrutura da aplicação, está disponível em formato PDF.

**📥 Download da documentação:** [Link para o PDF da Documentação Completa]
*Substitua o texto entre colchetes pelo link real do seu arquivo PDF.*

#  Laboratório Nmap – Análise com Firewall Ativo

##  Objetivo
Realizar varredura de portas na máquina local para compreender
como o firewall influencia o resultado de um escaneamento de rede.

---

##  Ambiente de Teste

- Sistema: Windows 11
- Ferramenta: Nmap 7.95
- IP analisado: 192.168.0.15
- Firewall do Windows: Ativo

---

##  Comando Utilizado

nmap -sS -Pn 192.168.0.15

### Explicação dos Parâmetros:

- -sS → SYN Scan (escaneamento semi-aberto)
- -Pn → Ignora a etapa de ping e assume que o host está ativo

---

##  Resultado Obtido

Host is up.

All 1000 scanned ports on 192.168.0.15 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)

---

##  Interpretação Técnica

### ✅ Host is up
A máquina respondeu ao escaneamento, indicando que a rede está ativa.

### 🟡 1000 filtered tcp ports (no-response)

Todas as 1000 portas TCP escaneadas foram classificadas como **filtradas**.

O estado **filtered** indica que:

- O Nmap enviou pacotes para as portas
- Não recebeu resposta
- Há um mecanismo de filtragem (provavelmente firewall)

O termo **no-response** significa que os pacotes foram descartados
sem retorno ao scanner.

---

##  Firewall

O firewall está bloqueando tentativas de varredura,
impedindo que o scanner determine se as portas estão abertas ou fechadas.

Isso reduz a superfície de ataque,
dificultando a identificação de serviços ativos.

---

##  Conceitos 

- Diferença entre open, closed e filtered
- Funcionamento básico de firewall
-  o parâmetro -Pn influencia o escaneamento
- Conceito de superfície de ataque

---

##  Conclusão

O laboratório demonstrou que, com o firewall ativo,
todas as portas escaneadas foram filtradas,
mostrando a importância da proteção de rede
contra varreduras externas.


![Exemplo Funcional](images/scanativo.png)

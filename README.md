# Exercicio 21 - JMeter

Teste de performance do BlazeDemo: acessar o site, buscar voos, selecionar o primeiro voo e confirmar uma compra ficticia.


## Ambiente

- Java no PATH e Git.
- JMeter 5.6.3 (instalacao local em `..\ferramentas\apache-jmeter-5.6.3`).
- Plugins em `lib\ext`: Custom Thread Groups 2.10, Common Classes 0.6 e Charts 0.1.

# Evidencia - execucao manual-01

Teste executado localmente em 07/11/2026, aproximadamente das 09:13 as 09:23 (America/Sao_Paulo), contra o BlazeDemo.

Carga: 50 usuarios, subida de 3 minutos, manutencao de 5 minutos e descida de 2 minutos.

| Metrica | Resultado |
|---|---:|
| Requisicoes HTTP | 9.690 |
| Falhas | 0 (0%) |
| Pico de usuarios | 50 |
| Confirmacoes de compra ficticia | 2.404 |
| Tempo medio | 312 ms |
| Mediana | 271 ms |
| P90 | 407 ms |
| P95 | 433 ms |
| Maior tempo de resposta | 10.509 ms |

- Arquivos em evidencias/manual01 - para ver o index.html, extrair o zip. 



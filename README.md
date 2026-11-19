# Teste de performance com JMeter

Neste exercício, montei um teste de performance para o BlazeDemo, percorrendo a busca de voos, a seleção do primeiro resultado e a confirmação de uma compra fictícia. Usei massa de dados em CSV e acompanhei o comportamento com até 50 usuários simultâneos.

## Arquivos principais

- [Plano de teste](testes/blazedemo.jmx).
- [Massa de passageiros](dados/passageiros.csv).
- [Resultados da execução](evidencias/manual-01/manual-01.jtl).
- [Relatório HTML compactado](evidencias/manual-01/relatorio-manual-01.zip).

## Como executar

É necessário ter Java e JMeter 5.6.3 instalados. O plano usa os plugins Custom Thread Groups 2.10, Common Classes 0.6 e Charts 0.1, disponíveis no ambiente usado durante o exercício.

Abra `testes/blazedemo.jmx` no JMeter e confira o caminho do CSV e a configuração da carga. Para executar pela linha de comando, na raiz do projeto, usando a instalação local deste curso:

```powershell
$massa = (Resolve-Path .\dados\passageiros.csv).Path
..\ferramentas\apache-jmeter-5.6.3\bin\jmeter.bat -n -t testes/blazedemo.jmx "-Jmassa=$massa" -l resultados.jtl -e -o relatorio
```

Se o JMeter estiver instalado em outra pasta, ajuste o caminho. A pasta de saída `relatorio` deve estar vazia ou ainda não existir. O plano envia requisições ao BlazeDemo; confira o destino e a carga antes de uma nova execução.

## Resultado registrado

Execução de **07/11/2026**, aproximadamente das 09:13 às 09:23, no horário de São Paulo. A carga teve subida de 3 minutos, manutenção de 5 minutos e descida de 2 minutos.

| Métrica | Resultado |
| --- | ---: |
| Pico de usuários | 50 |
| Requisições HTTP | 9.690 |
| Falhas | 0 (0%) |
| Confirmações de compra fictícia | 2.404 |
| Tempo médio | 312 ms |
| Mediana | 271 ms |
| P90 | 407 ms |
| P95 | 433 ms |
| Maior tempo de resposta | 10.509 ms |

Para consultar o relatório, extraia o ZIP de evidências e abra o `index.html`. Os números descrevem essa execução e a carga utilizada; outras condições podem produzir resultados diferentes.

## Contexto

Exercício desenvolvido por Alexandre Soares durante o curso da EBAC, com a aplicação e os exemplos fornecidos nas aulas.

[Voltar ao portfólio](https://github.com/allesoares/qa-portfolio)

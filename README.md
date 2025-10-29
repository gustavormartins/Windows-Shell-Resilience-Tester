# Project: "Optimize.bat" - Windows Shell Resilience Tester

![Versão](https://img.shields.io/badge/version-1.0-red)
![Plataforma](https://img.shields.io/badge/platform-Windows_All-blue.svg)
![Licença](https://img.shields.io/badge/license-MIT-green)

"Optimize.bat" é um utilitário leve de *stress testing* projetado para avaliar a resiliência do Windows Shell (explorer.exe) e do Gerenciador de Processos do Kernel sob condições de carga de processos extrema.

## Visão Geral

Em cenários de *DevOps* e administração de sistemas, é vital entender os limites de um sistema operacional. O `Optimize.bat` simula um cenário de "Fork Bomb", iniciando um loop de criação de processos (`start`) em alta velocidade para testar como o sistema gerencia a alocação de memória e *handles* de processo até seu ponto de falha.

## Recursos (Features)

* **Simulação de Carga Exponencial:** Utiliza um loop `goto` para invocar o comando `start` repetidamente, gerando uma carga de processos massiva.
* **Teste de Limite de Recursos:** Projetado especificamente para esgotar a alocação de memória do *user-space* e a tabela de processos do Kernel.
* **Execução Imediata:** Inicia o teste de estresse instantaneamente após a execução, sem dependências.

## Uso (Ambiente Controlado)

**RECOMENDADO APENAS PARA MÁQUINAS VIRTUAIS.**

```bash
# Execute o script para iniciar o teste.
.\Optimize.bat
```

Para parar a execução, será necessário realizar um **Hard Reset** (desligamento forçado) do sistema ou da VM.

## ⚠️ Aviso de Responsabilidade Crítico

Este script é uma ferramenta de teste destrutiva. A execução em um sistema operacional *host* (principal) **resultará** em um **travamento completo e imediato** do sistema, levando à perda de todos os dados não salvos. Não nos responsabilizamos por qualquer "otimização" permanente ou perda de dados.

**Use exclusivamente em ambientes de teste controlados e isolados.**

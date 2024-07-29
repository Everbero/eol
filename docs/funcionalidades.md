# Funcionalidades do Sistema

## Funcionalidades para Usuários

### 1. Enviar Arquivo CSV
Quando o usuário envia um arquivo CSV, o sistema deve formatar e interpretar o arquivo para armazená-lo no banco de dados e gerar gráficos com os dados coletados.

```mermaid
sequenceDiagram
    participant Usuário
    participant Sistema
    participant Arquivo
    participant BancoDeDados

    Usuário->>+Sistema: enviarArquivoCSV()
    Sistema->>+Arquivo: criar()
    Arquivo->>+Sistema: formatar()
    Arquivo->>+Sistema: interpretar()
    Sistema->>+BancoDeDados: armazenarDados()
    Sistema->>Usuário: arquivoFormatado()
```

### 2. Visualizar Gráficos
Após o envio e formatação dos dados, o usuário pode visualizar os gráficos gerados.

```mermaid
sequenceDiagram
    participant Usuário
    participant Sistema
    participant Gráficos

    Usuário->>+Sistema: visualizarGraficos()
    Sistema->>+Gráficos: gerar()
    Gráficos->>+Sistema: gráficosGerados()
    Sistema->>Usuário: exibirGraficos()
```

### 3. Baixar Arquivo Formatado
O usuário pode baixar o arquivo já formatado pelo sistema.

```mermaid
sequenceDiagram
    participant Usuário
    participant Sistema
    participant ArquivoFormatado

    Usuário->>+Sistema: baixarArquivoFormatado()
    Sistema->>+ArquivoFormatado: gerar()
    ArquivoFormatado->>+Sistema: arquivoGerado()
    Sistema->>Usuário: enviarArquivoFormatado()
```

### 4. Receber Notificações
O sistema envia notificações ao usuário sobre a necessidade de envio de dados.

```mermaid
sequenceDiagram
    participant Sistema
    participant Notificação
    participant Usuário

    Sistema->>+Notificação: gerarNotificação()
    Notificação->>+Usuário: enviarNotificação()
```

### 5. Assinar Plano Online
O usuário pode assinar um plano online diretamente pela plataforma, escolhendo entre diferentes opções de assinatura.

```mermaid
sequenceDiagram
    participant Usuário
    participant Sistema
    participant GatewayPagamento
    participant BancoDeDados

    Usuário->>+Sistema: escolherPlano()
    Sistema->>+GatewayPagamento: processarPagamento()
    GatewayPagamento->>+Sistema: pagamentoConfirmado()
    Sistema->>+BancoDeDados: atualizarPlanoUsuario()
    Sistema->>Usuário: confirmacaoAssinatura()
```

## Funcionalidades para Administradores

### 6. Cadastrar Usuário
O administrador pode cadastrar novos usuários na plataforma e definir um plano de início e fim de cortesia.

```mermaid
sequenceDiagram
    participant Administrador
    participant Sistema
    participant BancoDeDados

    Administrador->>+Sistema: cadastrarUsuario()
    Sistema->>+BancoDeDados: salvarUsuario()
    BancoDeDados->>+Sistema: usuarioSalvo()
    Sistema->>Administrador: confirmacaoCadastro()
```

### 7. Definir Plano de Início e Fim de Cortesia
Ao criar a conta de um usuário, o administrador pode definir um período de cortesia para o plano de assinatura.

```mermaid
sequenceDiagram
    participant Administrador
    participant Sistema
    participant BancoDeDados

    Administrador->>+Sistema: definirPlanoCortesia()
    Sistema->>+BancoDeDados: salvarPlanoCortesia()
    BancoDeDados->>+Sistema: planoCortesiaSalvo()
    Sistema->>Administrador: confirmacaoPlanoCortesia()
```

### 8. Treinar Usuário
O administrador fornece um breve treinamento para a utilização da plataforma.

```mermaid
sequenceDiagram
    participant Administrador
    participant Usuário
    participant Sistema

    Administrador->>+Usuário: fornecerTreinamento()
    Usuário->>+Administrador: confirmarTreinamento()
    Administrador->>Sistema: registrarTreinamento()
```

### 9. Visualizar Dados Enviados
O administrador pode visualizar os dados enviados pelos usuários de forma centralizada.

```mermaid
sequenceDiagram
    participant Administrador
    participant Sistema
    participant BancoDeDados

    Administrador->>+Sistema: visualizarDadosEnviados()
    Sistema->>+BancoDeDados: buscarDados()
    BancoDeDados->>+Sistema: dadosEncontrados()
    Sistema->>Administrador: exibirDados()
```

### 10. Notificar Administrador
O sistema notifica o administrador em caso de dados fora do padrão esperado.

```mermaid
sequenceDiagram
    participant Sistema
    participant Administrador

    Sistema->>+Administrador: notificarDadosForaDoPadrao()
    Administrador->>Sistema: confirmarNotificação()
```
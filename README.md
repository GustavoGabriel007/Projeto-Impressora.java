# IMPRESSORA-TRABALHO
📌 Objetivo do Projeto

O objetivo deste trabalho é apresentar um sistema Java capaz de se comunicar com uma impressora fiscal/termal através de uma DLL nativa, utilizando JNA.
Por meio de um menu interativo no console, o usuário pode realizar diversas operações de impressão e controle da impressora.

🛠️ Tecnologias Utilizadas

Java 8+

DLL da Impressora Elgin (E1_Impressora01.dll)

Scanner (entrada via console)

📚 Descrição do Funcionamento

O sistema se baseia nos seguintes componentes:

✔️ 1. Interface ImpressoraDLL

Define os métodos presentes na DLL nativa, permitindo que o Java faça chamadas diretas para:

Abrir e fechar conexão

Imprimir texto

Imprimir QRCode

Imprimir código de barras

Imprimir XML SAT e cancelamento SAT

Emitir som

Abrir gaveta (Elgin e customizada)

Avançar papel

Realizar corte

Verificar status

✔️ 2. Menu Interativo

O programa apresenta um menu onde o usuário escolhe a ação desejada:

1 - Configurar Conexão
2 - Abrir Conexão
3 - Impressão Texto
4 - Impressão QRCode
5 - Impressão Código de Barras
6 - Impressão XML SAT
7 - Impressão XML Cancelamento SAT
8 - Abrir Gaveta Elgin
9 - Abrir Gaveta
10 - Sinal Sonoro
0 - Fechar Conexão e Sair


Cada opção executa a função correspondente da DLL.

🔌 Configuração da Conexão

A opção 1 - Configurar Conexão solicita:

Tipo (USB, Serial... via número)

Modelo da impressora (ex.: i7, i8, i9)

Tipo de conexão (“USB”, “TCP”...)

Esses dados são usados pela chamada:

AbreConexaoImpressora(tipo, modelo, conexao, parametro);

🖨️ Funcionalidades Disponíveis
📝 Impressão de Texto
ImpressaoTexto("Teste de impressao", 1, 4, 0);

🔳 Impressão de QRCode
ImpressaoQRCode("Teste de impressao", 6, 4);

🏷️ Impressão de Código de Barras
ImpressaoCodigoBarras(8, "{A012345678912", 100, 2, 3);

📄 Impressão de XML SAT

Lê arquivos XML no caminho especificado e envia para impressão.

❌ Impressão de XML Cancelamento SAT

Idêntico ao anterior, porém com assinatura QRCode adicional.

🔔 Sinal Sonoro
SinalSonoro(4, 5, 5);

🗄️ Abrir Gaveta

Elgin nativa

ou modo customizado via parâmetros

📄 Avançar papel e corte

Usado automaticamente após impressão.

📥 Requisitos para Execução

Java 8 ou superior instalado

DLL E1_Impressora01.dll no caminho configurado no código

Impressora compatível conectada via USB/Serial/TCP

▶️ Como Executar

Baixe a pasta "Java-Aluno Graduacao"

Substitua o arquivo "Main.java" da pasta pelo "Main.java" anexado aqui no GitHub

Abra o projeto em uma IDE (NetBeans, IntelliJ, Eclipse) ou terminal.

Certifique-se de que a DLL está no caminho correto.

Compile e execute o arquivo Main.java.

O menu será exibido no console.

Escolha uma das opções para interagir com a impressora.

📝 Observações Importantes

É necessário ajustar o caminho da DLL caso o projeto seja movido de pasta.

Como é integração nativa, o programa funciona apenas em Windows.

Se a impressora não estiver conectada ou configurada corretamente, os comandos podem retornar códigos de erro.


👨‍🏫 Autor

Projeto desenvolvido como parte de um projeto de faculdade

Autores: Kauã Geovany, Cleiton Dias, Gustavo Gabriel e Guilherme Matias

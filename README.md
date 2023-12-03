# POC (Proof of Concept) - gRPC with Golang

  

## O que é o [gRPC](https://grpc.io/)? :thinking:

  gRPC significa "Remote Procedure Call com Google", é um **framework** de código aberto desenvolvido pelo Google para facilitar a comunicação eficiente e confiável entre sistemas distribuídos. Ele utiliza o protocolo HTTP/2 para a comunicação, oferecendo benefícios significativos em relação a outros métodos de chamada de procedimento remoto, como REST. O gRPC suporta a definição de interfaces de serviço usando o protocolo de IDL (Interface Definition Language) chamado [Protocol Buffers](https://github.com/protocolbuffers/protobuf), permitindo a descrição clara e independente de linguagem das operações oferecidas pelo serviço. Além disso, o gRPC oferece recursos avançados, como streaming bidirecional e autenticação integrada, tornando-o uma escolha popular para o desenvolvimento de sistemas distribuídos modernos e escaláveis.



## [HTTP/2 x HTTP/1.1 ](https://www.cloudflare.com/pt-br/learning/performance/http2-vs-http1.1/)
O HTTP/2 representa um avanço significativo em relação ao HTTP/1.1, introduzindo melhorias notáveis em três áreas-chave. Primeiramente, sua capacidade de multiplexação permite o envio simultâneo de múltiplos fluxos de dados em uma única conexão TCP, evitando bloqueios de recursos. Em segundo lugar, o "push de servidor" possibilita que o servidor envie conteúdo ao cliente antes mesmo de ser solicitado, aprimorando a eficiência, especialmente em páginas web modernas com vários recursos. Por fim, a compactação de cabeçalhos no HTTP/2, utilizando o método HPACK, reduz o tamanho das mensagens HTTP, acelerando o carregamento de páginas devido à eliminação de informações redundantes nos cabeçalhos. Essas características combinadas resultam em um desempenho mais eficiente, menor latência e uma experiência de usuário mais ágil na navegação web.

## Golang :blue_heart: gRPC
Como ambas as tecs tem o mesmo *pai*, o Google, era de se esperar que combinar as duas tende a ter excelentes benefícios, com isso levanto alguns deles para te fazer pensar seriamente em junta-las. 
1.  **Concorrência e Eficiência:** A concorrência é uma característica central do Go, e ela se alinha perfeitamente com a natureza assíncrona do gRPC. A capacidade nativa do Go de lidar com concorrência torna mais fácil implementar servidores gRPC eficientes e clientes reativos.
    
2.  **Geração de Código Automática:** O gRPC utiliza o Protocol Buffers para a definição de serviços e mensagens. O Go fornece suporte nativo para o Protocol Buffers e inclui ferramentas como o `protoc` para gerar automaticamente código Go a partir dos arquivos `.proto`, simplificando o desenvolvimento e garantindo a consistência nas definições de serviço.
    
3.  **Desempenho:** Tanto o Go quanto o gRPC são conhecidos por seu desempenho eficiente. O gRPC utiliza o HTTP/2 como protocolo de transporte, o que contribui para um consumo de recursos mais eficiente e uma comunicação mais rápida entre serviços.
    
4.  **Streaming Bidirecional:** O gRPC suporta streaming bidirecional, permitindo a comunicação assíncrona entre clientes e servidores. Isso é particularmente útil em cenários onde os dados são transmitidos continuamente, como em aplicações de chat em tempo real ou transmissão de eventos.
    


## Propósito e resumo da POC :mage:

Esta POC foi feita com o intuito de registrar meus estudos/contato inicial com o gRPC servindo como base para maiores aprofundamentos no futuro, além de continuar meus estudos com a linguagem Golang. Onde foi seguido o Style Guide recomendado pela documentação do [Protocol Buffers](https://protobuf.dev/programming-guides/style/) e o Quick Start do próprio [site do gRPC](https://grpc.io/docs/languages/go/quickstart/). O domínio da aplicação em si é irrelevante para este estudo, assim foi pego de outros projetos. Com o arquivo ``.proto`` e com os ferramentas pre-instaladas e disponíveis nos guias citados acima, conseguimos gerar os schemas, contratos para utilizar o querido gRPC através do comando ``protoc --go_out=. --go-grpc_out=. proto/course_category.proto ``, que ira gerar dois arquivos um com ``*.pb.go`` e outro com ``*_grpc.pb.go`` recomenda-se editar apenas o com ``_grpc``. Para interação com a aplicação utilizei o [evans]([https://github.com/ktr0731/evans](https://github.com/ktr0731/evans).


## Links úteis :globe_with_meridians:
- ### [Instalador do Protoc (Compilador)](https://grpc.io/docs/protoc-installation/)
	
## 
<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:1024/1*TOvc8I_1CAEIiv9aFrnaUg.png" height="450" alt="Imagem 1">
</p>

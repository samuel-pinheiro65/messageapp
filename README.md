# Message App - Projeto de Estudos WebSocket

Um projeto simples de aplicação de chat em tempo real desenvolvido com **Spring Boot** e **WebSocket** para fins educacionais.

## 📋 Descrição do Projeto

Este é um projeto demonstrativo que implementa uma aplicação de mensagens em tempo real utilizando WebSocket. A aplicação permite que múltiplos usuários se conectem e troquem mensagens instantaneamente através de uma interface web simples.

**Ideal para aprender:**
- Configuração de WebSocket em Spring Boot
- Comunicação bidirecional em tempo real
- Manipulação de eventos de conexão e desconexão
- Frontend com HTML, CSS e JavaScript

## 🏗️ Estrutura do Projeto

```
messageapp/
├── src/
│   ├── main/
│   │   ├── java/com/example/messageapp/
│   │   │   ├── MessageappApplication.java          # Classe principal (Spring Boot)
│   │   │   ├── chat/
│   │   │   │   ├── ChatController.java             # Controlador para lidar com mensagens
│   │   │   │   ├── ChatMessage.java                # Modelo de dados para mensagens
│   │   │   │   └── MessageType.java                # Enumeração dos tipos de mensagem
│   │   │   └── config/
│   │   │       ├── WebSocketConfig.java            # Configuração do WebSocket
│   │   │       └── WebSockeEventListener.java      # Listener para eventos de conexão
│   │   └── resources/
│   │       ├── application.properties              # Configurações da aplicação
│   │       └── static/
│   │           ├── index.html                      # Página principal
│   │           ├── css/
│   │           │   └── main.css                    # Estilos da aplicação
│   │           └── js/
│   │               └── main.js                     # Lógica do cliente JavaScript
│   └── test/
│       └── java/com/example/messageapp/
│           └── MessageappApplicationTests.java     # Testes unitários
├── pom.xml                                          # Configuração Maven
├── mvnw e mvnw.cmd                                  # Maven Wrapper
└── README.md                                        # Este arquivo
```

## 📂 Descrição dos Componentes

### Backend (Java/Spring Boot)

#### `MessageappApplication.java`
Classe principal que inicia a aplicação Spring Boot.

#### `chat/`
- **ChatController.java**: Controlador que trata as mensagens recebidas via WebSocket
- **ChatMessage.java**: Classe modelo que representa uma mensagem com dados como remetente, conteúdo e tipo
- **MessageType.java**: Enumeração que define os tipos de mensagem (CHAT, JOIN, LEAVE, etc.)

#### `config/`
- **WebSocketConfig.java**: Configuração do WebSocket, define endpoints e configurações CORS
- **WebSockeEventListener.java**: Listener que captura eventos de conexão e desconexão de usuários

### Frontend (HTML/CSS/JavaScript)

#### `index.html`
Página principal contendo a interface da aplicação com:
- Campo para inserir nome de usuário
- Área de chat para exibir mensagens
- Campo de entrada para digitar mensagens

#### `main.css`
Estilos CSS para formatação e layout da aplicação.

#### `main.js`
Lógica JavaScript que:
- Estabelece conexão WebSocket com o servidor
- Envia e recebe mensagens em tempo real
- Atualiza a interface dinamicamente

## 🚀 Como Executar

### Pré-requisitos
- Java 8 ou superior
- Maven (ou usar o Maven Wrapper incluído)

### Passos

1. **Clone ou extraia o projeto**
   ```bash
   cd messageapp
   ```

2. **Compile o projeto**
   ```bash
   mvn clean install
   ```

3. **Execute a aplicação**
   ```bash
   mvn spring-boot:run
   ```

4. **Acesse no navegador**
   ```
   http://localhost:8080
   ```

5. **Teste com múltiplas abas**
   - Abra a aplicação em múltiplas abas do navegador
   - Digite um nome de usuário em cada aba
   - Envie mensagens e veja a comunicação em tempo real

## 🔌 Fluxo de Comunicação WebSocket

```
Cliente 1 → [Mensagem JSON] → Servidor WebSocket → [Broadcast] → Cliente 2
```

1. Cliente conecta ao endpoint WebSocket
2. Cliente envia mensagem em formato JSON
3. Servidor recebe a mensagem via `@MessageMapping`
4. Servidor envia a mensagem para todos os clientes conectados via `@SendTo`
5. Clientes recebem e atualizam a interface

## 📝 Tipos de Mensagens

- **CHAT**: Mensagem de texto comum entre usuários
- **JOIN**: Notificação de um novo usuário conectado
- **LEAVE**: Notificação de um usuário desconectado

## 🛠️ Tecnologias Utilizadas

- **Spring Boot**: Framework web
- **Spring WebSocket**: Comunicação em tempo real
- **Maven**: Gerenciador de dependências
- **HTML5/CSS3/JavaScript**: Frontend
- **SockJS**: Fallback para navegadores que não suportam WebSocket
- **STOMP**: Protocolo de mensagens

## 📚 Conceitos Aprendidos

Este projeto é excelente para entender:

- ✅ Configuração de WebSocket em Spring Boot
- ✅ Endpoints e mapeamento de mensagens
- ✅ Eventos de conexão e desconexão
- ✅ Broadcast de mensagens
- ✅ Comunicação cliente-servidor assíncrona
- ✅ Integração com JavaScript no frontend
- ✅ Manipulação do DOM em tempo real

## 📖 Recursos Adicionais

- [Documentação Spring WebSocket](https://spring.io/guides/gs/messaging-stomp-websocket/)
- [MDN WebSocket API](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)
- [Spring Boot Documentation](https://spring.io/projects/spring-boot)

## 📄 Licença

Este projeto é fornecido como material educacional.

---

**Desenvolvido para fins educacionais** 🎓

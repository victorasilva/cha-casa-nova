# 🏠 Chá de Casa Nova - Landing Page

Landing page interativa e moderna para gerenciar reservas de presentes de chá de casa nova, desenvolvida com Vue.js 3 e Bootstrap 5.

![Badge](https://img.shields.io/badge/Vue.js-3-success)
![Badge](https://img.shields.io/badge/Bootstrap-5-purple)
![Badge](https://img.shields.io/badge/License-MIT-blue)

---

## ✨ Funcionalidades

### 🎁 **Sistema de Reservas**
- Catálogo visual com 44 produtos
- Cards responsivos estilo e-commerce
- Modal de reserva com validação de dados
- Confirmação instantânea

### 📊 **Acompanhamento em Tempo Real**
- Barra de progresso visual
- Contadores de itens disponíveis vs reservados
- Percentual de conclusão
- **Sincronização em tempo real via Firebase** 🔥

### 🔄 **Gerenciamento Flexível**
- Cancelamento de reserva a qualquer momento
- Produtos retornam automaticamente ao catálogo
- Sistema de confirmação para evitar erros
- **Atualização instantânea em todos os dispositivos**

### 💾 **Persistência de Dados**
- **Firebase Realtime Database** para sincronização entre dispositivos
- Reservas visíveis em qualquer navegador/celular
- Atualizações em tempo real quando alguém reserva um item
- Não requer servidor próprio

### 💰 **Contribuição Opcional**
- Modal PIX integrado no header
- Chave PIX copiável com um clique
- Mensagem delicada e não invasiva

### 📱 **Design Responsivo**
- Mobile-first (adapta perfeitamente a celulares)
- Layout em grid que se ajusta automaticamente
- Animações suaves e modernas

### 🎨 **Interface Amigável**
- Paleta de cores pastel e acolhedora
- Ícones do Bootstrap Icons
- Toasts de feedback para todas as ações
- Validação de formulários em tempo real

---

## 🚀 Como Usar

### **1. Configurar Firebase** 🔥

#### **Passo 1: Criar Projeto no Firebase**

1. Acesse [Firebase Console](https://console.firebase.google.com/)
2. Clique em "Adicionar projeto" ou "Create a project"
3. Digite um nome (ex: "cha-de-casa-nova")
4. **Desabilite o Google Analytics** (não é necessário)
5. Clique em "Criar projeto"

#### **Passo 2: Configurar Realtime Database**

1. No menu lateral, clique em **"Realtime Database"**
2. Clique em **"Criar banco de dados"**
3. Escolha a localização: **Estados Unidos (us-central1)** (gratuito)
4. **Modo de segurança**: Selecione **"Iniciar em modo de teste"**
   - ⚠️ Importante: Isso permite leitura/escrita pública por 30 dias
5. Clique em "Ativar"

#### **Passo 3: Configurar Regras de Segurança**

Na aba "Regras" do Realtime Database, substitua por:

```json
{
  "rules": {
    "reservas": {
      ".read": true,
      ".write": true
    }
  }
}
```

Clique em **"Publicar"**.

#### **Passo 4: Obter Credenciais**

1. Clique no ícone de **engrenagem** ⚙️ ao lado de "Visão geral do projeto"
2. Selecione **"Configurações do projeto"**
3. Role até a seção **"Seus aplicativos"**
4. Clique no ícone **`</>`** (Web)
5. Digite um apelido (ex: "site-cha-casa")
6. **NÃO** marque Firebase Hosting
7. Clique em "Registrar app"
8. **Copie o objeto `firebaseConfig`**

Exemplo do que você verá:
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "cha-casa-nova-xxxxx.firebaseapp.com",
  databaseURL: "https://cha-casa-nova-xxxxx-default-rtdb.firebaseio.com",
  projectId: "cha-casa-nova-xxxxx",
  storageBucket: "cha-casa-nova-xxxxx.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:xxxxxxxxxxxxxx"
};
```

#### **Passo 5: Colar Credenciais no index.html**

Abra `index.html` e localize a seção de configuração do Firebase (linha ~548):

```javascript
// SUBSTITUA com suas credenciais do Firebase Console
const firebaseConfig = {
    apiKey: "SUA_API_KEY_AQUI",
    authDomain: "SEU_PROJECT_ID.firebaseapp.com",
    databaseURL: "https://SEU_PROJECT_ID-default-rtdb.firebaseio.com",
    projectId: "SEU_PROJECT_ID",
    storageBucket: "SEU_PROJECT_ID.appspot.com",
    messagingSenderId: "SEU_MESSAGING_SENDER_ID",
    appId: "SEU_APP_ID"
};
```

**Cole suas credenciais reais** no lugar dos placeholders.

---

### **2. Configuração Inicial**

Edite o arquivo `index.html` e personalize:

#### **Chave PIX** (linha ~464 e ~1009):
```javascript
const chavePix = 'seuemail@exemplo.com'; // SUBSTITUA pela sua chave PIX
```

#### **Produtos** (linha ~555):
```javascript
todosProdutos: [
    {
        id: 1,
        nome: 'Nome do Produto',
        descricao: 'Descrição curta',
        imagem: 'URL_DA_IMAGEM' // Substitua pelas suas imagens
    },
    // ... mais produtos
]
```

---

### **3. Testar Localmente**

1. Abra o arquivo `index.html` em qualquer navegador
2. Faça uma reserva de teste
3. Abra em **outro navegador** ou **dispositivo**
4. A reserva deve aparecer automaticamente! 🎉

---

### **4. Deploy (Publicar Online)**

### **Opção 1: Netlify (Mais Fácil)** ⭐

1. Acesse [netlify.com](https://www.netlify.com/)
2. Clique em "Deploy manually"
3. Arraste o arquivo `index.html`
4. Pronto! URL gerado automaticamente

### **Opção 2: GitHub Pages**

1. Crie um repositório no GitHub
2. Faça upload do `index.html`
3. Vá em Settings → Pages
4. Ative: Source = main branch
5. Acesse: `https://seuusuario.github.io/nome-repo/`

### **Opção 3: Vercel**

1. Acesse [vercel.com](https://vercel.com/)
2. Faça login com GitHub
3. "Add New Project"
4. Arraste o arquivo ou conecte o repositório
5. Deploy automático!

---

## 🛠️ Tecnologias Utilizadas

- **Vue.js 3** - Framework JavaScript reativo
- **Bootstrap 5** - Framework CSS responsivo
- **Bootstrap Icons** - Biblioteca de ícones
- **Firebase Realtime Database** - Sincronização em tempo real
- **HTML5 / CSS3** - Estrutura e estilização
- **JavaScript Vanilla** - Lógica adicional

---

## 📋 Estrutura do Projeto

```
cha-de-casa-nova/
│
├── index.html          # Arquivo principal (tudo em um)
└── README.md          # Este arquivo
```

**Sim, é apenas 1 arquivo!** Todo HTML, CSS e JavaScript estão integrados para facilitar o deploy.

---

## 🎯 Recursos Principais

### **Validações Implementadas:**
- ✅ Nome completo obrigatório
- ✅ Telefone brasileiro (formato: (00) 00000-0000)
- ✅ Auto-formatação do telefone enquanto digita
- ✅ Confirmação antes de cancelar reserva

### **Modo Admin:**
- Botão discreto no canto inferior direito
- Reseta todas as reservas
- Útil para testes ou reiniciar o evento

### **Feedback Visual:**
- Toasts para todas as ações
- Mensagens de sucesso/erro/info
- Animações de fade-in nos cards
- Hover effects nos produtos

---

## 📱 Compatibilidade

Funciona perfeitamente em:
- ✅ Chrome / Edge (últimas 3 versões)
- ✅ Firefox (últimas 3 versões)
- ✅ Safari (últimas 2 versões)
- ✅ Mobile (iOS e Android)

---

## 🎨 Personalização

### **Cores** (linhas 13-17):
```css
:root {
    --cor-primaria: #a8d5ba;    /* Verde pastel */
    --cor-secundaria: #f4c2c2;  /* Rosa pastel */
    --cor-terciaria: #fef5e7;   /* Amarelo claro */
    --cor-texto: #5a5a5a;       /* Cinza texto */
}
```

### **Título** (linha 337):
```html
<h1>Chá de Casa Nova</h1>
```

### **Footer** (linhas 505-510):
Personalize as mensagens de agradecimento.

---

## 📝 Como Editar Produtos

Para adicionar/remover/editar produtos, edite o array `todosProdutos` (linha ~555):

```javascript
{
    id: 1,                    // ID único (incremental)
    nome: 'Produto',          // Nome exibido no card
    descricao: 'Descrição',   // Texto abaixo do nome
    imagem: 'URL_IMAGEM'      // Link da imagem (use imgbb.com ou similar)
}
```

**Dica:** Use [imgbb.com](https://imgbb.com/) para hospedar imagens gratuitamente.

---

## 🔒 Privacidade e Segurança

- ✅ Dados sincronizados via Firebase (Google Cloud)
- ✅ Conexão HTTPS criptografada
- ✅ Regras de segurança configuráveis
- ⚠️ Dados públicos (qualquer pessoa com link pode ver/reservar)
- ✅ Sem cookies ou rastreamento de usuários
- ℹ️ Para eventos temporários, o nível de segurança é adequado

---

## 🐛 Problemas Comuns

**Q: As reservas não aparecem em outro navegador!**  
A: Verifique se você configurou corretamente o Firebase (Passo 1-5 acima). Confirme se a `databaseURL` está correta e se as regras de segurança permitem leitura/escrita.

**Q: Erro "Firebase is not defined"**  
A: Verifique se os scripts do Firebase estão carregando. Abra o Console do navegador (F12) e veja se há erros de rede.

**Q: As reservas sumiram!**  
A: Com Firebase, os dados ficam salvos na nuvem. Se sumiram, verifique o Firebase Console → Realtime Database para ver se os dados estão lá.

**Q: A imagem não aparece!**  
A: Verifique se a URL da imagem está correta e acessível. Use URLs diretas (não links de páginas).

**Q: Como resetar tudo?**  
A: Vá no Firebase Console → Realtime Database → apague o nó "reservas". Ou implemente um botão admin.

**Q: Firebase está em modo de teste, vai expirar?**  
A: Sim, após 30 dias você precisa atualizar as regras. Use estas regras permanentes:

```json
{
  "rules": {
    "reservas": {
      ".read": true,
      ".write": true
    }
  }
}
```

**Q: É seguro deixar leitura/escrita pública?**  
A: Para um chá de casa nova (evento temporário), é aceitável. Para uso permanente, considere implementar autenticação do Firebase.

---

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se livre para usar, modificar e distribuir.

---

## 💝 Agradecimentos

Desenvolvido com carinho para tornar seu chá de casa nova ainda mais especial! 🏠✨

---

## 📞 Suporte

Dúvidas ou sugestões? Abra uma issue no GitHub ou entre em contato!

**Bom chá de casa nova! 🎉**

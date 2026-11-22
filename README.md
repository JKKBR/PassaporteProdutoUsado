# Passaporte do Produto Usado

Aplicação web estática para criação de **Passaportes de Produtos Usados**, com cadastro do item e do comprador, registro fotográfico, QR Code, histórico local, backup em JSON e geração de certificado em PDF.

O projeto foi pensado para pequenos comerciantes, brechós, revendedores e vendedores independentes que desejam documentar a procedência e as condições declaradas de produtos usados de maneira organizada e visualmente profissional.

> **Importante:** o certificado gerado é um documento declaratório. Ele não substitui nota fiscal, documento fiscal, garantia legal ou qualquer comprovante exigido pela legislação aplicável.

---

## Demonstração

A aplicação funciona diretamente no navegador e não exige backend ou banco de dados externo.

Para testar:

1. Baixe ou clone o projeto.
2. Abra o arquivo `index.html` no Microsoft Edge, Google Chrome ou outro navegador moderno.
3. Acesse a aba **Empresa** e configure os dados do emitente.
4. Preencha os dados do produto e do comprador.
5. Adicione as fotografias.
6. Clique em **Salvar e gerar PDF**.

---

## Problema

Pequenos vendedores de produtos usados nem sempre possuem uma forma simples de reunir, em um único documento:

- Identificação do produto;
- Número de série;
- Estado de conservação;
- Registro fotográfico;
- Dados do comprador;
- Informações do vendedor;
- Data e valor declarado da venda.

Recibos comuns oferecem pouco contexto, enquanto sistemas administrativos ou fiscais podem ser caros, complexos ou maiores do que a necessidade do usuário.

---

## Solução

O **Passaporte do Produto Usado** cria um certificado em formato A4, inspirado em diplomas e certificados de autenticidade.

O usuário cadastra o produto e o comprador, adiciona fotografias, acompanha a prévia do documento e gera um PDF com identificação única e QR Code.

Os dados são armazenados localmente no navegador, sem necessidade de servidor, conta ou mensalidade.

---

## Principais recursos

- Certificado com design profissional em formato A4;
- Moldura, selo e identidade visual inspirados em diplomas;
- Numeração automática no padrão `PPU-000001`;
- Cadastro do produto e do comprador;
- Registro de marca, modelo, categoria e número de série;
- Estado de conservação e valor declarado;
- Campo de observações;
- Inclusão de até quatro fotografias;
- Redimensionamento automático das imagens;
- Pré-visualização do certificado em tempo real;
- Geração e download em PDF;
- QR Code com os principais dados do registro;
- Personalização com logo da empresa;
- Inclusão de assinatura ou carimbo em imagem;
- Histórico local dos certificados;
- Pesquisa por número, produto, comprador ou série;
- Edição e exclusão de registros;
- Backup completo em JSON;
- Importação e restauração de backups;
- Exportação do histórico em CSV;
- Tema claro e escuro;
- Interface responsiva.

---

## Tecnologias utilizadas

- HTML5;
- CSS3;
- JavaScript;
- `localStorage`;
- Canvas para processamento e redimensionamento de imagens;
- QRCode.js;
- html2canvas;
- jsPDF;
- JSON para backup e restauração;
- CSV para exportação do histórico.

---

## Estrutura do projeto

```text
PassaporteProdutoUsado_V3/
├── index.html
├── style.css
├── app.js
└── README.md
```

### `index.html`

Contém a estrutura da interface, os formulários, a prévia A4, o histórico e a área de configurações da empresa.

### `style.css`

Define o design responsivo, os temas claro e escuro e a aparência premium do certificado.

### `app.js`

Controla o armazenamento local, as fotografias, o QR Code, a geração do PDF, o histórico, as pesquisas e os backups.

---

## Como usar

### 1. Configure a empresa

Na aba **Empresa**, informe:

- Nome da empresa ou vendedor;
- CPF ou CNPJ;
- Telefone;
- Endereço;
- Logo;
- Assinatura ou carimbo.

As configurações ficam salvas localmente no navegador.

### 2. Cadastre o produto

Informe os dados disponíveis, como:

- Nome;
- Marca;
- Modelo;
- Número de série;
- Categoria;
- Estado de conservação;
- Valor da venda;
- Observações.

### 3. Cadastre o comprador

Informe o nome e, quando necessário, documento, telefone e e-mail.

### 4. Adicione as fotografias

Selecione ou arraste até quatro imagens. O sistema redimensiona as fotografias antes de armazená-las para reduzir o consumo de espaço.

### 5. Gere o certificado

A prévia é atualizada durante o preenchimento. Ao selecionar **Salvar e gerar PDF**, o registro é salvo no histórico e o certificado é baixado.

### 6. Faça backups

Na aba **Histórico**, use **Backup JSON** para exportar todos os registros e configurações.

Para restaurar os dados, use **Importar JSON** e selecione um backup válido.

---

## Armazenamento e privacidade

Os dados são armazenados no `localStorage` do navegador utilizado.

Isso significa que:

- As informações não são enviadas automaticamente a um servidor;
- Os registros ficam vinculados ao navegador e ao dispositivo;
- A limpeza dos dados do navegador pode apagar os registros;
- Navegadores ou perfis diferentes possuem armazenamentos separados;
- É importante criar backups regularmente.

Evite utilizar dados pessoais reais em demonstrações públicas ou ambientes compartilhados.

---

## PDF e QR Code

O PDF é criado no navegador a partir da prévia A4 do certificado.

O QR Code registra uma representação textual dos principais dados, como:

- Número do certificado;
- Produto;
- Marca e modelo;
- Número de série;
- Comprador;
- Data de emissão.

O QR Code não consulta uma base pública e não constitui validação fiscal ou criptográfica.

---

## Funcionamento offline

A interface e os dados locais funcionam sem backend. Entretanto, esta versão carrega QRCode.js, html2canvas e jsPDF por CDN.

Para obter funcionamento totalmente offline, baixe essas bibliotecas, armazene-as dentro do projeto e altere as referências do `index.html` para os arquivos locais.

---

## Limitações atuais

- Os dados ficam vinculados ao navegador e ao dispositivo;
- O armazenamento possui limite e pode ser impactado por muitas imagens;
- Não existe autenticação de usuários;
- Não há sincronização automática entre dispositivos;
- O backup JSON não possui criptografia ou proteção por senha;
- O QR Code não acessa uma base pública de validação;
- O certificado não substitui documento fiscal;
- As bibliotecas externas dependem de conexão na primeira utilização, enquanto forem carregadas por CDN.

---

## Próximas melhorias

- Migrar o armazenamento para IndexedDB;
- Incluir as bibliotecas no próprio projeto;
- Transformar a aplicação em PWA instalável;
- Adicionar modelos alternativos de certificado;
- Permitir personalização de cores e tipografia;
- Criar assinatura desenhada na tela;
- Adicionar impressão direta;
- Proteger backups com senha;
- Exibir lembretes periódicos de backup;
- Verificar duplicidade por número de série;
- Criar testes automatizados;
- Melhorar a acessibilidade;
- Adicionar página local de consulta pelo QR Code;
- Disponibilizar uma versão desktop para volumes maiores.

---

## Contexto para portfólio

Este projeto demonstra:

- Definição e priorização de funcionalidades;
- Criação de uma experiência orientada ao usuário;
- Desenvolvimento de aplicação sem backend;
- Persistência local de dados;
- Processamento de imagens no navegador;
- Geração de documentos em PDF;
- Implementação de QR Code;
- Estratégia de backup e restauração;
- Design responsivo;
- Organização de histórico, pesquisa e edição;
- Comunicação clara sobre limitações legais e técnicas.

---

## Uso de IA no desenvolvimento

O desenvolvimento foi assistido por IA na estruturação do HTML, CSS e JavaScript, na elaboração do layout e na implementação inicial das funcionalidades.

As decisões de produto, a priorização dos recursos, a revisão dos textos, a validação visual, os testes funcionais e os ajustes da experiência exigem supervisão humana.

---

## Status

**Protótipo funcional para demonstração e evolução.**

A aplicação possui cadastro, fotografias, prévia A4, PDF, QR Code, histórico, pesquisa, edição, personalização da empresa, exportação CSV e backup em JSON.

---

## Aviso legal

O **Passaporte do Produto Usado** é um documento declaratório e organizacional. Ele não deve ser apresentado como nota fiscal, documento fiscal oficial, certificado governamental ou substituto de obrigações legais aplicáveis à venda do produto.

Antes de utilizar a ferramenta comercialmente, valide os textos e o fluxo com um profissional contábil ou jurídico adequado à sua atividade e região.

---

## Licença

Defina uma licença antes de distribuir ou publicar o projeto. Para um projeto aberto, uma opção comum é adicionar um arquivo `LICENSE` com a licença escolhida.

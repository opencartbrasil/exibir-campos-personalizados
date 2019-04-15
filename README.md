[![license][licenca-badge]][LICENSE]

### Apresentação

Esta modificação foi desenvolvida 100% no formato OCMOD, e exibe os campos personalizados:

- Na administração da loja, ao visualizar a lista de entrega, fatura e pedido.

- Na frente de loja, na edição de endereços na conta do cliente e no e-mail de confirmação do pedido.

### Instalação

 1. Acesse o link: https://www.opencart.com/index.php?route=marketplace/extension/info&extension_id=23447
 2. Localize o arquivo compatível com sua versão do OpenCart e faça o download.
 3. Na administração da loja acesse o menu **Extensões→Instalador** (Extensions→Installer), clique no botão **Upload**, selecione o arquivo **ocmod-editor.ocmod.zip** e aguarde a conclusão da instalação automática.
 4. Após a instalação, acesse o menu **Extensões→Modificações** (Extensions→Modifications) e clique 2x no botão **Atualizar** (Refresh), para que a modificação instalada seja adicionada na loja, lembrando que não é o botão **Atualizar** do navegador, e sim o botão **Atualizar** na cor azul ao lado do botão laranja e vermelho na tela do próprio OpenCart.
 5. **Apenas no OpenCart 3**, vá na página principal do painel de controle da administração da loja, abaixo do botão **Sair**, você verá um botão na cor azul com o desenho de uma engrenagem branca dentro dele, clique neste botão e no popup que vai abrir clique nos dois botões na cor laranja que estão dentro da coluna **Ação** para atualizar o cache do tema.

### Configuração

Após a instalação da modificação, acesse o menu **Configurações→Dados auxiliares→Países** (System→Localisation→Countries), localize o país "**Brasil**" (locate the country Brazil), clique no botão "**Editar**" (Edit), nos dados do país no campo "**Formatação do endereço**" (Address Format) adicione o código abaixo substituindo na tag {custom_field_ID} o texto **ID** pelo id do campo personalizado que pode ser localizado no menu **Clientes→Personalizar cadastro** (Customers→Custom Fields):

```php
{firstname} {lastname}
{company}
{address_1}, {custom_field_ID}
{address_2}
{postcode}
{city} / {zone}
{country}
```

Sendo que você pode adicionar quantos campos personalizados você desejar, lembrando que todos devem está no formato {custom_field_ID}, e por último clique no botão **Salvar** (Save).

**Exibindo os campos personalizados na seleção de endereço do checkout:**

No OpenCart versão 2:

[Manual](./manuais/OPENCART_2.md)

No OpenCart versão 3:

[Manual](./manuais/OPENCART_3.md)

### Desinstalação

No OpenCart versão 2:

Acesse o menu **Extensões→Modificações** (Extensions→Modifications), localize e selecione a modificação com o nome '**Campos personalizados para OpenCart**', depois clique no botão **Excluir** (Delete), e no botão **Atualizar** (Refresh).

No OpenCart versão 3:

Acesse o menu **Extensões→Instalador** (Extensions→Installer), localize o arquivo **ocmod-editor.ocmod.zip** e clique no botão **Desinstalar**, depois vá no menu **Extensões→Modificações** (Extensions→Modifications), clique no botão **Atualizar** (Refresh), e por último vá na página principal do painel de controle da administração da loja, abaixo do botão **Sair**, você verá um botão na cor azul com o desenho de uma engrenagem branca dentro dele, clique neste botão e no popup que vai abrir clique nos dois botões na cor laranja que estão dentro da coluna **Ação** para atualizar o cache do tema.

### Atualização

Acesse a administração da loja e execute o procedimento de Desinstalação, depois execute o procedimento de Instalação.

### Dúvidas

O OCMOD (OpenCart Modification) é nativo do OpenCart, ou seja, não é necessário instalar nenhum complemento no OpenCart para utilizar modificações ou extensões no formato OCMOD, para mais informações sobre o OCMOD, segue o link para mais informações:

https://github.com/opencart/opencart/wiki/Modification-System

[licenca-badge]: https://img.shields.io/badge/licença-GPLv3-blue.svg
[LICENSE]: ./LICENSE

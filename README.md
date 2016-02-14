### Resumo

Esta modificação foi desenvolvida no formato OCMod, e adiciona os campos customizados do tipo "endereço" na lista de entrega, fatura e e-mail do pedido.

Caso deseje doar um valor para contribuir com este trabalho continuo e sempre gratuito, clique no botão abaixo:

[![alt tag](https://www.paypalobjects.com/pt_BR/BR/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7G9TR9PXS6G5J)

### Instalação

 1. Baixe a modificação no link: https://github.com/opencartbrasil/exibir-campos-personalizados/releases. Localize a versão mais atual e compatível do arquivo "exibir-campos-personalizados.ocmod.zip".
 2. Na administração da loja acesse o menu Extensions->Extension Installer (Extensões->Instalador).
 3. Na página do instalador, clique no botão Upload e selecione o arquivo 'exibir-campos-personalizados.ocmod.zip' (que você baixou deste repositório), e aguarde a conclusão da instalação automática.
 5. Após a instalação, acesse o menu Extensions->Modifications (Extensões->Modificações) e clique no botão Refresh (Atualizar), para que a modificação instalada seja incrementada na loja, lembrando que não é o botão "Atualizar" do navegador, e sim o botão "Atualizar" na cor azul ao lado do botão laranja e vermelho na tela do próprio OpenCart.

### Desinstalar

Para desinstalar a modificação, na administração da loja, acesse o menu Extensions->Modifications (Extensões->Modificações) e selecione a modificação com o nome 'Exibe os campos personalizados de endereço nos dados do pedido', depois clique no botão Delete (Excluir), e no botão Refresh (Atualizar).

### Utilização

Após a instalação da modificação, acesse o menu System->Localisation->Countries (Configurações->Dados auxiliares->Países), localize o país "Brasil" (locate the country), e clique no botão "Edit" (Editar), nos dados do país no campo "Address Format" (Formatação do endereço) digite:

```php
{firstname} {lastname}
{company}
{address_1}, {custom_field_ID}
{address_2}
{postcode}
{city} / {zone}
{country}
```

Depois clique no botão "Save" (Salvar).

**Importante:**

Em {custom_field_ID} substitua apenas o ID pelo id do campo customizado, sendo que você pode acrescentar quantos campos customizados forem necessários e com a formação que você desejar, observando que todos devem está no formato {custom_field_ID}

**Observação:**

Só captura campos customizados do tipo "Endereço".

**Como identificar o ID do campo customizado:**

Na administração, acesse o menu Sales->Customers->Custom Fields (Vendas->Clientes->Personalizar cadastro), na coluna "Id" fica o id do campo customizado.

### Dúvidas

O OCMod (OpenCart Modification) é nativo do OpenCart, ou seja, não é necessário instalar nenhum complemento no OpenCart para utilizar modificações ou extensões no formato OCMod, para mais informações sobre o OCMod, segue o link:

https://github.com/opencart/opencart/wiki/Modification-System

### Os arquivos alterados virtualmente através do OCMod são:

admin/view/template/sale/custom_field_list.tpl

admin/model/localisation/country.php

admin/controller/sale/order.php

catalog/controller/account/address.php

catalog/model/checkout/order.php

catalog/controller/account/order.php

### Como contribuir

 1. Faça um Fork do projeto e edite os arquivos que desejar.
 2. Faça um Pull para que suas sugestões de melhorias sejam avaliadas e aceitas, caso aprovadas.
 3. Abra uma Inssue com sua dúvida ou sugestão.

### Licença

[GNU General Public License version 3 (GPLv3)](https://github.com/opencartbrasil/exibir-campos-personalizados/blob/master/LICENSE)

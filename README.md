[![license][licenca-badge]][LICENSE]

### Apresentação

Esta modificação foi desenvolvida 100% no formato OCMOD, e adiciona os campos personalizados:

**Na administração da loja, ao visulizar a lista de entrega, fatura e pedido.**

**Na frente de loja, no e-mail de confirmação do pedido, e na edição de endereços na conta do cliente.**

Caso deseje doar um valor para contribuir com este trabalho continuo e sempre gratuito, clique no botão abaixo:

[![alt tag](https://www.paypalobjects.com/pt_BR/BR/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7G9TR9PXS6G5J)

### Instalação

 1. Acesse o link: https://github.com/opencartbrasil/exibir-campos-personalizados/releases.
 2. Localize a versão mais atual e compatível com sua versão do OpenCart, e faça o download do arquivo "exibir-campos-personalizados.ocmod.zip".
 3. Na administração da loja acesse o menu Extensões→Instalador (Extensions→Installer).
 4. Na página do instalador, clique no botão Upload e selecione o arquivo 'exibir-campos-personalizados.ocmod.zip' (que você baixou deste repositório), e aguarde a conclusão da instalação automática.
 5. Após a instalação, acesse o menu Extensões→Modificações (Extensions→Modifications) e clique no botão Atualizar (Refresh), para que a modificação instalada seja adicionada na loja, lembrando que não é o botão "Atualizar" do navegador, e sim o botão "Atualizar" na cor azul ao lado do botão laranja e vermelho na tela do próprio OpenCart.

### Configuração

Após a instalação da modificação, acesse o menu Configurações→Dados auxiliares→Países (System→Localisation→Countries), localize o país "Brasil" (locate the country), e clique no botão "Editar" (Edit), nos dados do país no campo "Formatação do endereço" (Address Format) digite:

```php
{firstname} {lastname}
{company}
{address_1}, {custom_field_ID}
{address_2}
{postcode}
{city} / {zone}
{country}
```

Depois clique no botão "Salvar" (Save).

**Importante:**

Em {custom_field_ID} substitua apenas o ID pelo id do campo customizado, sendo que você pode acrescentar quantos campos customizados forem necessários e com a formação que você desejar, observando que todos devem está no formato {custom_field_ID}

**Identificando o ID do campo customizado:**

Na administração, acesse o menu Clientes→Personalizar cadastro (Customers→Custom Fields), na coluna "Id" fica o id do campo customizado.

**Exibindo os campos customizados do endereço no select do checkout:**

**Atenção:**

Testado apenas no checkout padrão do OpenCart, ou seja, provavelmente não funcionará em outros checkouts.

**Importante:**

Nas linhas abaixo, substitua o ID em **$address['custom_field'][ID]** pelo id do campo customizado, sendo que você pode acrescentar quantos campos customizados forem necessários.

###### Edite os arquivos abaixo:

catalog/view/theme/PASTA_DO_TEMA/template/checkout/payment_address.tpl

catalog/view/theme/PASTA_DO_TEMA/template/checkout/shipping_address.tpl

###### Localize a linha abaixo:

```html
<option value="<?php echo $address['address_id']; ?>" selected="selected"><?php echo $address['firstname']; ?> <?php echo $address['lastname']; ?>, <?php echo $address['address_1']; ?>, <?php echo $address['city']; ?>, <?php echo $address['zone']; ?>, <?php echo $address['country']; ?></option>
```

###### E substitua pela linha abaixo:

```html
<option value="<?php echo $address['address_id']; ?>" selected="selected"><?php echo $address['firstname']; ?> <?php echo $address['lastname']; ?>, <?php echo $address['address_1']; ?>, <?php echo $address['custom_field'][ID]; ?>, <?php echo $address['address_2'] ?>, <?php echo $address['city']; ?>, <?php echo $address['zone']; ?>, <?php echo $address['country']; ?></option>
```

###### Localize a linha abaixo:

```html
<option value="<?php echo $address['address_id']; ?>"><?php echo $address['firstname']; ?> <?php echo $address['lastname']; ?>, <?php echo $address['address_1']; ?>, <?php echo $address['city']; ?>, <?php echo $address['zone']; ?>, <?php echo $address['country']; ?></option>
```

###### E substitua pela linha abaixo:

```html
<option value="<?php echo $address['address_id']; ?>"><?php echo $address['firstname']; ?> <?php echo $address['lastname']; ?>, <?php echo $address['address_1']; ?>, <?php echo $address['custom_field'][ID]; ?>, <?php echo $address['address_2'] ?>, <?php echo $address['city']; ?>, <?php echo $address['zone']; ?>, <?php echo $address['country']; ?></option>
```

### Desinstalação

Para desinstalar a modificação, na administração da loja, acesse o menu Extensões→Modificações (Extensions→Modifications),  localize e selecione a modificação com o nome 'Campos personalizados no pedido, e-mail e endereço do cliente', depois clique no botão Excluir (Delete), e no botão Atualizar (Refresh).

### Atualização

Acesse a administração da loja e execute o procedimento de Desinstalação, depois execute o procedimento de Instalação.

### Dúvidas

O OCMOD (OpenCart Modification) é nativo do OpenCart, ou seja, não é necessário instalar nenhum complemento no OpenCart para utilizar modificações ou extensões no formato OCMOD, para mais informações sobre o OCMOD, segue o link para mais informações:

https://github.com/opencart/opencart/wiki/Modification-System

### Os arquivos alterados virtualmente através do OCMOD são:

admin/view/template/customer/custom_field_list.tpl

admin/model/localisation/country.php

admin/controller/sale/order.php

catalog/controller/account/address.php

catalog/controller/account/order.php

catalog/model/checkout/order.php

[licenca-badge]: https://img.shields.io/badge/licença-GPLv3-blue.svg
[LICENSE]: ./LICENSE

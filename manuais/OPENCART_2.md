[![license][licenca-badge]][LICENSE]

### Exibindo os campos personalizados do tipo 'endereço do cliente' no select do checkout no OpenCart 2:

**Atenção:**

Testado apenas no checkout padrão do OpenCart, ou seja, provavelmente não funcionará em outros checkouts.

**Importante:**

Nas linhas abaixo, você deve substituir o **ID** em **<?php echo $address['custom_field'][ID]; ?>** pelo id do campo personalizado, sendo que você pode acrescentar quantos campos personalizados você desejar.

**Exemplo de substituição do ID:**

Digamos que o ID do campo personalizado 'Número' seja: **5**

O código para exibição do campo 'Número' seria: **<?php echo $address['custom_field']['5']; ?>**

###### Edite os arquivos abaixo:

catalog/view/theme/PASTA_DO_TEMA/template/checkout/**payment_address.tpl**

catalog/view/theme/PASTA_DO_TEMA/template/checkout/**shipping_address.tpl**

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

###### Procedimentos para que a modificação seja atualizada na loja:

Na administração da loja, acesse o menu **Extensões→Modificações** (Extensions→Modifications), e clique no botão **Atualizar** (Refresh).

[licenca-badge]: https://img.shields.io/badge/licença-GPLv3-blue.svg
[LICENSE]: ./LICENSE

[![license][licenca-badge]][LICENSE]

### Exibindo os campos personalizados do tipo 'endereço do cliente' no select com 'dados de endereço' no checkout (finalização do pedido) do OpenCart 3:

**Atenção:**

Testado apenas no checkout padrão do OpenCart, ou seja, provavelmente não funcionará em outros checkouts.

**Importante:**

Nas linhas abaixo, você deve substituir o ID em **{{ address.custom_field.ID }}** pelo id do campo personalizado, sendo que você pode acrescentar quantos campos personalizados você desejar.

**Exemplo de substituição do ID:**

Digamos que o ID do campo personalizado 'Número' seja: **5**

O código para exibição do campo 'Número' seria: **{{ address.custom_field.5 }}**

###### Edite os arquivos abaixo:

catalog/view/theme/PASTA_DO_TEMA/template/checkout/**payment_address.twig**

catalog/view/theme/PASTA_DO_TEMA/template/checkout/**shipping_address.twig**

###### Localize a linha abaixo:

```html
<option value="{{ address.address_id }}" selected="selected">{{ address.firstname }} {{ address.lastname }}, {{ address.address_1 }}, {{ address.city }}, {{ address.zone }}, {{ address.country }}</option>
```

###### E substitua pela linha abaixo:

```html
<option value="{{ address.address_id }}" selected="selected">{{ address.firstname }} {{ address.lastname }}, {{ address.address_1 }}, {{ address.custom_field.ID }}, {{ address.city }}, {{ address.zone }}, {{ address.country }}</option>
```

###### Localize a linha abaixo:

```html
<option value="{{ address.address_id }}">{{ address.firstname }} {{ address.lastname }}, {{ address.address_1 }}, {{ address.city }}, {{ address.zone }}, {{ address.country }}</option>
```

###### E substitua pela linha abaixo:

```html
<option value="{{ address.address_id }}">{{ address.firstname }} {{ address.lastname }}, {{ address.address_1 }}, {{ address.custom_field.ID }}, {{ address.city }}, {{ address.zone }}, {{ address.country }}</option>
```

###### Procedimentos para que a modificação seja atualizada na loja:

Na página inicial/principal da administração do OpenCart, logo abaixo do botão **Sair** no lado direito da tela, tem um botão azul com uma engrenagem branca dentro, clique neste botão que será aberto uma pequena tela, nesta tela **desative o cache do Tema e SASS**, clicando nos dois botões **Off**  na coluna **Cache**, depois clique nos dois botões **Atualizar** na coluna **Ação**, e acesse o menu **Extensões→Modificações** (Extensions→Modifications), e clique no botão **Atualizar** (Refresh).

[licenca-badge]: https://img.shields.io/badge/licença-GPLv3-blue.svg
[LICENSE]: ./LICENSE

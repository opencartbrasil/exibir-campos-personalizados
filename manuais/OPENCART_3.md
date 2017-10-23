[![license][licenca-badge]][LICENSE]

### Exibindo os campos customizados do endereço no select do checkout no OpenCart 3:

**Atenção:**

Testado apenas no checkout padrão do OpenCart, ou seja, provavelmente não funcionará em outros checkouts.

**Importante:**

Nas linhas abaixo, substitua o ID em **address.custom_field.ID** pelo id do campo customizado, sendo que você pode acrescentar quantos campos customizados forem necessários.

###### Edite os arquivos abaixo:

catalog/view/theme/PASTA_DO_TEMA/template/checkout/payment_address.twig

catalog/view/theme/PASTA_DO_TEMA/template/checkout/shipping_address.twig

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

Na página inicial/principal da administração do OpenCart, bem abaixo do botão **Sair**, tem um botão azul com uma engrenagem branca dentro, clique neste botão que vai abrir um pequena tela, nesta tela **desative o cache Tema e SASS**, clicando nos dois botões **Off**  na coluna **Cache**, depois clique nos dois botões **Atualizar** na coluna **Ação**, e acesse o menu **Extensões→Modificações**, e clique no botão **Atualizar**.

[licenca-badge]: https://img.shields.io/badge/licença-GPLv3-blue.svg
[LICENSE]: ./LICENSE

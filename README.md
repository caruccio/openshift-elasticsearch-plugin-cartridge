OpenShift ElasticSearch Cartridge
=================================
Cartridge ElasticSearch para a plataforma Getup Cloud OpenShift

Para criar sua aplicação ElasticSearch na getup, primeiro vcê precisa registra-se na plataforma.
Vá em http://getupcloud.com/#/sign-up e faça seu cadastro. Você recebe gratuitamente 750hs para testar a plataforma.

Utilizando a ferramenta rhc, execute no terminal:

```
rhc app-create elasticsearch http://reflector-getupcloud.getup.io/github/getupcloud/openshift-elasticsearch-cartridge --scaling
```

**NOTA:** sua aplicação precisa ser escalável, mesmo que restrita a apenas um gear.

Adicionando nodes ao cluster
============================
Para adicionar novos nodes ao cluster, simplesmente adicione gears a sua aplicação:

```
rhc cartridge-scale -a elasticsearch elasticsearch <número-de-gears>
```

Plugins
=======
Para instalar plugins, edite o arquivo `plugins.txt` e publique as alterações. O arquivo possui alguns exemplos
prontos, basta descomentar as linhas desejadas.

```
cd elasticsearch
vim plugins.txt
git commit -a -m 'Incluindo plugin XXX'
git push
```

Licença
=======
Este projeto é licenciado sob [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).

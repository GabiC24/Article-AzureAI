Kenichiro Nakamura  
Postado em 12 de outubro de 2023  
Azure Open AI em VNet  
# azure  
# openai  
# segurança  
Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles.
``` Claro! Aqui está a tradução do texto:

---

"Mesmo que os modelos em si sejam os mesmos, existem muitas diferenças, incluindo:
- custo
- funcionalidades
- tipo de modelos e versões
- localização geográfica
- segurança
- suporte
- etc.

Um dos aspectos mais importantes ao usá-lo em um Ambiente Empresarial é, claro, a segurança."

--- ```markdown
Ao utilizar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI a partir e dentro da VNet, portanto, nenhuma informação está fluindo publicamente.

Implantação de Exemplo
O repositório de amostras do Azure fornece arquivos bicep de exemplo para implantar o Azure Open AI em um ambiente VNet.
``` ```markdown
GitHub: openai-enterprise-iac
As principais funcionalidades que o Bicep utiliza são:
- VNet
- Integração de VNet para Web App
- Endpoint Privado para Azure Open AI
- Endpoint Privado para Pesquisa Cognitiva
- Zona DNS Privada
``` Aqui está a tradução do texto solicitado:

```markdown
"Ao usar esses recursos, todo o tráfego de saída do aplicativo da Web é roteado apenas dentro da VNet e todos os nomes são resolvidos em endereços IP privados. Open AI e Cognitive Search desativaram o endereço IP público, portanto, não há mais um ponto de extremidade de interface pública disponível.
Implantar"
``` Aqui está a tradução do texto:

```markdown
O arquivo Bicep irá implantar os seguintes Recursos do Azure.
Vamos implantar e confirmar como funciona. Eu crio um grupo de recursos na região Leste dos EUA para meu próprio teste.
git clone https://github.com/Azure-Samples/openai-enterprise-iac
cd openai-enterprise-iac
az group create -n openaitest -l eastus
``` ```markdown
az deployment group create -g openaitest -f .\infra\main.bicep
Entrar em modo de tela cheia
Sair do modo de tela cheia
Uma vez que eu execute o comando acima, vejo que a implantação começou.
Aguarde até que a implantação seja concluída.
Teste
Vamos ver se a implantação foi bem-sucedida.
Azure Open AI
``` Aqui está a tradução do texto solicitado:

---

"Vamos tentar o acesso público primeiro.  
Eu consegui criar uma implantação sem problemas. Mas quando tento a partir do playground do Chat no meu Portal Azure, vejo o seguinte erro.  
E quanto ao acesso via Web API?  
De uma ferramenta avançada do App Service, eu faço login na sessão Bash e primeiro faço um ping na URL do serviço."

--- Aqui está a tradução do texto solicitado:

```markdown
"Eu vejo que o endereço IP privado atribuído ao Endpoint Privado foi retornado.
Então, eu uso o comando curl para enviar uma solicitação para o endpoint.
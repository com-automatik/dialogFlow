<p align="center">
	<img src="https://upload.wikimedia.org/wikipedia/en/thumb/c/c7/Dialogflow_logo.svg/694px-Dialogflow_logo.svg.png?20171011172202" />	
	</p>
Os chatbots são uma parte essencial de todas as plataformas de atendimento ao cliente. 
</p>
Se você tiver muitas conversas acontecendo em sua conta, dimensionar o suporte humano pode não ser eficaz. 
</p>
Você pode implantar um chatbot que ajude a responder a perguntas triviais e entregá-lo a um agente somente quando necessário.
</p>
Dialogflow e Rasa.ai são as plataformas NLP mais bem avaliadas que permitem que você crie um bot com base no seu caso de uso. 
</p>
Neste artigo, veremos como você pode configurar um chatbot Dialogflow com Chatwoot.
</p>

</p>
<hr />
<p align="left">
	<img src="https://telegram.org/favicon.ico" alt="Telegram-logo" width="32" />
	<span>Grupo Telegram: </span>
	<a href="https://telinkei.com/gp-dialogflowbr-tg" target="_blank">Grupo</a>
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP: </span>
	<a href="https://telinkei.com/gp-dialogflowbr-" target="_blank">Grupo</a>
</p>
----------------------------------------------------------------------------
</p>

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="DialogFlow" width="200" />

</p>
----------------------------------------------------------------------------
</p>


**Configurando a integração do Dialogflow no Chatwoot**

Criar um novo Agente
</p>
Acesse o Console do Dialogflow.
</p>
https://dialogflow.cloud.google.com
</p>
Usaremos o Dialogflow Essentials para este artigo. Clique em "Criar novo agente". Ele mostraria opções como mostrado abaixo.
</p>

<img src="https://www.chatwoot.com/docs/assets/images/create-new-agent-51f6b6bc6e6da84e81c18c0bbc06986a.png" alt="DialogFlow" width="1000" />

Criar Interações

Você precisará criar intenções com base em como deseja que seu bot responda. Haverá 2 intenções padrão no projeto chamadas "Default Fallback Intent" e "Default Welcome Intent", conforme mostrado abaixo

<img src="https://www.chatwoot.com/docs/assets/images/default-intents-1159dded08111f981981ea9513cff68f.png" alt="DialogFlow" width="1000" />

Agora que a configuração básica do bot está concluída, vamos criar uma conta de serviço e conectá-la ao Chatwoot.

Você também pode criar intenções adicionais para seus casos de uso específicos.
O Chatwoot também oferece suporte a intenções avançadas que permitem transferência de agente , mensagens interativas , etc.
consulte: Intenções avançadas

Criar uma CONTA

Para conectar este bot ao Chatwoot, você precisa criar uma conta de serviço em seu console do Google Cloud. Navegue até o console do projeto na nuvem do Google clicando no ID do projeto nas configurações do projeto abaixo.

<img src="https://www.chatwoot.com/docs/assets/images/project-settings-7e5fb3d738a18ead8c0298b7af2b8276.png" alt="DialoFlow" width="1000" />

Navegue até IAM e administrador -> Contas de serviço . Você verá uma visualização como a abaixo. Clique em "Criar conta de serviço".

<img src="https://www.chatwoot.com/docs/assets/images/service-account-console-418be807b0449cb5e3a1ba539a106407.png" alt="DialoFlow" width="1000" />

Forneça um nome de conta de serviço e uma descrição conforme mostrado abaixo.

<img src="https://www.chatwoot.com/docs/assets/images/service-account-details-4ab284d92f85ffca4f9f18702dcfc5b7.png" alt="DialoFlow" width="1000" />

Para fornecer acesso, selecione Dialogflow API Client no menu suspenso.

<img src="https://www.chatwoot.com/docs/assets/images/service-access-88029531f5f8437b409ed22d1e7cab8f.png" alt=""DialoFlow" width="1000" />

Continue e clique em "Concluído". Agora, você poderá ver o serviço listado no painel. O próximo passo é criar uma chave para que ela possa ser compartilhada com o Chatwoot. Clique na conta de serviço e clique na guia "Chaves". Em seguida, clique em "Adicionar chave". Você será capaz de ver uma tela como a abaixo.

<img src="https://www.chatwoot.com/docs/assets/images/add-keys-885720919305b703fa3979807b445c7a.png" alt="DialoFlow" width="1000" />

Clique em "JSON" e clique em "Criar". Ele geraria uma chave para sua conta de serviço, baixaria a chave e a salvaria para uso posterior.

</p>
O Chatwoot possui uma integração nativa do Dialogflow. 
</p>
Vá para "Configurações -> Aplicativos -> Dialogflow". 
</p>
Clique em "Configurar", você verá um botão para "Adicionar um novo gancho".
</p>
Você precisa adicionar "ID do projeto", "Arquivo de chave do projeto" e uma caixa de entrada para criar um gancho. 
</p>
(Copie o conteúdo do arquivo de chave baixado anteriormente e cole-o na área de texto)
</p>
<img src="https://www.chatwoot.com/docs/assets/images/add-to-chatwoot-463fe037a8269b447e13e5f9c3d4c891.png" alt="Quepasa-logo" width="1000" />[

</p>
Voilá! A integração está completa.
</p>
Teste a caixa de entrada do site para ver se a consulta inicial é tratada pelo bot ou não



Interações Avançadas

Criando uma 
Depois que o usuário solicita falar com o agente, o Dialogflow precisa informar ao Chatwoot que um agente agora pode assumir a conversa.

Crie uma intenção chamada "Intenção de transferência" com frases de treinamento como "Fale com um agente" ou "Fale com um agente" etc. Para lidar com a intenção de transferência, criaremos uma resposta "Carga útil personalizada" conforme mostrado abaixo.


{
  "action": "handoff"
}

<img src="https://www.chatwoot.com/docs/assets/images/handoff-intent-c24d32864b162046bd0ec929b0cc1be1.png" alt="Quepasa-logo" width="1000" />[

Ao acionar uma intenção com a carga útil acima, o Chatwoot alternará o status da conversa para opene a entregará a um agente.

Mensagens interativas


Nota: As mensagens interativas são suportadas apenas no canal do site no momento

A integração do chatwoot dialogflow também suporta mensagens interativas . Os seguintes tipos de mensagens interativas são suportados:

Opções : acompanhamento suportado
cartões
Artigos
Criando uma mensagem interativa 
Você pode criar outras mensagens interativas alterando a carga conforme mencionado na documentação de mensagens interativas.

Crie uma intenção com as frases de treinamento necessárias e uma resposta "Custom Payload" conforme mostrado abaixo para uma mensagem de opções.


Quando o usuário interage com as mensagens de entrada. O valor selecionado é enviado de volta ao dialogflow, para que você configure uma intenção de acompanhamento, se necessário.
Exemplo : configurar um intent com a frase de treinamento "Gosto de biryani" para os casos em que o contato selecionar a opção "biryani".


Como um agente pode transferir a conversa de volta para o bot Dialoflow 
Quando o bot Dialoflow está conectado a uma caixa de entrada, as conversas são criadas com pendingstatus em vez de open. Isso permite que a triagem inicial aconteça por meio do bot antes que a conversa seja passada para um agente. Quando handoffisso acontece, o status da conversa é alterado opene o bot para de responder a ela.

Às vezes, os agentes gostariam de adiar uma conversa que foi transferida de volta para a fila do bot. Eles podem fazer isso alterando o status da conversa novamente pendingpara que o bot comece a responder a essa conversa novamente.

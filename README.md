Durante minha pesquisa, descobri um dia zero de alta gravidade na versão Red Hat do Quarkus — uma estrutura Java popular, full-stack, nativa do Kubernetes, otimizada para máquinas virtuais Java (JVMs) e compilação nativa que é usada como uma plataforma para ambientes sem servidor, nuvem e Kubernetes . 

Eu esperava que fosse anunciado a tempo para a palestra, mas era uma semana tarde demais. Dado que a Red Hat publicou detalhes da vulnerabilidade - CVE-2022-4116 - na segunda-feira, 21 de novembro, agora posso compartilhar detalhes da vulnerabilidade, que é perigosa. 

Neste ponto, a vulnerabilidade foi classificada como 9,8 no CVSS v3 Base Score. A vulnerabilidade é encontrada no Dev UI Config Editor, que é vulnerável a ataques drive-by localhost que podem levar à execução remota de código (RCE) . Explorar a vulnerabilidade não é difícil e pode ser feito por um ator mal-intencionado sem nenhum privilégio. 

De acordo com as descobertas preliminares da Red Hat, a vulnerabilidade afeta o pacote quarkus_dev_ui. Para ser claro, o CVE-2022-4116 não afeta os serviços executados na produção; isso afeta apenas os desenvolvedores que criam serviços usando o Quarkus. Se um desenvolvedor que executa o Quarkus localmente visita um site com JavaScript malicioso, esse JavaScript pode executar silenciosamente o código na máquina do desenvolvedor. 

A carga útil que criei — veja aqui no GitHub — apenas abre a calculadora do sistema. No entanto, existe a possibilidade de o código silencioso realizar ações mais prejudiciais, como instalar um keylogger na máquina local para capturar informações de login para sistemas de produção ou usar tokens do GitHub para modificar o código-fonte. 

# Mars

Mars é uma interface de assistente de voz baseada em web, projetada para automação de comandos em salas de aula e laboratórios de idiomas. O projeto combina animações visuais interativas, processamento contínuo de fala e integração de áudio externo para oferecer uma experiência de controle fluida e de baixa latência em dispositivos móveis e desktops.

## Funcionalidades Principais

* **Reconhecimento de Voz Contínuo**: Implementação baseada na Web Speech API configurada para capturar e analisar áudio em tempo real, permitindo interações dinâmicas através de palavras-gatilho.
* **Ciclo de Vida de Áudio Seguro**: Sistema avançado de gerenciamento de hardware que evita loops de auto-escuta ao isolar temporariamente a captura do microfone durante a reprodução de mídias.
* **Expressividade Visual Dinâmica**: Interface visual responsiva que reage aos estados do sistema (espera, escuta, processamento e feedback) com simulação de monitor CRT e efeito phosphor integrados via CSS e Tailwind.
* **Dicionário de Comandos**: Mapeamento extensível de palavras-chave para redirecionamento automatizado de ferramentas pedagógicas essenciais, como Whiteboard e quadros de registro.

## Requisitos de Ambiente

Para o funcionamento correto dos recursos de reconhecimento de voz e gerenciamento de áudio assíncrono, o navegador exige um contexto seguro de execução:

* **Produção**: O deploy deve ser realizado obrigatoriamente sob o protocolo HTTPS (como o ambiente nativo do GitHub Pages).
* **Desenvolvimento**: Execução local via localhost ou protocolos de desenvolvimento seguro.

## Estrutura Técnica

O projeto é construído em arquivo único estruturado para performance e portabilidade:

* **Interface e Estilização**: Tailwind CSS para estruturação responsiva e Lucide Icons para componentes vetoriais.
* **Motor de Sincronia (Mecânica de Reinicialização)**: Uso do manipulador de eventos `onended` em objetos de áudio para acionar a destruição e recriação limpa da instância do `SpeechRecognition`. Esse método contorna as restrições rígidas de privacidade e economia de energia de navegadores móveis (iOS e Android), reestabelecendo a ponte de captura sem a necessidade de novos pop-ups de permissão.

## Configuração e Instalação

1. Clone o repositório em sua máquina local.
2. Certifique-se de que o arquivo principal esteja nomeado como `index.html` para o reconhecimento automático do servidor de hospedagem.
3. Configure as constantes de áudio no script inserindo os links definitivos dos arquivos hospedados em seu serviço de nuvem (ex: Cloudinary).

Como Usar
Abra a aplicação através do link gerado pelo GitHub Pages.

Clique no botão de inicialização para conceder a permissão inicial de hardware.

Após a saudação vocal do Mars, o sistema entrará automaticamente em modo de escuta ativa.

Diga a palavra-gatilho seguida pelo comando desejado registrado no dicionário de produção.

Licença e Direitos Autorais
Todos os direitos reservados.

Este software e todos os arquivos associados são de propriedade exclusiva e privada de sua autora. É estritamente proibida a cópia, modificação, distribuição, reprodução, publicação, engenharia reversa ou uso comercial não autorizado de qualquer parte deste código-fonte sem a permissão expressa, formal e por escrito da proprietária dos direitos autorais.

# Gerenciador de Partidas de Volei

## Objetivos
A máquina tem como primeira função solicitar e registrar o e-mail do usuário; como segunda função, permitir e identificar a seleção do tipo de conta (Instituição, Técnico ou Jogador); em seguida, exibir os campos de formulário para inserção dos dados solicitados; processar o clique no botão salvar; e, por fim, aguardar e processar a confirmação do cadastro realizada pelo usuário; para a inscrição em campeonatos, a máquina tem como primeira função dar acesso e carregar a área de campeonatos; como segunda função, registrar a seleção do campeonato desejado pelo jogador; e em seguida, processar a ação do usuário de clicar em "Inscrever-se"; já no cadastro de equipes, a máquina tem como primeira função conceder acesso à área de equipes; como segunda função, disponibilizar a opção "Cadastrar Equipe"; em seguida, carregar o formulário para preenchimento dos dados gerais da equipe; permitir a inscrição dos jogadores integrantes; e, por fim, receber o comando de salvar para validar as informações, registrar a equipe na base de dados e emitir a confirmação.
- Para o cadastro e acesso ao sistema, cada usuário deve registrar um e-mail válido e selecionar obrigatoriamente um perfil de acesso — Instituição, Técnico ou Jogador —, dependendo das suas permissões; a validação e o envio de e-mail de confirmação são obrigatórios para a ativação da conta.  
Para a gestão de eventos e campeonatos, apenas contas do tipo Instituição podem criar eventos e realizar o sorteio de equipes; a inscrição em um campeonato requer que o evento/campeonato esteja com status de inscrições abertas, e que os dados cadastrais do jogador ou da equipe estejam completos e válidos antes de confirmar a participação.  
Para a gestão de equipes e jogadores, somente contas do tipo Técnico têm permissão para criar e cadastrar equipes, vincular jogadores e definir as posições táticas dos atletas em quadra; cada jogador deve estar ativo no sistema e só pode figurar em uma única equipe por campeonato simultaneamente.  
Por fim, no gerenciamento e execução das partidas, o sistema deve exigir a validação prévia da súmula e das posições iniciais escaladas pelo técnico antes do apito inicial, garantindo a integridade dos dados registrados, a pontuação em tempo real e a validação automática do resultado e das estatísticas do confronto na base de dados.

### Stack Tecnlógico
- Backend: PHP estruturado com sessões nativas
- Banco de dados: MySQL (PDO para segurança)
- Frontend: HTML5, PHP, CSS, Tailwind CSS

#### Regras de negócio (CORE)
Tratar senhas de usuários com hash bcript
O sistema deve ter uma página de históricos e manter sempre os logs de qualquer alteração feita por 
qualquer usuário, para auditorias futuras.
-Permite realizar o cadastro de um usuário no sistema
Ação do ator: Digitar o e-mail
Ação do ator: Selecionar o tipo de conta
  Ação do ator: Inserir os dados solicitados
  Ação do ator: Clicar em salvar
  Resposta do sistema: Validar os dados
Resposta do sistema: Salva os dados na base de dado
  Resposta do sistema: Enviar um email de confirmação
  Ação do ator: Confirmar o cadastro
-Permite ao jogador se inscrever em campeonatos disponíveis
  Ação do ator: Acessar a área de campeonatos
Ação do ator: Selecionar o campeonato desejado
  Resposta do sistema: exibir ações do campeonato
  Ação do ator: Clicar em “Inscrever-se”
   Resposta do sistema: Verificar dados do jogador
   -Permite ao técnico cadastrar equipes no sistema
   Ação do ator: Acessar a área de equipes
   Ação do ator: Selecionar a opção “Cadastrar Equipe”
   Resposta do sistema: Exibir o formulário de cadastro
  Ação do ator: Inserir os dados da equipe
   Ação do ator: Inserir os jogadores da equipe
   Ação do ator: Clicar em salvar
  Resposta do sistema: Validar os dados informados
   Resposta do sistema: Salvar a equipe na base de dado
   Resposta do sistema: Exibir a confirmação do cadastro
 


##### Regras Globais
- Use sempre PDO para conexão e queries no MySQL para evitar SQL Injections
- Mantenha o código limpo e comente apenas logicas complexas.
- Separe os arquivos de forma lógica: um arquivo para conexão com a base (bd.php) e scripts de backend isolados e views em HTML5/PHP, nunca faça o sistema como um monolito, deixe sempre separados todas as regras para facilitar os futuros upgrades.
 - Estilize as telas em Tailwind de forma responsiva priorizando o MobileFrist.
 - Retorne sempre as mensagens de erros de forma claras na interface para o usuário (TOAST)
 - sempre trate as mensagens de caixa de mensagens nativas do navegador em um MODAL

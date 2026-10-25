#  TV Box Server — Servidor Linux de Baixo Custo

## Sobre o projeto

Este projeto transforma uma TV Box em um servidor de baixo custo utilizando **Armbian**, uma distribuição Linux baseada em Debian/Ubuntu, para explorar conceitos de administração de sistemas, redes, armazenamento, programação e automação.

O servidor utiliza hardware reutilizado para hospedar uma página web própria de filmes e séries, permitindo organizar e reproduzir conteúdos multimídia pela rede. O acesso remoto é realizado por meio do **Tailscale**, uma VPN que conecta dispositivos de forma segura.

##  Objetivos

- Reutilizar hardware antigo e reduzir custos.
- Aprender administração de sistemas Linux.
- Hospedar uma página web para filmes e séries.
- Configurar armazenamento externo para arquivos multimídia.
- Permitir acesso remoto utilizando uma VPN.
- Desenvolver conhecimentos em redes, servidores e automação.

##  Tecnologias utilizadas

| Tecnologia | Função |
|---|---|
| Armbian | Sistema operacional do servidor |
| Debian/Linux | Base para gerenciamento de serviços |
| Python | Execução e gerenciamento do servidor web |
| HTML, CSS e JavaScript | Desenvolvimento da interface web |
| Tailscale | VPN para acesso remoto seguro |
| HD externo | Armazenamento de filmes e séries |
| Linux CLI | Administração e configuração do sistema |

## ⚙️ Sistema operacional — Armbian

O Armbian foi instalado na TV Box para transformar o dispositivo em um servidor Linux.

A configuração permite utilizar o terminal para instalar pacotes, administrar arquivos, configurar serviços e executar aplicações em segundo plano.

Principais atividades:

- Configuração inicial do sistema.
- Instalação de dependências.
- Gerenciamento de usuários e permissões.
- Configuração de rede.
- Execução de aplicações e serviços.

##  Configuração do HD externo

Um HD externo é utilizado para armazenar os arquivos de mídia, evitando ocupar o armazenamento interno limitado da TV Box.

O armazenamento pode ser organizado da seguinte forma:

```text
/mnt/hd/
├── filmes/
│   ├── filme1.mp4
│   └── filme2.mkv
└── series/
    ├── serie1/
    │   ├── temporada1/
    │   └── temporada2/
    └── serie2/
```

A configuração envolve a montagem do dispositivo, a definição das permissões de acesso e, quando necessário, a montagem automática durante a inicialização do sistema.

## Página web de filmes e séries

Foi desenvolvida uma página web própria para organizar e reproduzir filmes e séries armazenados no HD externo.

A interface utiliza tecnologias web para apresentar os conteúdos de forma organizada e permitir que o usuário selecione o vídeo desejado.

Funcionalidades do projeto:

- Interface personalizada para navegação.
- Organização dos filmes e séries.
- Reprodução de vídeos pelo navegador.
- Integração com os arquivos armazenados no HD externo.
- Acesso pela rede local.

A aplicação web é hospedada diretamente na TV Box, eliminando a necessidade de manter um computador convencional ligado para disponibilizar o serviço.

##  Acesso remoto com Tailscale

O Tailscale foi configurado para permitir a comunicação segura entre dispositivos conectados à mesma rede privada virtual.

Com ele, é possível acessar o servidor mesmo fora da rede local, sem precisar expor diretamente o serviço à internet por meio de redirecionamento de portas no roteador.

O acesso depende de:

- Tailscale instalado e autenticado no servidor.
- Tailscale instalado no dispositivo cliente.
- Permissões de acesso configuradas corretamente.
- Serviço web funcionando e acessível pela rede privada.

**Importante:** o Tailscale fornece conectividade entre os dispositivos, mas não hospeda os vídeos nem substitui o servidor web.

##  Arquitetura do projeto

```text
         Celular / Computador
                  |
             Tailscale VPN
                  |
                  v
           TV Box com Armbian
                  |
          Servidor Python / Web
                  |
          Página de filmes e séries
                  |
                  v
              HD externo
          Filmes e episódios
```

##  Como utilizar

1. Instale e configure o Armbian na TV Box.
2. Conecte e configure o HD externo.
3. Instale as dependências necessárias para executar a aplicação web.
4. Configure o caminho dos arquivos de mídia.
5. Inicie o servidor web.
6. Instale e autentique o Tailscale na TV Box.
7. Conecte o dispositivo cliente à mesma rede Tailscale.
8. Acesse a página pelo endereço IP ou nome de dispositivo disponibilizado na rede privada.

##  Conhecimentos desenvolvidos

Este projeto permite praticar conceitos de:

- Administração de sistemas Linux.
- Redes de computadores e VPN.
- Hospedagem de aplicações web.
- Programação com Python, HTML, CSS e JavaScript.
- Gerenciamento de armazenamento externo.
- Permissões e sistemas de arquivos.
- Automação e execução de serviços.
- Reutilização de hardware e computação de baixo custo.

##  Melhorias futuras

- Inicialização automática do servidor com systemd.
- Interface responsiva para celulares e computadores.
- Catálogo automático de filmes e episódios.
- Sistema de busca e categorias.
- Continuação da reprodução de vídeos.
- Monitoramento de CPU, memória e armazenamento.
- Backup de configurações e arquivos importantes.

##  Conclusão

O TV Box Server demonstra como um dispositivo de baixo custo pode ser reutilizado como uma infraestrutura funcional para serviços pessoais.

A integração entre Armbian, armazenamento externo, desenvolvimento web e Tailscale transforma a TV Box em uma plataforma de aprendizado prático, combinando programação, redes e administração de sistemas em um único projeto.

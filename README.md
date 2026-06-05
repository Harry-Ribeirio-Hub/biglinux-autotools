# BIGLINUX-AUTOTOOLS

Conjunto de scripts em Shell (Bash) desenvolvidos para automatizar o pós-instalação e a manutenção periódica do sistema operacional BigLinux.

---

## 📋 Sobre o Projeto

O **biglinux-autotools** nasceu da necessidade de evitar tarefas repetitivas ao configurar o sistema após uma formatação e ao realizar a manutenção do dia a dia. Com este projeto, você centraliza a instalação de programas essenciais e a limpeza profunda do sistema com apenas um comando no terminal.

O repositório é composto por dois scripts principais:

* **`setup.sh`**: Focado no pós-instalação. Ele baixa seus aplicativos favoritos (incluindo o OBS Studio e plugins, navegadores e utilitários), configura automaticamente um ambiente virtual seguro para bibliotecas Python, ajusta configurações regionais do ZapZap para PT-BR e reinicia o computador.
* **`atualizar_sistema.sh`**: Focado na manutenção frequente. Ele sincroniza os repositórios oficiais, atualiza pacotes do AUR/Flatpak e elimina arquivos e caches inúteis.

---

## 🛠️ Explicação Técnica Simplificada

Os scripts foram otimizados de Python para **Shell Script puro**, garantindo execução instantânea e integração nativa com o sistema operacional.

* **Gerenciamento Híbrido de Pacotes**: O script utiliza o `pamac` (gerenciador nativo do BigLinux) por ser capaz de lidar tanto com os repositórios oficiais da base Arch quanto com o **AUR** (Arch User Repository) de forma automatizada e em lote.
* **Isolamento de Privilégios**: O script de atualização roda como usuário comum e só eleva permissões (`sudo`) internamente para tarefas que realmente exigem privilégios administrativos (como limpar logs do sistema com `journalctl` ou remover pacotes órfãos com `pacman -Rns`). Isso impede que o gerenciador do AUR seja bloqueado por segurança.
* **Tratamento de Strings e Arquivos**: O script localiza e modifica arquivos de configuração `.desktop` do sistema (utilizando ferramentas nativas como `sed`) e aplica overrides de ambiente para forçar o idioma `LANG=pt_BR.UTF-8`, garantindo correções de interface de forma transparente.

---

## 🚀 Como Baixar e Executar

Abra o seu terminal e siga os passos abaixo:

### 1. Clonar o repositório e acessar a pasta
```bash
git clone [https://github.com/Harry-Ribeirio-Hub/biglinux-autotools.git](https://github.com/Harry-Ribeirio-Hub/biglinux-autotools.git)
cd biglinux-autotools

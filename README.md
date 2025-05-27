# Window-Server-DHCP
# Instalação e Configuração do Servidor DHCP - Windows Server 2008

Este repositório contém um guia técnico detalhado para instalar e configurar o serviço DHCP no Windows Server 2008. Ideal para ambientes que precisam distribuir endereços IP automaticamente na rede local.

---

## Requisitos

### Permissões
- Conta com privilégios de administrador local.

### Sistema
- Windows Server 2008 já instalado e configurado.
- Servidor com endereço IP fixo (estático).

---

## Etapas de Instalação do DHCP

### 1. Acessar o Gerenciador do Servidor

1. Faça login como Administrador.
2. Acesse:  
   Iniciar > Ferramentas Administrativas > Gerenciador do Servidor.

---

### 2. Adicionar a Função DHCP

1. No painel esquerdo, clique em "Funções".
2. No painel direito, clique em "Adicionar Funções".
3. No assistente que aparece, clique em "Avançar".
4. Marque a opção "Servidor DHCP".
5. Clique em "Avançar" para continuar.

---

### 3. Configuração de Rede

1. Selecione a interface de rede com IP fixo.
2. Clique em "Avançar".

---

### 4. Definir Escopo DHCP

Você pode configurar o escopo agora ou posteriormente. Para configurar agora:

1. Clique em "Adicionar".
2. Preencha os seguintes campos:
   - Nome do Escopo: `EscopoPadrao` (ou outro nome descritivo)
   - Intervalo de IPs: exemplo `192.168.1.100` a `192.168.1.200`
   - Máscara de sub-rede: será sugerida automaticamente
   - Gateway (opcional): exemplo `192.168.1.1`
   - Servidores DNS (opcional): IP(s) dos servidores DNS
   - Duração do lease: padrão é 8 dias, ajuste conforme necessário
3. Clique em "OK", depois em "Avançar".

---

### 5. Configurar DNS (opcional)

- Informe o nome do domínio e os IPs dos servidores DNS, se necessário.
- Clique em "Avançar".

---

### 6. Autorizar o Servidor DHCP

1. Se o servidor for membro de um domínio Active Directory, a autorização ocorrerá automaticamente.
2. Caso contrário, será necessário autorizar manualmente pelo console DHCP.

---

### 7. Concluir a Instalação

1. Revise o resumo das configurações.
2. Clique em "Instalar".
3. Ao final da instalação, clique em "Fechar".

---

## Gerenciando o Servidor DHCP

### Acessar o console DHCP:

- Iniciar > Ferramentas Administrativas > DHCP

### Tarefas comuns:

- Criar ou excluir escopos
- Reservar endereços IP para dispositivos específicos
- Monitorar clientes DHCP ativos
- Adicionar opções como WINS, TFTP, PXE, entre outras

---

## Testando o DHCP

1. Em uma máquina cliente, configure a interface de rede para obter IP automaticamente.
2. Execute no Prompt de Comando:

<<<<<<< HEAD
# 🚀 Portfólio Microsoft Azure - AZ-900

## 👋 Sobre Mim
Estudante de Cloud Computing | Microsoft Azure | Concluí a Formação AZ-900 na DIO

## 📊 Meus Projetos Azure

### 🔧 1. [Configuração e dimensionamento de VMs no Azure](https://github.com/Dani-dba/Configurando-recursos-e-dimensionamento-em-VMs-na-azure)
Dimensionamento e estratégias de escalabilidade de Máquinas Virtuais

### 💾 2. [Serviços de Armazenamento e migração de dados no Azure](https://github.com/seu-usuario/Servicos-de-armazenamento-e-migracao-de-dados-no-azure) 
Estratégias de storage, redundância e migração de dados

### 🔐 3. [Identidade acesso e Segurança Azure](https://github.com/Dani-dba/Identidade-Acesso-e-Seguranca-no-Microsoft-Azure)
Microsoft Entra ID, RBAC, MFA e Zero Trust

### 💰 4. [Gerenciamento de Custos e Governança no microsoft Azure](https://github.com/Dani-dba/Gerenciamento-de-Custos-e-Governanca-no-Microsoft-Azure)
Otimização, tags e Azure Cost Management

### 📝 5. [Ferramentas de Gerenciamento e implantação Azure](https://github.com/Dani-dba/Ferramentas-de-Gerenciamento-e-Implantacao-Azure)
Azure CLI, PowerShell, ARM Templates e Azure Arc

## 🛠️ Tecnologias Dominadas
- **Azure Services**: VMs, Storage, Networking, Security
- **Ferramentas**: Azure CLI, PowerShell, ARM Templates
- **Conceitos**: IaaS/PaaS/SaaS, High Availability, Scalability
- **Segurança**: RBAC, MFA, Zero Trust, Azure Policy
- **Governança**: Cost Management, Tags, Compliance

## 📈 Estatísticas do GitHub
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=seu-usuario&show_icons=true&theme=radical)

## 🎓 Certificação
- **AZ-900**: Em preparação (Formação concluída na DIO)

## 🔗 Links Importantes
- [📝 Meu LinkedIn](https://www.linkedin.com/in/danielle-goes/)
- [🎓 Perfil DIO](https://dio.me/users/daniellegoessoares)
- [📚 Microsoft Learn](https://learn.microsoft.com/pt-br/users/me/)

---

⭐ **Dica**: Explore cada projeto clicando nos links acima!
=======
# 🚀 Resumo do Lab:  Configurando recursos e dimensionamento em VM's na azure

## 📋 Visão Geral do Projeto

Este projeto explora os conceitos fundamentais de configuração e dimensionamento de Máquinas Virtuais (VMs) no Microsoft Azure, abordando desde a seleção de recursos até estratégias de escalabilidade.

## 🎯 O que Aprendi

### **1. Fundamentos de Computação no Azure**
- **Tipos de Computação**: Compreensão do espectro completo, de IaaS (VMs) a PaaS (App Services, Functions) e Serverless
- **Modelos de Serviço**: Diferenças entre VMs, Contêineres, App Services e Azure Functions
- **Cenários de Aplicação**: Como escolher o serviço correto para cada necessidade de negócio

### **2. Tipos de VMs e Seleção de Recursos**
- **Séries de VMs**: Diferenças entre séries (B, D, F, NC, etc.) e seus casos de uso específicos
- **vCPUs e Memória**: Como dimensionar recursos conforme workload e orçamento
- **Armazenamento**: Discos SSD Premium, Standard HDD e SSD Standard - escolhas de performance vs. custo
- **GPU**: Identificação de cenários que exigem unidades de processamento gráfico

### **3. Estratégias de Escalabilidade e Alta Disponibilidade**
```azurecli
# Criando um Conjunto de Dimensionamento de VMs
az vmss create \
  --resource-group myResourceGroup \
  --name myScaleSet \
  --image UbuntuLTS \
  --upgrade-policy-mode automatic \
  --instance-count 2 \
  --admin-username azureuser \
  --generate-ssh-keys\
```

- **Scale Sets**: Dimensionamento automático baseado em métricas de performance

- **Conjuntos de Disponibilidade**: Garantia de uptime através de domínios de falha e atualização

- **Balanceamento de Carga**: Distribuição inteligente de tráfego entre instâncias

### **4. Configuração de Discos e Armazenamento**
```azurecli
# Configurando disco gerenciado
az disk create \
--resource-group MyResourceGroup \
--name myDataDisk \
--size-gb 100 \
--sku Premium_LRS \
--encryption-type EncryptionAtRestWithPlatformKey
```

### **5. Serviços de Rede Azure**
- **Virtual Network (VNet)**: Comunicação segura entre recursos Azure

- **Sub-redes**: Segmentação lógica para organização e segurança

- **DNS Azure**: Resolução de nomes confiável e de alta performance

- **Gateway de VPN**: Conexão segura entre redes locais e Azure

- **ExpressRoute**: Conectividade privada dedicada com provedores

### **6. Monitoramento e Métricas**
- **Azure Monitor**: Acompanhamento contínuo de desempenho e saúde

- **Métricas Chave**: CPU, Memory, Disk I/O, Network - estabelecimento de baselines

- **Alertas**: Configuração proativa de notificações para métricas críticas

## 🛠️ Tecnologias e Serviços Utilizados 
- Microsoft Azure Portal

- Azure Virtual Machines & VM Scale Sets

- Azure CLI e PowerShell

- Azure Monitor & Application Insights

- Azure Virtual Network

- Azure DNS

- Azure Backup e Site Recovery

## 📊 Tabela de Tipos de VMs e Casos de Uso
| Série | Caso de Uso | vCPUs | Memória | Armazenamento | Ideal para |
|-------|-------------|-------|---------|---------------|------------|
| B | Cargas Burstáveis | 1-4 | 0.5-16GB | SSD/HDD | Dev/Test, Ambientes de Não-Produção |
| D | Propósito Geral | 1-64 | 4-256GB | SSD Premium | Servidores Web, Aplicações Enterprise |
| F | Computação | 1-64 | 2-128GB | SSD Premium | Processamento de Alto CPU |
| E | Otimizada Memória | 2-64 | 16-432GB | SSD Premium | Bancos de Dados, Análise em Memória |
| NC | Computação GPU | 1-24 | 6-220GB | SSD Premium | AI, Machine Learning, Renderização |


## 🔧 Configurações Práticas Implementadas
**Criação de VM com Rede Virtual**
``` bash
az vm create \
  --resource-group myRG \
  --name myVM \
  --image UbuntuLTS \
  --size Standard_D2s_v3 \
  --vnet-name myVNet \
  --subnet mySubnet \
  --admin-username azureuser \
  --generate-ssh-keys
  ```

### **Dimensionamento Vertical com Alta Disponibilidade**
```bash
# Parar a VM para redimensionar
az vm deallocate --resource-group myRG --name myVM

# Alterar para instância com mais recursos
az vm resize --resource-group myRG --name myVM --size Standard_D4s_v3

# Configurar em Conjunto de Disponibilidade
az vm availability-set create --resource-group myRG --name myAvailabilitySet
```

### 🚦 Principais Desafios e Soluções
|	Desafio						| Solução Implementada |
|-------------------------------|----------------------|
|	Custo vs Performance		|	Utilização de séries burstáveis (B) com monitoramento de créditos de CPU |
|	Alta Disponibilidade		|	Implementação de Availability Sets com domínios de falha	|
|	Escalabilidade Automática	|	Configuração de VM Scale Sets com regras de auto-scaling	|
|	Backup e Recuperação		|	Implementação de Azure Backup com políticas de retenção	|
|	Segurança de Rede			|	NSGs (Network Security Groups) e endpoints privados	|


# 📈 Melhores Práticas Aplicadas
1. **Right-Sizing**: Começar com menor instância e escalar conforme métricas reais

2. **Monitoramento Contínuo**: Alertas configurados para CPU > 80% e Disk I/O alto

3. **Disaster Recovery**: Backup automatizado e replication entre regiões

4. **Otimização de Custos**: Desligamento automático de VMs em horários não produtivos

5. **Governança**: Tagging de recursos para controle de custos e organização

# 💡 Casos de Uso Implementados
**Ambiente de Desenvolvimento**: Série B (burstable) com auto-shutdown

**Servidor Web Production**: Série D (general purpose) em Scale Set

**Banco de Dados**: Série E (memory optimized) em Availability Set

**Machine Learning**: Série NC (GPU optimized) com disco premium

# 🔗 Links Úteis e Materiais de Apoio
[Documentação Oficial Azure VMs](https://learn.microsoft.com/azure/virtual-machines/)


[Calculadora de Preços Azure](https://azure.com/e/)

[Azure CLI Documentation](https://learn.microsoft.com/cli/azure/)

[Slides do Curso - Computação e Rede](https://web.dio.me/track/formacao-microsoft-az-900-certification/course/computacao-e-rede/learning/12d956d8-af9f-446c-a17c-24b233e5fa64?autoplay=1)

[Microsoft Learn - AZ-900](https://learn.microsoft.com/pt-br/credentials/certifications/azure-fundamentals/?practice-assessment-type=certification)

# 🌐 Conectividade e Rede
- **DNS Azure**: Configurado para resolução interna e externa

- **VNet Peering**: Conectividade entre redes virtuais

- **VPN Gateway**: Conexão site-to-site com datacenter local

- **Network Security Groups**: Controle de tráfego granular

# 📝 Conclusão e Insights
O laboratório proporcionou uma experiência prática completa, desde a seleção inicial do tipo de VM até a implementação de estratégias enterprise de alta disponibilidade e disaster recovery. Aprendi que:

- O dimensionamento correto impacta diretamente performance e custos

- Estratégias de scaling devem ser baseadas em métricas reais

- A segurança deve ser implementada em todas as camadas (rede, disco, acesso)

- O monitoramento contínuo é essencial para operações cloud

# 🎯 Próximos Passos de Aprendizado
- Explorar Azure Kubernetes Service (AKS) para orquestração de contêineres

- Aprofundar em Azure Networking (Firewall, WAF, Front Door)

- Estudar para certificação AZ-104 (Azure Administrator)

- Implementar infraestrutura como código com Terraform/Bicep

- Explorar Azure Arc para gerenciamento híbrido

*Desenvolvido como parte do Bootcamp Formação Microsoft AZ-900 Certification na DIO - Maio 2024*
>>>>>>> 9db4779448be52625fb8f20271452379f2dd38ed

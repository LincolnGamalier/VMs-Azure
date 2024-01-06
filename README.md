# VMs-Azure

![image](https://github.com/LincolnGamalier/VMs-Azure/assets/155745584/c6b1c8a7-8069-4e22-89a7-82901bd32fc9)

--Criar recursos no Azure--

Um grupo de recursos do Azure é um contêiner lógico no qual os recursos do Azure são implantados e gerenciados. Você deve criar um grupo de recursos antes de  criar  uma  máquina  virtual.  Neste  exemplo,  criaremos  um  grupo  de  recursos chamado vm-grupo na região brazilsouth.A linha de comando utilizada é: 

az group create --name vm-grupo --location brazilsouth

--Criar VM-- 

az vm create \--resource-group "vm-grupo" \--name "LinuxVM" \--image "Ubuntu2204" \--admin-username "teste" \--admin-password "exemplo@123" \--location brazilsouth

-- Conectar-se a uma VM --

ssh adminfiap@xxx.xxx.xx.xx
(Comando ssh)

-- Para  retornarmos endereços  IP  públicos  e  privados  de  uma  máquina  virtual --
az vm list-ip-addresses --resource-group vm-grupo--name LinuxVM --output table

Para interromper uma máquina virtual: az vm stop --resource-group vm-grupo  --name  LinuxVM

Para iniciar uma máquina virtual:az vm start --resource-group vm-grupo --name LinuxVM

Ao excluir um grupo de recursos, você exclui todos os recursos contidos nele, tais  como  a  VM,  rede  virtual  e  disco.  O  parâmetro --no-wait  retorna  o  controle  ao prompt sem aguardar a conclusão da operação. O parâmetro --yes confirma que você deseja excluir os recursos sem um prompt adicional para fazer isso.

az group delete --name vm-grupo --no-wait –yes 

**(Comando  az group delete)**

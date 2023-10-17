<h1 align="center">Instalando um servidor Oracle Linux 8.x em uma virtual box</h1>
<p align="center"><i>Neste repositório irei documentar passo a passo como deve ser feita a instalação do servidor Oracle Linux em uma VM.</i></p>

## Instalando o que é necessário
### Virtual Box
- Caso você não tenha instalado na sua máquina será necessário baixar e instalar uma Virtual Box.
- Recomendo que instale a própria Virtual Box da Oracle.
- Link para download: https://www.oracle.com/br/virtualization/technologies/vm/downloads/virtualbox-downloads.html

### Oracle Linux
- Também será necessário uma versão do Oracle Linux para instalar na máquina virtual.
- Logo abaixo está o link do site para download, para acessá-lo será preciso criar uma conta da Oracle.
  - https://edelivery.oracle.com/osdc/faces/SoftwareDelivery
- Em seguida, selecione a versão do Linux que você quer utilizar e clique em "continue" como na imagem abaixo.
<img src="OracleLinux-website.png">

- Na próxima página selecione a plataforma/sistema operacional, para nosso caso de uso, x86 64bit servirá.
<img src="SelecionandoPlataforma.png">

- Logo depois selecione o arquivo para download.
<img src="EscolhendoArquivoLinux.png"> 

## Criando a máquina virtual (VM)
- Abra o Oracle VM VirtualBox Gerenciador
1. Clique em "Novo" ou "New", dê um nome a sua máquina, confira se o tipo é "Linux" e mantenha as configurações iniciais.
2. Na parte de "Hardware", selecione para a Memória Base "4096 MB" (4GB de RAM) e selecione apenas uma CPU.
3. Na parte "Disco Rígido Virtual / Virtual Hard Disk", não será preciso adicionar uma agora no momento, escolha "Não acrescentar um Disco Rígido Virtual" (a última opção).
4. Finalize a criação da VM.

### Adicionando armazenamento na VM
- No Oracle VM VirtualBox Gerenciador, clique na sua máquina uma vez e depois selecione "Configurações".
<img src="ConfiguracoesVM.png">

- Em seguida vá em "Armazenamento" e clique com o botão direito do mouse em "controladora: SATA", selecione a opção "Disco Rígido"
<img src="SelecionandoArmazenamento.png">

- Agora clique em "Criar" e selecione o tipo de arquivo como "VDI (VirtualBox Disk Image)"
<img src="EscolhendoTipoArmazenamento.png">

- Recomendo que você selecione está opção "Pré-alocar Tamanho Total", principalmente se você não tem muito espaço de armazenamento disponível.
<img src="Pre-alocandoTamanho.png">

- Definindo um tamanho para o disco rígido virtual, recomendo que selecione um tamanho maior que o arquivo de instalação do "Oracle Linux". Nesse caso vou selecionar 20 GB que é mais do que suficiente.]
<img src="DefinindoTamanhoArmazenamento.png">

- Agora basta finalizar o processo e adicionar o disco rígido virtual que você criou.
<img src="SelecionandoHardDisk.png">

### Instalando o Linux na VM
- De volta as configurações de sua máquina, selecione novamente "Armazenamento"
- Clique com botão esquerdo no "Disco vazio" na "Controladora: IDE", e depois clique no disco azul mais a direita da tela
- Escolha "imagem de disco", selecione o arquivo ISO do Linux que baixamos anteriormente, no meu caso é o arquivo "V1035444-01.iso".
<img src="SelecionandoISO.png">

- Selecione "OK", agora basta iniciar a máquina e começar a instalação do Linux.

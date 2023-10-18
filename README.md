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
<img src="Screenshots-linux/OracleLinux-website.png">

- Na próxima página selecione a plataforma/sistema operacional, para nosso caso de uso, x86 64bit servirá.
<img src="Screenshots-linux/SelecionandoPlataforma.png">

- Logo depois selecione o arquivo para download.
<img src="Screenshots-linux/EscolhendoArquivoLinux.png"> 

## Criando a máquina virtual (VM)
- Abra o Oracle VM VirtualBox Gerenciador
1. Clique em "Novo" ou "New", dê um nome a sua máquina, confira se o tipo é "Linux" e mantenha as configurações iniciais.
2. Na parte de "Hardware", selecione para a Memória Base "4096 MB" (4GB de RAM) e selecione apenas uma CPU.
3. Na parte "Disco Rígido Virtual / Virtual Hard Disk", não será preciso adicionar uma agora no momento, escolha "Não acrescentar um Disco Rígido Virtual" (a última opção).
4. Finalize a criação da VM.

### Adicionando armazenamento na VM
- No Oracle VM VirtualBox Gerenciador, clique na sua máquina uma vez e depois selecione "Configurações".
<img src="Screenshots-linux/ConfiguracoesVM.png">

- Em seguida vá em "Armazenamento" e clique com o botão direito do mouse em "controladora: SATA", selecione a opção "Disco Rígido"
<img src="Screenshots-linux/SelecionandoArmazenamento.png">

- Agora clique em "Criar" e selecione o tipo de arquivo como "VDI (VirtualBox Disk Image)"
<img src="Screenshots-linux/EscolhendoTipoArmazenamento.png">

- Recomendo que você selecione está opção "Pré-alocar Tamanho Total", principalmente se você não tem muito espaço de armazenamento disponível.
<img src="Screenshots-linux/Pre-alocandoTamanho.png">

- Definindo um tamanho para o disco rígido virtual, recomendo que selecione um tamanho maior que o arquivo de instalação do "Oracle Linux". Nesse caso vou selecionar 20 GB que é mais do que suficiente.
<img src="Screenshots-linux/DefinindoTamanhoArmazenamento.png">

- Agora basta finalizar o processo e adicionar o disco rígido virtual que você criou.
<img src="Screenshots-linux/SelecionandoHardDisk.png">

### Instalando o Linux na VM
- De volta as configurações de sua máquina, selecione novamente "Armazenamento"
- Clique com botão esquerdo no "Disco vazio" na "Controladora: IDE"
- Depois clique no disco azul mais a direita da tela (indicado na imagem)
- Escolha "imagem de disco", selecione o arquivo ISO do Linux que baixamos anteriormente, no meu caso é o arquivo "V1035444-01.iso".
<img src="Screenshots-linux/SelecionandoISO.png">

- Clique em "OK", agora basta iniciar a máquina e começar a instalação do Linux.

## Instalação e configuração do Linux na VM
- Agora já com a máquina virtual ligada (VM), se ocorrer tudo certo aparecerá está tela:
![InstallOL8_9](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/bc2d3392-0bb2-4ab7-9496-493bd9914f09)

- Selecione "Install Oracle Linux 8.x.x" para instalar a versão que foi baixada do Oracle Linux.

- Escolha o idioma que você quer utilizar durante a instalação
![InstallOL8_10](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/26b1120c-a176-433b-83d8-491cb78702e4)

- Selecione o Disco Rígido Virtual que foi criado em "Installation Destination" ou "Destino de instalação"
![InstallOL8_11](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/7cc6aa09-1c4e-48dc-8c70-04d675d4abcd)

- ATA VBOX HARDDISK (disco virtual criado) já está selecionado, basta clicar em "DONE" e voltar.
![InstallOL8_12](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/3aebdec0-1e51-48ad-a66c-879dd174a6e6)

- Vamos agora para "Software Selection" ou "Seleção de Software", deixe marcadas estas duas opções da imagem.
![SoftwareSeleciton](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/83142ea2-060d-46b9-8a10-9b9fcfb72f7c)

- Criando um usuário Root, em "Root Password"
![InstallOL8_16](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/2eecf499-75c9-4a3b-a0d4-87182656f5d4)

- Configurando "Network and Host Name window", no caso as configurações de rede, na imagem a conexão é a cabo e já está selecionada, faça o mesmo com sua conexão.
![configurando-network](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/44920722-23a3-46f4-9326-f51d87175b89)

- Configurando "Time Zone", selecione a sua região.
![TimeZonepng](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/b18caf2d-62a4-4a33-8725-0522581cc818)

- Na seção de "sistema" ou "system", habilite o "Kdump"
![kdump](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/9bbccecb-5164-49c8-add4-510969da338d)

- Selecione a opção de "Installation Source", e escolha "Auto-detected" como opção de instalação. Depois disso, clique no botão de verificar.
 
![InstallationSource](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/4f6837b1-6c55-4b05-97a4-30b5eecf9c42)
  
- Depois de configurar tudo, comece a instalação.
![image](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/9ee641fb-7478-442e-9560-9d89376332b1)

- Quando termianr a instalação clique em "Reboot" para reiniciar o sistema.
![image](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/214f7873-0dbe-447e-9a53-f66c8f7dc782)

- Aceite a licença para terminar a configuração
![InstallOL8_20](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/b088e9a3-0db0-4672-80b6-17505f6ccbc7)

- Termine a configuração

![InstallOL8_22](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/d2973c90-8441-461b-ba7c-4bfa32d7e87f)

### Agora basta fazer o login com seu usuário, selecionar o idioma do sistema e teclado, e seu sistema estará pronto!
![InstallOL8_23](https://github.com/CleitonOS/compass-linux-desafio1/assets/107083529/897e1c1b-30c6-48c2-af94-d894fd307536)



## Introdução aos pacotes de recursos
Antes de construir seu primeiro Add-On, você precisará criar um pacote para adicionar qualquer conteúdo personalizado no Minecraft: Bedrock Edition. Existem dois tipos de pacotes que um criador pode fazer: pacotes de recursos e de comportamento. Um **pacote de recursos** é uma estrutura de pastas que conterá todos os seus modelos personalizados, sons, texturas e qualquer conteúdo personalizado criado. pacotes de recursos são comumente usados ​​para adicionar conteúdo gerado pelo usuário ao Minecraft, a fim de aumentar a experiência do jogador.
<img src="https://docs.microsoft.com/en-us/minecraft/creator/documents/media/resourcepack/introduction-to-resource-packs.jpg">
Neste tutorial, você aprenderá o seguinte:
* Entenda como um **pacote de recursos** é criado.
* Como um **arquivo de manifesto** é criado.
* Como as texturas personalizadas são carregadas no Minecraft.
* O conceito de **Empilhamento de Pacotes** ao trabalhar com conteúdo Add-On.

## Requisitos
Recomenda-se que o seguinte seja concluído antes de iniciar este tutorial:
* <a href="getting-started">Introdução ao desenvolvimento de add-on</a>

Você também precisará do seguinte:
* Baixe o <a href="https://aka.ms/resourcepacktemplate">pacote de recursos Vanilla</a>

## Construindo o Pacote de Recursos
Para criar um novo pacote de recursos, você precisará criar uma nova pasta para conter um arquivo de manifesto que pode ser lido pelo Minecraft e o conteúdo personalizado que será carregado no jogo.
* Abra a pasta de localização do jogo com.mojang
Clique duas vezes na pasta **development_resource_packs**.
* Clique com o botão direito na janela do Explorador de Arquivos e selecione **Novo** e depois **Pasta** para criar uma nova pasta.
* Nomeie a nova pasta como **HelloWorldRP**.
* Clique duas vezes em **HelloWorldRP**!para abrir a pasta.
<img src="https://docs.microsoft.com/en-us/minecraft/creator/documents/media/resourcepack/helloworldrp.png">

## O arquivo de manifesto
Para carregar um pacote de recursos no Minecraft, um arquivo de manifesto precisará ser gerado. O arquivo de manifesto é um arquivo JSON que contém as seguintes informações;
* **Descrição:** descrição no jogo do que o pacote de recursos faz.
* **Nome:** nome no jogo do pacote de recursos.
* **UUID:** identificador universalmente único.
* **Versão:** versão do pacote de recursos.
* **Versão mínima do motor:** versão necessária do Minecraft na qual este pacote funcionará.


Como o arquivo é escrito em JSON, o Minecraft será capaz de analisar as informações do arquivo e exibi-lo na seção Add-On. Dentro do arquivo, as informações serão divididas em duas seções separadas; cabeçalho e módulos. A seção do cabeçalho conterá as informações gerais do pacote, enquanto os módulos conterão as informações dos pacotes dedicados.
* Clique com o botão direito do mouse na janela do Explorer e selecione **Novo** e, em seguida, selecione **Documento de texto**.
* Defina o nome como **manifest.json**.
 a. Você precisará alterar a extensão do arquivo de .txt para .json. Se a janela do Explorer não mostrar extensões de arquivo, você pode habilitar **Extensões** de **nome de arquivo** na guia **Exibir**.
 <img src="https://docs.microsoft.com/en-us/minecraft/creator/documents/media/resourcepack/manifest_file.png">
* Clique duas vezes em **manifest.json** para abri-lo em um Editor de Texto.
* Copie/cole o seguinte trecho de código em seu editor de texto.

```js
{
	"format_version": 2,
	"header": {
		"name": "Hello WorldRP",
		"description": "Meu primeiro add-on!",
		"uuid": "1e31540c-92d1-4103-8e90-c0b0119f982b",
		"version": [1, 0, 0],
		"min_engine_version": [1, 16, 0]
	},
	"modules": [
		{
			"type": "resources",
			"uuid": "fca72eb1-cfb5-4ee6-8b26-894f3b627ecb",
			"version": [1, 0, 0]
		}
	]
}
```
<blockquote>
<h3>Nota</h3>
<p>Para <code>format_version</code>, <code>2</code> é usado como o valor para o arquivo manifest.json. Enquanto <code>"1.16.0"</code> ou <code>[1.16.0]</code> são usados ​​em arquivos de manifesto vanilla, é recomendado usar o <code>"format_version": 2</code> mais recente para conteúdo personalizado.</p>
</blockquote>

## UUID
Identificador universalmente exclusivo, ou UUID por curtos, é um número único usado para identificar diferentes softwares. Para Minecraft, o UUID é usado para definir um pacote específico e evitar que qualquer software duplicado cause problemas. Para cabeçalho e módulos, precisará haver 2 diferentes números UUID inseridos entre as cotações. Você pode usar um gerador on-line de UUID, como o <a href="https://www.uuidgenerator.net/">UUID Generator</a>.
<img src="https://docs.microsoft.com/en-us/minecraft/creator/documents/%5CMedia%5CBehaviorPack%5CUUID.png">
* Copie e cole um UUID na seção do cabeçalho.  O UUID precisará ser colado entre aspas ("") para ser lido corretamente.
* Recarregue a página da web para gerar um novo UUID para uso na seção Módulos.
* Copie e cole o novo UUID na seção de módulos entre as aspas.
* Salve o arquivo de manifesto.

## Mudando o bloco de terra
Com o arquivo de manifesto concluído, agora você pode começar a adicionar conteúdo personalizado ao Minecraft. Vamos começar aplicando uma nova textura ao bloco de terra vanilla.
* No Explorador de Arquivos, na pasta **HelloWorldRP**, clique com o botão direito e selecione **Novo** e selecione **Pasta**.
* Renomeie a pasta para **textures**.
* Clique duas vezes na pasta de **textures*".
* Clique com o botão direito e selecione *Novo* e selecione *Pasta*.
* Renomeie a pasta para **blocks**.
* Clique duas vezes na pasta **blocks**.
<img src="https://docs.microsoft.com/en-us/minecraft/creator/documents/media/resourcepack/blocks_folder.png">

## Criando a textura
Agora que a estrutura de pastas foi criada, você pode colocar suas texturas personalizadas aqui. Um arquivo png também é fornecido para que você possa fazer o download e colocá-lo em sua pasta.
<img src="images/dirt.png">
* Abra um editor de imagens como o Paint3D, MS Paint ou Photoshop.
* Na **barra de ferramentas**, selecione **Arquivo** e, em seguida, selecione **Propriedades**.
* Defina a **largura** e a **altura** em **16 pixels** cada.

Agora você pode criar um padrão ou qualquer arte no editor. Neste exemplo, uma cor de preenchimento simples foi adicionada.

<blockquote>
<h3>Importante</h3>
<p>Embora o MS Paint seja usado para este exemplo pelo seu acesso rápido e fácil, também existem algumas desvantagens.</p>
<ul>
<li>O MS Paint não oferece suporte a canais alfa que são comumente usados ​​para efeitos de transparência no Minecraft.</li>
<li>O MS Paint não oferece suporte a tipos de arquivos .tga.</li>
</ul>
</blockquote>
* Quando terminar com sua textura, selecione *Arquivo* e, em seguida, selecione *Salvar* como *PNG*.
* Navegue até a pasta **blocks**.
* Salve o arquivo como **dirt.png**.

## Testando o pacote
Agora que o pacote tem um arquivo de manifesto e uma textura, você pode iniciar o Minecraft e testar seu novo complemento.
<blockquote>
<h3>Importante</h3>
<p><strong>Empilhamento de pacote</strong> é quando o conteúdo é carregado em cima do conteúdo vanilla, fazendo com que cada objeto que tenha o mesmo nome em ambos os pacotes seja sobrescrito pelo último pacote aplicado (em nosso exemplo, a textura Dirt é sobrescrita por nossa textura personalizada).</p>
<br />
<p>Se outro pacote que usa o arquivo dirt.png for carregado <strong>após</strong> HelloWorldBP, o Minecraft usará o último dirt.png aplicado.</p>
</blockquote>
Como a textura personalizada é chamada de dirt.png, a textura será usada em cada bloco de terra do jogo.
* Inicie o Minecraft.
* Quando o Minecraft for lançado e chegar ao menu principal, selecione **Jogar**.
* Selecione **Criar um novo mundo**.
* Em **Configurações**, role para baixo até a seção **Add-On**.
* Clique nos **pacotes de recursos** para ver todos os pacotes disponíveis.
* Em todos os pacotes, selecione **HelloWorldRP** para adicionar o pacote ao mundo.
* **Inicie** o seu mundo.
<img src="https://docs.microsoft.com/en-us/minecraft/creator/documents/media/resourcepack/addonsettings.png">

## Qual é o próximo?
Com uma textura personalizada agora parte do seu mundo Minecraft, agora é hora de olhar os pacotes de comportamento e como você pode alterar os comportamentos de entidade existentes. Na próxima seção, você aprenderá como adicionar um comportamento agressivo a uma entidade de vaca normalmente pacífica.

## Criadores
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/MokuseiDev">
        <img src="https://avatars.githubusercontent.com/u/93236936?v=4" width="100px;" alt=""/><br />
       <sub><b>Mokusei</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/GabrielAplok">
        <img src="https://avatars.githubusercontent.com/u/49401038?v=4" width="100px;" alt=""/><br />
       <sub><b>Gabriel Aplok</b></sub>
      </a>
    </td>
  </tr>
</table>

## Atenção
Este site não é afiliado da Mojang Studios ou da Microsoft de forma alguma.

# Pasta Com Senha
 Esse codigo cria pasta com Senha

# Como Usar

1- Copia o código
2- Abre o bloco de notas padrão
3- Cola o codigo
4- Edite como quiser (Ver abaixo)
5- Clique em salvar como no bloco de notas, e antes de salvar mude o tipo arquivo de "Arquivo de texto" para "Todos os Arquivos" 
6- Renomeie pro que preferir, mas no final coloque ".bat"
7- Pronto, clique no comando e vai abrir uma tela, onde você coloca a senha pra pasta surgir, e se clicar novamente ele pergunta se você quer esconder a pasta novamente.

#Codigo Completo

cls
@ECHO OFF
title PastaSegura
if EXIST "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" goto UNLOCK
if NOT EXIST PastaSegura goto MDLOCKER
:CONFIRM
echo Tem certeza que deseja bloquear a pasta(S/N)
set/p "cho=＞"
if %cho%==S goto LOCK
if %cho%==s goto LOCK
if %cho%==n goto END
if %cho%==N goto END
echo Invalid choice.
goto CONFIRM
:LOCK
ren PastaSegura "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
attrib +h +s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
echo Folder locked
goto End
:UNLOCK
echo Digite a Senha da pasta para DESBLOQUEAR
set/p "pass=＞"
if NOT %pass%== #sua-senha-aqui# goto FAIL
attrib -h -s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
ren "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" PastaSegura
echo Folder Unlocked successfully
goto End
:FAIL
echo Invalid password
goto end
:MDLOCKER
md PastaSegura
echo Locker created successfully
goto End
:End

# Pra editar
"PastaSegura" = Muda o nome da pasta pra qual você preferir
"#sua-senha-aqui#" = Você coloca a senha que preferir

Código bem basico, uma vez salvo o arquivo não pode mudar o nome nem senha!
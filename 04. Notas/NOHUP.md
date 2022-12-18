Ambos os comandos `nohup` e `&` são muito conhecidos em servidores linux, porém não são tão comuns para usarmos nos desktops.

## nohup

O `nohup` é usado para separar o comando depois dele do terminal, mas para que separar um comando do terminal? Eu não interajo com o comando pelo terminal?

Separamos o comando do terminal para que ele continue executando mesmo se o terminal fechar, podemos fazer um teste, se você está em uma máquina linux, você pode iniciar um programa, como o navegador, através de um comando, para o Firefox o comando é `firefox` e para o google chrome é `google-chrome`, assim que o navegador abrir, feche o terminal e você verá que o navegador também vai fechar.

Agora coloque o `nohup` na frente do comando, ficando com `nohup firefox` ou `nohup google-chrome`, assim que o navegador abrir, feche o terminal e você verá que o navegador não irá fechar.

O mesmo ocorre em uma conexão SSH, quando fechamos a conexão, o terminal usado também é fechado e as aplicações sendo executadas nele são finalizadas.

## &

O `&` permite que o comando seja executado em segundo plano, assim o programa não fica aberto no nosso terminal e permite com que seja possível usar o mesmo terminal para outros comandos.

Então para a nossa aplicação, é importante executar ela com o `&` assim o terminal é liberado, e para todos os efeitos, o terminal identifica que o programa terminou de executar e pode ir para o próximo comando, ou finalizar o script.

Sem o `&` no final do comando, vamos encontrar que o nosso script não finaliza enquanto a aplicação estiver em execução.
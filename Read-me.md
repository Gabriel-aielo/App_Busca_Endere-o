Este projeto consiste na criação de um App para busca de endereços, com base no arquivo JSON existente. 

Este branch consiste no dia 2 do projeto.

Ao decorrer do segundo dia de projeto foi focado na parte Back-end do projeto, integrando através de uma API (Application Programming Interface ) de CEP's. Sendo assim, quando o usuário insere um cep válido dentro da TAG input, este valor é armazenado em uma variável, e é realizada uma requisição HTTP através do próprio javaScipt. Se a requisição for retornada com sucesso, as demais divs input serão acrescentadas do valor correspondente. 

Projeto explicado de forma mais intuitiva:

 1 - Tag com evento ONBLUR, para que quando o foco no input for retirado, a função "getDadosEnderecoPorCep(this.value)" com o valor armazenado seja disparada ![image](https://user-images.githubusercontent.com/68876300/214656391-671f9fb5-e747-4ac6-9a16-5b2645273c97.png)
 
 2 - Função disparada e "this.value" se encontra armazenada no parâmetro "cep". O parametro "cep" é concatenado junto ao diretório que nos realizará a busca das informações no lado do servidor.
 
 ![image](https://user-images.githubusercontent.com/68876300/214657869-9cb63985-676e-4205-a903-79a9f04b5839.png)

3 - Requisição HTTP disparada, através do método GET 

![image](https://user-images.githubusercontent.com/68876300/214659725-bc55a8ab-4337-461a-903d-d15f310f0a30.png)

4 - Para verificação do estado da requisição, utilizaremos a "arrow function" " xmlHttp.onreadystatechange. Dentro da função vamos realizar a seleção de informações exibidas. Para caso de state == 4 e status == 200 (processo concluído e arquivo retornado com sucesso), pega-se o arquivo de texto armazenado em "jsonText" (linha 15) e vamos transforma-lo em um objeto manipulável, para realizar por fim a exibição em cada Div selecionada. Dentro desta mesma condição if teremos outra condição if, para o caso de não ser retornado um arquivo, mas sim "erro".

![image](https://user-images.githubusercontent.com/68876300/214659939-f304c2ea-dcf3-47c2-9d5b-af9b2ca16289.png)

5 - Estes trechos em questão fazem a mudança de informação exibida.

Para processo bem sucedido:

![image](https://user-images.githubusercontent.com/68876300/214664951-a947763c-0c0f-40d5-829f-92e82a4808a1.png)

Para processo inválido

![image](https://user-images.githubusercontent.com/68876300/214665242-349f6296-a683-4487-874b-7419fa6c06d3.png)





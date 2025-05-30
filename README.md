# Objetivo
Criar uma aplicação utilizando recursos comuns do Html, CSS e JavaScript, para: buscar, listar e mostrar detalhes de um filme utilizando a  **OMDb API**.

### Ambiente de desenvolvimento
- [VisualCode](https://code.visualstudio.com/)
- [Git](https://git-scm.com/downloads)

**Extensões úteis para o VisualCode**

- **EditorConfig for VS Code** 
	- Padronização de configs do editor.
- **Color Hightlight**
	-  Visualização de cores através do código hexadecimal.
- **Live Server**
	-  Visualizar o documento em tempo real.
- **Prettier**
	-  Padronização de código.

Vou deixar uma pré configuração dessas extensões.
Quando iniciar o VisualCode, ele irá sugerir a instalação das mesmas.

### OMDb API
[-> Site oficial](https://omdbapi.com)
- Link a ser utilizado na aplicação:
`http://www.omdbapi.com/?apikey=[yourkey]&`

### Sobre a aplicação
**- Interface**

[-> Site oficial e instruções e implementação](https://getbootstrap.com/docs/5.3/getting-started/introduction/)

A aplicação deve utilizar a biblioteca Bootstrap para a criação dos elementos.
No menu ao lado esquerdo do site, contém toda a documentação e exemplos de implementação dos componentes em tela.

**-CSS**
O arquivo de CSS deve ser separado do arquivo Html.

**-JavaScript**

[-> Guia W3 Schools](https://www.w3schools.com/js/default.asp)

Devem ser utilizadas funcionalidades atuais para o desenvolvimento ES6.

Para as requisições da API, deve ser utilizada a Fetch API

[-> Guia Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

Exemplo de utilização:
```js
async function SearchMovies(searchTerm) {
	// montando a estrutura da chamada.
	const req = await fetch(`http://www.omdbapi.com/?apikey=[yourkey]&s=${searchTerm}`, { method: "GET" });
	// verifica se a requisição retornou um erro
	if (!req.ok) {
		// cria um novo erro mostrando o status, por exemplo "404 Not Found"
		// para a execução do script
		throw new Error(`Response status: ${req.status}`);
	}
	// caso teha sucesso, transforma os dados em JSON
	const result = await req.json();
	// mostra no console do navegador o resultado da busca
	console.log('movies::', result);
}
```
Exemplo de resposta no console do navegador.
![response](https://img001.prntscr.com/file/img001/OhKPmpohScShyaOdz1-yqw.png)

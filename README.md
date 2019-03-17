# Vis�o Geral
Api para gerenciamento de cadastro de motoristas.

Essa aplica��o foi desenvolvida com prop�sito exclusivo de estudo. Ela utiliza .NET CORE 2.1, .NET Standard e .NET Framework 4.7 e os dados s�o armazenados em mem�ria. Ou seja, s�o vol�teis e n�o ir�o persistir ap�s o aplicativo ser parado ou reiniciado no servidor.

A arquitetura tem como base o estilo proposto pelo Domain-Driven Design tendo bastante foco no DomainModel, Entidade, Objeto de Valor e Linguagem Ub�qua.

Diversos design patterns foram utilizados em v�rios trechos dos c�digos, no entanto sem exageros. � f�cil perceber princ�pios SOLID principalmente no DomainModel e Infrastructure.

Todo o codigo em s�, preza pela simplicidade e legibilidade e se orienta por m�tricas de baixo acoplamento e complexidade ciclom�tica.

# Get Start

1. Clone o c�digo para seu computador.
2. Abra a Solution usando Visual Studio 2017+
3. No menu do Visual Studio, clique em Build / Clean Solution.
4. Defina o projeto WappaMobile.ChallengeDev.WebApi como Startup (clique sobre o projeto com o bot�o direito em seguida escolha Set as Startup Project)
5. No projeto WappaMobile.ChallengeDev.GoogleMaps, altere o valor da constant API_KEY da classe Settings informando a sua Chave de Api fornecida pelo Google.6. Execute a Solution apertando F5.

# End Points

### POST /api/motoristas
Inclus�o de motoristas no banco de dados.

Body (application/json)
```javascript
{
	nome:
	{
		primeiro:"",
		ultimo:""
	},
	carro:
	{
		marca:"",
		modelo:"",
		placa:
		{
			letras:"AAA",
			numeros:"0000"
		}
	},
	endereco:
	{
		tipo:"Rua",
		logradouro:"",
		numero:"",
		bairro:"",
		cidade:"",
		estado:"",
		uf:"",
		cep:""
	}
}
```

### PUT /api/motoristas/{id}
Atualiza��o dos dados de um motorista existente atrav�s do seu ID.

Body (application/json)
```javascripty
{
	nome:
	{
		primeiro:"",
		ultimo:""
	},
	carro:
	{
		marca:"",
		modelo:"",
		placa:
		{
			letras:"AAA",
			numeros:"0000"
		}
	},
	endereco:
	{
		tipo:"Rua",
		logradouro:"",
		numero:"",
		bairro:"",
		cidade:"",
		estado:"",
		uf:"",
		cep:"
	}
}
```

### GET /api/motoristas
Listagem de todos os motoristas cadastrados.

### GET /api/motoristas?orderby={campo}
Listagem de todos os motoristas de forma ordenada.

<table>
<tr>
<th>Parametro</th>
<th>Descri��o</th>
<th>Valores esperados</th>
</tr>

<tr>
<td>orderby</td>
<td>Define qual o campo ser� utilizado como refer�ncia para a ordena��o.</td>
<td>nome / sobrenome</td>
</tr>
</table>

### DELETE /api/motoristas/{id}
Exclus�o de um motorista atrav�s de seu ID.
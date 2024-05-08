

# AULA VETOR E MATRIZ | WESLEY SALES

O que são e para que servem: 

Vetores e Matrizes são estruturas de dados assim como listas, pilhas, árvores (conceitos que veremos pra frete). Usamos este tipo de estrutura para facilitar o gerenciamento de dados, podemos atribuir, manipular e visualizar de forma mais prática, além de otimizar o código.

Só podemos usar um vetor ou matriz para guardar dados de um mesmo tipo, ou seja, nao podemos guardar nomes e idades dentro de um vetor ou matriz. Isso é uma limitação, mas eles são úteis para resolver problemas mais simples.

Exemplo 1: Cadastro de 3 alunos - SEM vetores e matrizes

	char aluno1[50], aluno2[50], aluno3[50];
	
	printf("Digite o nome do primeiro aluno: ");
	scanf("%s", aluno1);
	printf("Digite o nome do segundo aluno: ");
	scanf("%s", aluno2);
	printf("Digite o nome do terceiro aluno: ");
	scanf("%s", aluno3);
	
	printf("%s\n", aluno1);
	printf("%s\n", aluno2);
	printf("%s\n", aluno3);

O problema foi resolvido, porém com muito trabalho desnecessário. Imagine ter que cadastrar 50 alunos ou até mais, o código teria muito mais linhas do que o necessário. Isso é o ponto negativo tanto na criação quanto manutenção do código. 
Imagine que exista uma alteração necessária e você precise realizar em todas as linhas que a variável aluno apareça...

# Por isso Deus criou as Estruturas de Dados!

 Veja aquele problema
 
	//AGORA USANDO VETOR
	char alunos[3][50];//declarando o vetor alunos que vai armazenar os dados.
	
	//Preenchendo o vetor com uso da estrutura de repetiçao FOR(para).
	for(int i=0;i<3;i++){
		printf("Digite o nome do aluno: ");
		scanf("%s", alunos[i]);
	}
	//Retornando os dados do vetor com uso do FOR.
	for(int i=0;i<3;i++){
		printf("Aluno %d: %s\n",i+1,alunos[i]);}



//A matriz, ou vetor bidimensional, armazena dois dados de mesmo tipo.*/

/*Exemplo, podemos usar uma matriz para armazenar as notas por unidade:
vou montar uma matriz com 3 unidades e cada unidade terá 3 notas, ou seja, matriz 3x3*/



int notas_unidade[3][3]; //declarei minha matriz que vai armazenar as 3 notas por unidade

/*usarei novamente a estrutura FOR para preencher a matriz
uma coisa um pouco diferente é que nessa situação vamos usar 
2 FOR, um dentro do outro.*/

for(int linha=0;linha<3;linha++){
	//printf("\nPreenchendo a unidade %d:\n",);
	
	for(int linha=0;linha<3;linha++){
	printf("\nPreenchendo a unidade %d:\n",linha+1);
	
	for(int coluna=0;coluna<3;coluna++){
		printf("\nDigite a %d° nota: ",coluna+1);
		scanf("%d",&notas_unidade[linha][coluna]);
	}
}

}


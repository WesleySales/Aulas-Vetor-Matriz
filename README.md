

# AULA VETOR E MATRIZ | WESLEY SALES

## O que são e para que servem: 

Vetores e Matrizes são estruturas usadas para facilitar o gerenciamento de dados (assim como listas, pilhas, árvores...). Podemos atribuir, visualizar e manipular de forma mais prática, além de otimizar o código. 

Só podemos usar um vetor ou matriz para guardar dados de um mesmo tipo, ou seja, nao é possível guardar nomes e idades dentro de um vetor ou matriz, visto que essas informações requerem variáveis do String e int respectivamente. Isso é uma limitação dessas estruturas, porém elas são bem úteis em diversos casos.

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

Quanto mais você digita, mais chances de cometer um erro.
Imagine que exista uma alteração necessária e você precise realizar em todas as linhas que a variável aluno apareça...
##
## Por isso Deus criou as Estruturas de Dados!

Veja a resolução daquele problema usando um vetor básico: 

	char alunos[3][50];//declarando o vetor alunos que vai armazenar os dados.
	
	//Preenchendo o vetor com uso da estrutura de repetiçao FOR(para).
	for(int i=0;i<3;i++){
		printf("Digite o nome do aluno: ");
		scanf("%s", alunos[i]);
	}
	//Retornando os dados do vetor com uso do FOR.
	for(int i=0;i<3;i++){
		printf("Aluno %d: %s\n",i+1,alunos[i]);}

O mesmo problema que antes eu precisei de 10 linhas agora foi resolvido em 6 e o melhor é que se fossem 50 alunos continuariam sendo as mesmas 6 linhas. 

### Estrutura de Dados + Estrutura de Repetição: Vetor para armazenar os dados e FOR para manipular.
##

## MATRIZ OU VETOR BIDIMENSIONAL

Como o nome sugere, matriz é apenas a relação de dois vetores na qual usamos linhas e colunas para armazenar dados.

Podemos usar como exemplo de aplicação da matriz um Boletim de Notas. 
Neste exemplo vamos usar 3 unidades e 3 notas por unidade, sendo assim, é uma Matriz[3][3]

	int notas_unidade[3][3]; //declarei minha matriz que vai armazenar as 3 notas por unidade
	
	for(int linha=0;linha<3;linha++){
	printf("\nPreenchendo a unidade %d:\n",linha+1);
	
	for(int coluna=0;coluna<3;coluna++){
		printf("\nDigite a %d° nota: ",coluna+1);
		scanf("%d",&notas_unidade[linha][coluna]);
	}
	}
	}

Nesse caso usamos dois FOR, um para indicar que estamos preenchendo a primeira linha (ou Vetor) e o segundo for para indicar a coluna que estamos trabalhando.

### Trabalhando melhor a questão anterior: 

			
	int notas_unidade[3][3]; //declarei minha matriz que vai armazenar as 3 notas por unidade
	double media[3];

	for(int linha=0;linha<3;linha++){
		double soma=0;
		printf("\nPreenchendo a unidade %d:\n",linha+1);
  
  		for(int coluna=0;coluna<3;coluna++){
				
			printf("Digite a %d° nota: ",coluna+1);
			scanf("%d",&notas_unidade[linha][coluna]);
			soma+=notas_unidade[linha][coluna];
		}
			media[linha]=soma/3;
	}
	
	for(int i=0;i<3;i++){
		printf("\nA média do aluno na %d unidade foi: %.2f", i+1,media[i]);
	}

	}

O que eu fiz agora foi realizar uma operação com base nos dados oferecidos. Fiz a média do aluno em cada uma das unidades e mostrei. Ainda podemos trabalhar muito em cima deste modelo, proponho esses desafios:
- Solicitar nome e turma do aluno no inicio do programa e apresentar junto a média no final.
- Indicar se ele foi aprovado, reprovado ou se deve fazer uma recuperação (aprovado: >=6; reprovado: <5; recuperação: >=5 && < 6.

### fique a vontade para trabalhar como preferir.
##

	#include <stdio.h>
	#include <string.h>
	#include <locale.h>
	
	int main(){
	setlocale(LC_ALL,"Portuguese");
	int notas_unidade[3][3]; 		
	double media[3];
	char nome[50],turma[50];
	
	printf("Nome: ");
	scanf("%s", nome);
	printf("Turma: ");
	scanf("%s", turma);

	for(int linha=0;linha<3;linha++){
	double soma=0;
	
	printf("\nPreenchendo a unidade %d:\n",linha+1);

		for(int coluna=0;coluna<3;coluna++){	
			printf("Digite a %d° nota: ",coluna+1);
			scanf("%d",&notas_unidade[linha][coluna]);
			soma+=notas_unidade[linha][coluna];
	}
		media[linha]=soma/3;
	}
	
	printf("\nBOLETIM ESCOLAR:\n");
	printf("_______________\n: ");
	printf("Nome: %s ", nome);
	printf("Turma: %s \n", turma);
	printf("_______________\n: ");
	

	for(int i=0;i<3;i++){
		if(media[i]>=6){
			printf("\nA média do aluno na %d unidade foi: %.2f. ----> APROVADO", i+1,media[i]);
		}
		else if(media[i]>=5 && media[i]<6){
			printf("\nA média do aluno na %d unidade foi: %.2f. ----> RECUPERAÇÃO", i+1,media[i]);
		}
		else {
			printf("\nA média do aluno na %d unidade foi: %.2f. ----> REPROVADO", i+1,media[i]);
		}
	
	}
	

	}
	
	

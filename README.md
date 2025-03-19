# Sistemas-Distribuidos-e-Programacao-Paralela-atividade1

# Membros do grupo

- Eric Menezes : https://github.com/mi1048
- Rodrigo Dias Sarno : https://github.com/RodsSarno

# Sobre o que e este repositorio:
Este repositorio e sobre a atividade de Sistemas Distribuidos e Programação Paralela onde e feito a verificação de números primos em um arquivo com o intuito de avaliar o quanto o paralelismo em threads pode ajudar na execução de algoritmos.

# Configurando o Ambiente de execução:
1. Baixe o arquivo ProjetosPrimos1.1.zip
2. Extrai o ProjetosPrimos1.1.zip em uma pasta
3. Importe os arquivos do projeto em Java
4. Baixe o [Xchart](https://knowm.org/open-source/xchart/)
5. Adicione os arquivos .jar do Xchart no seu Projeto->Buildpath->Bibliotecas->Classpath
6. Após isso o codigo deve ser executado normalmente

# Mas como fazemos isto?

Primeiro dividimos em duas classes a busca do arquivo 'entrada.txt':

1. **Sequencial**: Encontra os números primos de forma sequencial.
2. **Paralela**: Utiliza múltiplas threads para encontrar os números primos de maneira paralelizada, utilizando diferentes quantidades de threads para medir o impacto no desempenho.

# Estrutura do Programa

O programa foi dividido em quatro partes principais:

1. A primeira parte é responsável por ler e escrever arquivos, usando `BufferedReader` e `BufferedWriter` para garantir que a manipulação de arquivos seja eficiente;
2. Depois disso, a segunda parte verifica se um número é primo, utilizando um loop que vai até a raiz quadrada do número para otimizar o processo;
3. Em seguida, a terceira parte faz a busca sequencial de números primos, ou seja, sem usar threads, apenas iterando sobre a lista de números e verificando cada um;
4. Por fim, a quarta parte implementa a busca paralela, onde cada número é verificado em uma thread separada, usando `ExecutorService` e `Callable` para gerenciar as tarefas.

# Com isso,após a busca ser feita plotamos os gráficos

1. **Gráfico de Tempo Real de Execução vs. Número de Threads**: Mostra como o tempo de execução do algoritmo paralelo varia conforme o número de threads.  
   ![Grafico de Tempo por threads](https://raw.githubusercontent.com/mi1048/Sistemas-Distribuidos-e-Programacao-Paralela-atividade1/refs/heads/main/Speedupvsthreadsjava3.jpg)  
O comportamento esperado é que, à medida que o número de threads aumenta, o tempo de execução diminua devido ao paralelismo. No entanto, após um certo ponto, o ganho de desempenho diminuiu pois o sistema começa a ter dificuldades em gerenciar muitas threads.

Logo, o tempo de execução sequencial é claramente maior que o tempo paralelo, mas com 5 e 10 threads, o tempo cai significativamente. Depois disso, o ganho marginal diminui.

2. **Gráfico de Speedup vs. Número de Threads**: Mostra como o speedup varia conforme o número de threads, ajudando a visualizar a eficiência da paralelização.  
   ![Tempodeexecucao3](https://github.com/user-attachments/assets/1c35bdd8-66bb-4182-a7f6-a83d8d6d8338)  
O speedup aumenta com o número de threads, mas tende a se estabilizar após um certo ponto devido à Lei de Amdahl e à sobrecarga de gerenciamento de threads.
A Lei de Amdahl é um princípio que define o ganho máximo de desempenho que pode ser obtido ao paralelizar uma tarefa, levando em consideração a parte do código que não pode ser paralelizada.

Em outras palavras, mesmo que aumentemos o número de threads, existe um limite teórico para o speedup, pois sempre haverá uma parte do programa que precisa ser executada de forma sequencial.

O speedup máximo foi alcançado com 14 threads, onde o valor foi de 7.0x. Após esse ponto, aumentar o número de threads não traz ganhos significativos, pois a sobrecarga de gerenciamento das threads e a parte sequencial do código começam a dominar o tempo de execução. Isso significa que, embora o paralelismo ofereça melhorias significativas, ele não é escalável infinitamente.

3. **Gráfico de Comparação de desempenho**:Abaixo está um gráfico comparando o tempo de execução dos diferentes modelos:

   

   
# Dependências

- Java 8 ou superior
- Biblioteca [Xchart](https://knowm.org/open-source/xchart/) para geração de gráficos (utilizada pelo código).

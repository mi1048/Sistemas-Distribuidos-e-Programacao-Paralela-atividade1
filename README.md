# Sistemas-Distribuidos-e-Programacao-Paralela-atividade1

# Membros do grupo

- Eric Menezes : https://github.com/mi1048
- Rodrigo Dias Sarno : https://github.com/RodsSarno

# Sobre o que e este repositorio:
Este repositorio e sobre a atividade de Sistemas Distribuidos e Programação Paralela onde e feito a verificação de números primos em um arquivo com o intuito de avaliar o quanto o paralelismo em threads pode ajudar na execução de algoritmos.

# Mas como fazemos isto?

Primeiro dividimos em duas classes a busca do arquivo 'entrada.txt':

1. **Sequencial**: Encontra os números primos de forma sequencial.
2. **Paralela**: Utiliza múltiplas threads para encontrar os números primos de maneira paralelizada, utilizando diferentes quantidades de threads para medir o impacto no desempenho.

# Com isso,após a busca ser feita plotamos os graficos

1. **Gráfico de Tempo Real de Execução vs. Número de Threads**: Mostra como o tempo de execução do algoritmo paralelo varia conforme o número de threads.
2. **Gráfico de Speedup vs. Número de Threads**: Mostra como o speedup varia conforme o número de threads, ajudando a visualizar a eficiência da paralelização.

# Dependências

- Java 8 ou superior
- Biblioteca `XChart` para geração de gráficos (utilizada pelo código).

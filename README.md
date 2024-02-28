# algoritmia

    public class Main {
    private static void main(String[] a­rgs) {
        int n = 5; // Or any other value you want to test
        int[] dp = new int[n + 1];
        System.out.println(function(n, dp));
    }

    private static int function(int n, int[] dp) {
        if (n == 0) {
            return 0;
        }

        if (n == 1 || n == 2) {
            return 1;
        }

        if (dp[n] != 0) {
            return dp[n]; // Return the precomputed result if available
        }

        dp[n] = function(n - 1, dp) + function(n - 2, dp) + function(n - 3, dp);
        return dp[n];
    }
}

    a. Update the code so it uses dynamic programming
    En el codigo actualizado, antes de calcular el valor de dp[n], comprobamos si ya se ha calculado y almacenado en la matriz dp[]. Si es así, devolvemos directamente ese valor, evitando así cálculos redundantes.
    b. Identify where the overlap of the subproblems occurs
    En esta función recursiva, el overlap de subproblemas se produce porque se realizan múltiples llamadas recursivas con el mismo valor n. Por ejemplo, al calcular función(n), la función llama recursivamente a función(n-1), función(n-2) y función(n-3). Esto significa que el mismo subproblema se resuelve varias veces ahi es donde se encuentra el problema.


2. Can we say that "all the implementations that use a top-down approach are dynamic programming algorithms”?
No, aunque es cierto que muchos algoritmos de programación dinámica utilizan un enfoque top-down, no todas las implementaciones que utilizan un enfoque top-down son algoritmos de programación dinámica.
3. .Give an example of an optimization problem
A lo que entiendo un problema de optimización en algoritmia implica encontrar la mejor solución posible entre un conjunto de posibles soluciones, no se si aplicaria para lo que se esta pidiendo pero un problema simple de optimización podría ser encontrar el número más grande en una lista de números. La solución óptima sería el número más grande de la lista.


4. Fuchsia has organized a surprise party for Coco, and the guests have already arrived and placed their gifts in a row at the gift table
Fuchsia knows Coco very well, so she knows which gift she would like the most-. That is why she labels each gift with a number representing how much she would like the gift
Fuchsia decides to make the party more fun for Coco; she will rearrange the gifts so that the first gift is the one she likes the least and so on until the last gift is the one she like the most
Fuchsia wants to know the minimum amount of gifts she should move around so the gifts are arranged correctly

Input: A number N that represents the number of gifts, followed by N numbers representing how much Coco will like each gift(Constraint: There are not two gifts with the same value)

Output
The minimum amount of gifts that Fuchsia should move

Sample input 1:
4
1 12 5 31
Sample output 1:
1
Sample input 2:
5 
30 21 15 12 4
sample output 2:
4
a. Identify the problem in general terms
El problema consiste en reorganizar una fila de regalos de acuerdo a las preferencias de Coco, de tal manera que el primer regalo sea el que menos le gusta y el último sea el que más le gusta. Se desea determinar el mínimo número de regalos que deben moverse para lograr esta disposición.
b. Analyse the problem based on sub-problems and find the formula
Podemos dividir el problema en subproblemas de la siguiente manera:
    • Para cada regalo en la fila, determinar cuántos regalos hay antes de él que son menos preferidos por Coco.
    • Luego, calcular el mínimo número de regalos que deben moverse para que este regalo esté en la posición correcta.
c. Identify where the overlap of sub-problems occurs
La superposición de subproblemas ocurre cuando necesitamos calcular el mínimo número de regalos a mover para un regalo específico que ya ha sido calculado antes.
d. Implement the solution to the problem using DP top-down

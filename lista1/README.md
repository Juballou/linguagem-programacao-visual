# Lista 1

1. Faça um programa que receba um número e verifique se ele é negativo ou não negativo.

'''
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;

    namespace ConsoleApplication1
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Digite um número");
                double num = double.Parse(Console.ReadLine()); //Recebe na variavel o numero que foi digitado.
                string resultado = "O número é: ";
                resultado += num >= 0 ? " Positivo" : " Negativo"; // True e false
                Console.WriteLine(resultado);
            }
        }
    }
'''

2. Faça um programa que solicite a entrada de um número e exiba se o número é par ou ímpar.

'''
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            int nro;
            
            Console.WriteLine("Entre com um número inteiro: ");
            nro = int.Parse(Console.ReadLine());
            
            string resultado = "O número é: ";
            
            resultado += nro % 2 == 0 ? "Par" : "Ímpar";
            
            Console.WriteLine(resultado);
        }
    }
}
'''

3. Faça um programa que compara a soma de dois números se o valor for maior que 10 incrementa a soma em 5. Se o valor for menor que 10, decrementa a soma em 7.

'''
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            int nro1, nro2, soma;

            Console.WriteLine("Entre com um número inteiro: ");
            nro1 = int.Parse(Console.ReadLine());

            Console.WriteLine("Entre com um número inteiro: ");
            nro2 = int.Parse(Console.ReadLine());

            soma = nro1 + nro2;

            if (soma >= 10)
            {
                soma += 5;
            }
            else soma -= 7;
            
            Console.WriteLine("O resultado é: " + soma);

        }
    }
}
'''

4. Faça um programa que solicite ao usuário duas notas e o respectivo peso de cada uma das notas de duas provas realizadas por um aluno e calcule a média ponderada.

'''
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            double nota1, nota2, peso1, peso2, media;

            Console.WriteLine("Digite a nota do 1 bimestre: ");
            nota1 = Double.Parse(Console.ReadLine());

            Console.WriteLine("Digite o peso da nota do 1 bimestre: ");
            peso1 = Double.Parse(Console.ReadLine());

            Console.WriteLine("Digite a nota do 2 bimestre: ");
            nota2 = Double.Parse(Console.ReadLine());

            Console.WriteLine("Digite o peso da nota do 2 bimestre: ");
            peso2 = Double.Parse(Console.ReadLine());

            media = ((peso1 * nota1) + (nota2 * peso2)) / (peso1 + peso2);
            
            Console.WriteLine("O resultado é: " + media);

        }
    }
}
'''
    
5. Faça um programa que calcule a velocidade média de um veículo qualquer, leia a distância percorrida pelo veículo e o tempo gasto no percurso. O cálculo da velocidade média é distância/tempo.

'''
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            double distancia, tempo, media;

            Console.WriteLine("Digite a distância que o veículo percorreu: ");
            distancia = Double.Parse(Console.ReadLine());

            Console.WriteLine("Digite o tempo gasto durante o percurso: ");
            tempo = Double.Parse(Console.ReadLine());

            media = distancia / tempo;
            
            Console.WriteLine("O calculo da velocidade média é: " + media.ToString("F"));

        }
    }
}

'''

6. Crie um programa que calcule o salário mensal de um vendedor de uma revendedora de carros. O vendedor recebe uma comissão por cada carro vendido e mais 5% sobre o valor total das vendas.
Solicitar ao usuário o número de identificação do vendedor, seu salário fixo, a quantidade de carros vendidos, o valor da comissão por cada carro vendido e o valor total das vendas. Exibir o número de identificação e seu salário total.

'''
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            int cod, carrosvendidos;
            double salario, comissao, totalvendas, totalsalario;

            Console.WriteLine("Digite o número de identificação do vendedor: ");
            cod = int.Parse(Console.ReadLine());

            Console.WriteLine("Digite o salário fixo: ");
            salario = Double.Parse(Console.ReadLine());

            Console.WriteLine("Diigite o número de carros vendidos: ");
            carrosvendidos = int.Parse(Console.ReadLine());

            Console.WriteLine("Digite o valor da comissão para cada carro vendido: ");
            comissao = Double.Parse(Console.ReadLine());

            Console.WriteLine("Digite o valor total de vendas: ");
            totalvendas = Double.Parse(Console.ReadLine());

            totalsalario = salario + (carrosvendidos * comissao) + (totalvendas * 0.05);
            
            Console.WriteLine("Número de identificação: " + cod + ". Salário Total: " + totalsalario.ToString("C"));

        }
    }
}
'''

7. Crie um programa que tenha como finalidade calcular o reajuste salarial de um funcionário. Solicitar ao
usuário o código do funcionário e seu salário atual. Calcular o novo salário do funcionário de acordo com as condições:
    > Utilizar estrutura de seleção if/else aninhadas. 

| Índice de Aumento | Salário Atual |
| --- | --- |
| 10% | R$ 0,00 - R$ 300,00 |
| 11% | R$ 301,01 - R$ 600,00 |
| 12% | R$ 600,01 - R$ 900,00 |
| 6% | R$ 900,01 - R$ 1500,00 |
| 3% | R$ 1500,01 - R$ 2000,00 |
| Sem aumento | Acima de R$ 2000,00 |

Exibir para o usuário a seguinte mensagem: "O funcionário 123, teve um aumento de R$ 45,00,
e agora seu salário é: R$ 1545,00", caso o funcionário não tenha aumento exibir: "O funcionário 123,
não teve aumento, o salário é: R$ 2100,00".
    > Utilizar a interpolação de strings e delimitar o número de casas decimais do salário.

'''    
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            int cod;
            double salario, aumento;

            Console.WriteLine("Digite o número de identificação do funcionário: ");
            cod = int.Parse(Console.ReadLine());

            Console.WriteLine("Digite o salário atual: ");
            salario = Double.Parse(Console.ReadLine());

            if(salario >= 0 && salario <= 300){
                aumento = salario * 0.10;
                salario += aumento;
                Console.WriteLine("O funcionário " + cod + ", teve o aumento de " + aumento.ToString("C") + ", e agora seu salário é: " + salario.ToString("C"));
            }
            else if(salario >= 301.01 && salario <= 600){
                aumento = salario * 0.11;
                salario += aumento;
                Console.WriteLine("O funcionário " + cod + ", teve o aumento de " + aumento.ToString("C") + ", e agora seu salário é: " + salario.ToString("C"));
            }
            else if (salario >= 600.01 && salario <= 900)
            {
                aumento = salario * 0.12;
                salario += aumento;
                Console.WriteLine("O funcionário " + cod + ", teve o aumento de " + aumento.ToString("C") + ", e agora seu salário é: " + salario.ToString("C"));
            }
            else if (salario >= 900.01 && salario <= 1500)
            {
                aumento = salario * 0.06;
                salario += aumento;
                Console.WriteLine("O funcionário " + cod + ", teve o aumento de " + aumento.ToString("C") + ", e agora seu salário é: " + salario.ToString("C"));
            }
            else if (salario >= 1500.01 && salario <= 2000)
            {
                aumento = salario * 0.03;
                salario += aumento;
                Console.WriteLine("O funcionário " + cod + ", teve o aumento de " + aumento.ToString("C") + ", e agora seu salário é: " + salario.ToString("C"));
            }
            else
            {
                Console.WriteLine("O funcionário " + cod + ", não teve aumento, o salário é: " +  salario.ToString("C"));
            }

        }
    }
}
'''

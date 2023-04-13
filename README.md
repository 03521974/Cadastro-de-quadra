# Cadastro-de-quadra
Projeto Java básico
Este projeto visa melhorar o código proposto em java.

import jdk.swing.interop.SwingInterOpUtils;
import java.time.LocalDate;
import java.util.Scanner;
    public class Locacao {
        private Locatario locatario;
        private Quadra quadra;
        private int tempoMinuto;
        private char necessitaEquipamento;
        double valorTotal;
        public void cadastrarLocacao() {
            valorTotal = 0;
            Scanner sc = new Scanner(System.in);
            System.out.println("-------Cadastro de locacao------- ");
            quadra = new Quadra();
            quadra.cadastrarQuadra();
            System.out.println("-------Cadastro do Locatario-------");
            locatario = new Locatario();
            locatario.cadastrarLocatario();
            LocarAcessorio();
        }
        public double LocarAcessorio () {
            valorTotal = 0;
            Scanner scanner = new Scanner(System.in);
            System.out.print("Digite o tempo da locacao em minutos: ");
            tempoMinuto = scanner.nextInt();
            System.out.println("Necessita de equipamento ?");
            System.out.print("S - Sim / N - Nao: ");
            char resposta = scanner.next().charAt(0);
            valorTotal = quadra.getValorMinuto() * tempoMinuto;
            if (tempoMinuto >= 120) {
            valorTotal = valorTotal - (0.10 * valorTotal);
            }
            if (resposta == 'S') {
            valorTotal = valorTotal + 50;
            } else {
            if (resposta == 'N') ;
            }
            return valorTotal;
            }
        public void ResumoLocacao () {
                System.out.println("");
                System.out.println("-------Resumo da locacao-------");
                System.out.println("Nome" + locatario.getNome());
                System.out.println("Cpf" + locatario.getCpf());
                System.out.println("Telefone: " + locatario.getTelefone());
                System.out.println("Ano do nascimento: " + locatario.getAnoNascimento());
                System.out.println("Nome da quadra: " + quadra.getNome());
                System.out.println("Tipo de quadra: " + quadra.getTipoDaQuadra());
                System.out.println("Valor do minuto: R$" + quadra.getValorMinuto());
                System.out.println("Tempo em Minutos: " + tempoMinuto);
                System.out.println("Valor calculado em R$: " + valorTotal);
            System.out.println("");
            System.out.println("Locacao realizada com sucesso!");
            }
        }

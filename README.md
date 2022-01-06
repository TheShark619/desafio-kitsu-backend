
O projeto é uma lista de cadastro que adiciona, apaga e altera a os já cadastrados na lista
Assim como ele responde e ajuda o usuário quando ele digita errado!

 Rafael Henrique: package br.com.interview.prova;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
import br.com.relembrando.utils.Utils;

public class Prova {

	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);
		List<String> usuarios = new ArrayList<String>();

		int opcao = 0;

		while (opcao != 4) {

			Utils.tela();

			opcao = scan.nextInt();

			if (opcao <= 4 & opcao >= 1) {

				if (opcao == 1) {
					System.out.println("===> digite o nome do usuário para efetuar cadastro :");

					usuarios.add(scan.next());

				} else if (opcao == 2) {
					if (!usuarios.isEmpty()) {
						for (String usuario : usuarios) {
							System.out.println("usuário : " + usuario);
						}
						System.out.println("===> digite o nome do usuário deseja remover :");
						String nome = scan.next();
						if (usuarios.contains(nome)) {
							usuarios.remove(nome);
						} else {
							System.out.println("usuário não existe...");
						}

					} else {
						System.out.println("não há usuarios para serem removidos ");
					}
				} else if (opcao == 3) {

					if (!usuarios.isEmpty()) {
						System.out.println("==> os usuários cadastrados são : ");
						for (String usuario : usuarios) {
							System.out.println("usuário : " + usuario);

						}
					} else {
						System.out.println("==> Não existem usuários cadastrados no sistema.");

					}
				} else if (opcao == 4) {

					System.out.println("==> Encerrando sistema...");

				}
			} else {
				System.out.println("==> opção inválida... ");
				System.out.println("==> digite um numero de 1 a 4 ");
			}

		}

	}

} 
-------------------------------------------------------------------------------------------------------------------------------------
Rafael Henrique: package br.com.interview.utils;

public class Utils {
	
	public static void tela() {
		System.out.println("||=================================================||");
		System.out.println("||       {{Escolha a opção desejada :}}            ||");
		System.out.println("||=================================================||");
		System.out.println("||----> 1 – Cadastrar novo usuário                 ||");
		System.out.println("||----> 2 – Remover um usuário cadastrado          ||");
		System.out.println("||----> 3 – Consultar todos os usuários cadastrados||");
		System.out.println("||----> 4 – Sair do sistema                        ||");
		System.out.println("||=================================================||");
		
		
	}

}

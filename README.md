/*
 * Écrire un programme qui permet de jouer au jeu du "nombre mystérieux" : l’utilisateur est censé
trouver un nombre entier inconnu dont la valeur est fixée aléatoirement dans le programme (on
suppose que la valeur est comprise entre 0 et 100). L’utilisateur propose des solutions. Tant qu’il n’a
pas trouvé, le programme répond "Encore plus petit", "Encore plus grand", ou "Bravo, vous avez
trouvé le nombre". Si l’utilisateur dépasse 10 essais, le programme s’arrête et affiche "Game Over".
*/
package exercice2;

import java.util.Random;
import java.util.Scanner;

public class nombreMystérieux {

	private static Scanner r;

	public static void main(String[] args) {
		r = new Scanner(System.in);
		int n, i = 0;
		Random m = new Random();
		int mystérieux = m.nextInt(101);
		System.out.println(mystérieux);
		System.out.println("Donnez votre nombre mystérieux(0--100),vous avez maximum 10 essais:");
		n = r.nextInt();

		while (i < 10) {
			i++;
			if (n < mystérieux) {
				System.out.println("Encore plus grand");

				System.out.println("Donnez votre nombre mystérieux(0--100):");
				n = r.nextInt();

			} else {
				if (n == mystérieux) {
					System.out.println("Bravo, vous avez trouvé le nombre");
					break;
				} else {
					System.out.println("Encore plus petit");
					System.out.println("Donnez votre nombre mystérieux(0--100):");
					n = r.nextInt();

				}
			}

		}
		System.out.println("Game Over");
	}
}

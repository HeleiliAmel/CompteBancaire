# CompteBancaire
https://github.com/HeleiliAmel/CompteBancaire.git
	 echo # CompteBancaire >> README.md
	 git init
	 git add README.md
	 git commit -m "first commit"
	 git remote add origin https://github.com/HeleiliAmel/CompteBancaire.git
	 git push -u origin master
	 git remote add origin https://github.com/HeleiliAmel/CompteBancaire.git
		  
package compte;
import java.util.Scanner;
public class DAB {
public static void main (String[]args){
	Compte compte = new Compte (1,1000,0.5);
	compte.AfficherInfo();
	compte.Interet();
	int choix = 0;
	while(choix != 4){
		System.out.println("Tapez 1 si vous voulez ajouter un montant ");
		System.out.println("Tapez 2 si vous voulez retirer un montant ");
		System.out.println("Tapez 3 si vous voulez reafficher les informations ");
		Scanner clavier = new Scanner(System.in);
		System.out.print(" choix : ");
		choix = clavier.nextInt();
		switch(choix){
		case 1 :{
			System.out.println("Le montant que vous voulez ajouter au compte :");
			double montant = clavier.nextDouble();
			compte.Ajout(montant);
			System.out.println(compte.getSolde());
		}
		break;
		case 2 :{
			System.out.println("Le montant que vous voulez retirer au compte :");
			double montant = clavier.nextDouble();
			compte.Retrait(montant);
			System.out.println(compte.getSolde());
		}
		break;
		case 3 :{
			compte.AfficherInfo();
		}
		}
	}
}
}
package compte;

public class Compte {
  private int Numero_Compte;
  private double Solde;
  public double getSolde() {
	return Solde;
}
public void setSolde(double solde) {
	Solde = solde;
}
private double Taux;
  
public Compte(int Numero_Compte , double Solde , double Taux){
	this.Numero_Compte = Numero_Compte;
	this.Solde = Solde;
	this.Taux = Taux;
}
public void AfficherInfo(){
	System.out.println("Le compte " +Numero_Compte+ "\nSolde : "+Solde+ "\nSon taux d'interet est de " +Taux);
}
public void Interet (){
	double Interet;
	Interet = Solde * Taux;
}
public void Ajout(double Montant){
	Solde = Solde + Montant;
}
public void Retrait(double Montant){
	if(Solde - Montant < 0)
		System.out.println("Vous ne pouvez pas retirer ce montant");
	else 
		Solde = Solde - Montant;
}

}

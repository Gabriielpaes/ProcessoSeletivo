import java.util.Random;
import java.util.concurrent.ThreadLocalRandom;

public class ProcessoSeletivo {
    public static void main(String[] args) {    
        String[] candidatos = {"DANIELA", "MARIANA", "LUCAS", "ANA", "FELIPE"};
        selecaoCandidatos(); // Adicione esta linha
        for(String candidato : candidatos) {
            entrandoEmContato(candidato);
        }
    }
    static void entrandoEmContato(String candidato){
        int tentativasRealizadas = 1;
        boolean continuarTentando = true;
        boolean atendeu=false;
        do {
            atendeu=atender();
            continuarTentando = !atendeu;
            if(continuarTentando)
            tentativasRealizadas++;
            else
            System.out.println("CONTATO REALIZADO COM SUCESSO");


        }while(continuarTentando && tentativasRealizadas<3);

        if(atendeu)
    System.out.println("CONSEGUIMOS CONTATO COM " + candidato + "NA" + tentativasRealizadas + "TENTATIVA");
    else
    System.out.println("NÃO CONSEGUIMOS CONTATO COM " + candidato + ",NÚMERO MAXIMO TENTATIVAS" + tentativasRealizadas + "REALIZADA");
    }
    

    //método auxiliar
    static boolean atender(){
        return new Random().nextInt(3)==1;
    }
    static void imprimirSelecionados() {
        String [] candidatos = {"DANIELA","MARIANA","LUCAS","ANA","FELIPE"};

        System.out.println("Imprimindo a lista de candidatos informando o indice do elemento");
        for(int indice=0; indice < candidatos.length;indice++) {
            System.out.println("o candidato de n° " + (indice+1) + " é " + candidatos[indice]);
        }

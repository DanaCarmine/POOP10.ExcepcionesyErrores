# POOP10.ExcepcionesyErrores

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package poop10;

import java.util.Arrays;

/**
 *
 * @author Optiplex 780
 */
public class POOP10 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        
        String mensajes [] = {"Primero", "Segundo", "Tercero"};
        try{ 
             for (int i = 0; i <= 3; i++) {
                 System.out.println(mensajes[i]);   
            }
        }catch(ArrayIndexOutOfBoundsException aiobe){
            System.out.println("Error: Tu apuntador está fuera de rango");
        }
        
        System.out.println("**********************Ej2***********************");
        int a = 8, b=7;
        try{
            float c = (float) a/b;
            System.out.println("C= "+c);
        }catch(ArithmeticException ae){
            System.out.println("Error: dividiste entre cero");
        }finally{
            System.out.println("A pesar de todo este bloque finally se ejecuta");
        }
        System.out.println("**********************Ej3***********************");
        //Try catch anidados 
        // Siempre debe ir de lo más particular a lo más general 
        try{
            int d= 99/0;
            System.out.println("D= "+d);
        }catch(ArithmeticException ae){
            System.out.println("Error: División etre cero");
        }catch(Exception e){
            System.out.println("Error Exception general");
        }finally{
            System.out.println("El bloque finelly siempre se ejecuta");
        }
        System.out.println("**********************Ej4***********************");
        try{
            int division = metodoPropagaExc(55,0);
            System.out.println("Division= "+division);
        }catch(ArithmeticException ae){
            System.out.println("Exception aritmetica arrojada: ");
            //ae.printStrackTrace();
        }
        
    }
    public static int metodoPropagaExc( int x, int y)throws ArithmeticException{
        if(y==0){
            throw new ArithmeticException();
        }
        return x/y;
    }
}

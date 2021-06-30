# POOP10.ExcepcionesyErrores

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package p10miexcepcion;

/**
 *
 * @author Optiplex 780
 */
public class CuentaBancaria {
   
    private double saldo;

    public CuentaBancaria() {
        saldo = 0;
    }

    public void getSaldo() {
        System.out.println("Saldo "+ saldo);
    }
    
    public void depositar(double monto)throws TopeDepositoException{
        System.out.println("Depositando "+monto+" pesos");
        if(monto > 20000.0)
            throw new TopeDepositoException();
        else
        saldo+=monto;
    }
    public void retirar(double monto) throws SaldoInsufiienteException, MaximosRetirosException {
        System.out.println("Retirando "+monto+ " pesos");
        if(saldo < monto)
            throw new SaldoInsufiienteException();
        else    
            for (int i = 0; i < 3; i++) {  
                if(i<3)                                 
                 saldo-=monto;             
                else
                 throw new MaximosRetirosException();
            } 
    }
}

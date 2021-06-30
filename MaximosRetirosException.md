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
public class MaximosRetirosException extends Exception{
    
    public MaximosRetirosException() {
        super ("Cantidad de retiros sobrepasada");
    }

}

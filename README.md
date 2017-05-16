# ConsultarDNI_RUC_Peru
DLL que permite consultar un DNI o RUC

Agregar las referencias:

HtmlAgilityPack.dll
ProcesosGeneralesCajamiSoft.dll

A su proyecto de VB.net o C#.


```c#
using ProcesosGeneralesCajamiSoft;
````

# Consultar DNI

```c#
//Agregamos el captcha al picturebox
ImagenCaptchaDNI.Image = ProcesosJH.ReadCapchaDNIReniec();

.......

//Con dicho valor, podemos recuperar el nombre y apellidos del DNI
txtNombresApellidos.Text =(String) ProcesosJH.ConsultarDNI(txtDniBuscar.Text, txtCaptchaDNI.Text);

```
![alt text](https://github.com/Cajami/ConsultarDNI_RUC_Peru/blob/master/DNI.png)

# Consultar RUC

```c#
//recuperamos el captcha de sunat
ImagenCaptcha.Image = ProcesosJH.ReadCapchaRUCSunat();

...
//la repuesta la recuperamos en una estructura
ProcesosJH.DatosRuc MiRuc = ProcesosJH.ConsultarRUC("numeroruc", txtCapcha.Text);


....

TxtRazon.Text = MiRuc.RazonSocial;
TxtDir.Text = MiRuc.DireccionDomicilioFiscal;

```

![alt text](https://github.com/Cajami/ConsultarDNI_RUC_Peru/blob/master/RUC.png)

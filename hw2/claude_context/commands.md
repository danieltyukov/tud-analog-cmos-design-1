### **Simulation Commands**

* `.tran 0 20u 0 10n`
* `.noise V(Vout) Vin dec 100 10k 100G`
* `.ac dec 100 1k 100G`
* **`.step param Ibm 1200 2000 100`**
* `.step dec param Mn34 0.1 1000 4`

---

### **Parameters**

* **`.param W=1u L=0.18u Mp=65 Mn=12 Rn=5.3 Rp=7.3`**
* **`.param Aadd=100 mpratio=5.41 Mn12=(4*ScaleA) Mn56=(2*ScaleA) Mn78=(2*ScaleA) Mp13=(4*ScaleA*mpratio) Mp24=(2*ScaleA*mpratio)`**
* **`.param Rin=100G Acl=8 Rfb=(Acl*Rin) Cfb=(Cin/Acl) Cload=(Cin)`**
* `.param ScaleA=0.25 Mn34=(1980*ScaleA) Cin=3.99p Rbig=10G Lbig=1G Ibm=765u`

---

### **Measurement Commands**

* `.meas TRAN Tsettle FIND 20*log10(1.2/(V(virtualground)+1n)) AT 0.3u`
* **`.meas TRAN TR6 TRIG 20*log10(1.2/(V(virtualground)+1n))=40 TD=1n TARG 20*log10(1.2/(V(virtualground)+1n))=48.69 TD=1n`**
* `.meas TRAN Idd AVG I(Vdd) FROM 1n`
* `.meas NOISE Vorms INTEG V(onoise) FROM 10k TO 100G`
* `.meas FoM PARAM -10*log10((2*pi*abs(Idd*1.8)*TR6)/pow(5327,2))`

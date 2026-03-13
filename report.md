## Privilege Escalation Report

Útok fungoval, protože uživatel `student` mohl pomocí `sudo` spouštět program 
`zip` jako uživatel `spravce` bez hesla. Program `zip` umožňuje pomocí parametrů `-T` a `-TT` spustit externí příkaz, 
což umožnilo spustit `cat /home/spravce/.flag` s právy uživatele `spravce` a přečíst vlajku.

Administrátor by měl takové zranitelnosti zabránit tím, že nebude v `sudoers` povolovat programy, 
které mohou spouštět externí příkazy nebo shell. 
Bezpečnější je povolit pouze specifické skripty s omezenými argumenty nebo vytvořit vlastní wrapper skript.

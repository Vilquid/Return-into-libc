# English
# Definition
A return-to-libc attack is a computer security attack usually starting with a buffer overflow in which a subroutine return address on a call stack is replaced by an address of a subroutine that is already present in the process executable memory, bypassing the no-execute bit feature (if present) and ridding the attacker of the need to inject their own code.
# Kernel
Recent versions of kernel patches offer all the protections that prohibit simple return-into-libc exploitation, but it is still effective on other operating systems (Solaris) and on older versions of Linux kernel patches.
# Derived methods
There are other derived methods from these which allow to exploit the stack overflows even with recent versions for these patches.
We are going to discover a more flexible method to make the control of a program without having to resort to a shellcode.
It is indeed possible to directly return a function of the libc or of another library of functions present in the memory space of the attacked process in order to execute it.
# Bypass the patches
This method allows to bypass the patches during the non-executable stack, or to exploit the overflows involving small buffers (not enough space for the shellcode).
This program has a classic flaw involving the strcpy() function.
No check is made on the size of argv[1]. The call to strcpy() will have the effect of copying the string on the stack so a null character will not be encountered below we compile our program and we give it the necessary rights in order to be able to run with root rights for a user normal.
# Warning
I am not responsibile of your acts, this code is only for the knowledge and the security.

#
# Français
# Définition
Une attaque de type return-to-libc est une attaque informatique démarrant généralement par un dépassement de tampon dans lequel l'adresse de retour dans la pile est remplacée par l'adresse d'une autre fonction et une seconde partie de la pile est modifiée pour fournir les paramètres à cette fonction.
# Noyau
Les versions récentes des patchs du noyau proposent toutes les protections qui interdisent une exploitation return-into-libc simple mais elle est encore effective sur d'autres systèmes d'exploitation (Solaris) et sur les anciennes versions des patchs du noyau Linux.
# Méthodes dérivées
Il existe d'autres méthodes dérivées de celles-ci qui permettent d'exploiter les stack overflows même avec des versions récentes pour ces patchs.
Nous allons découvrir une méthode plus souple pour rendre le contrôle d'un programme et ce sans avoir recours à un shellcode.
Il est en effet possible de retourner directement une fonction de la libc ou d'une autre bibliothèque de fonctions présentes dans l'espace mémoire du processus attaqué afin de l'exécuter.
# Contourner les patchs
Cette méthode permet de contourner les patchs pendant la pile non exécutable, ou encore d'exploiter les débordements impliquant de petits buffers (pas assez de place pour le shellcode).
Ce programme comporte une faille classique impliquant la fonction strcpy().
Aucune vérification n'est faite sur la taille de argv[1]. L'appel à strcpy() aura pour effet de copier la chaîne sur la pile donc un caractère nul ne sera pas rencontré ci-après nous compilons notre programme et nous lui donnons les droits nécessaires afin de pouvoir exécuter avec les droits root pour un utilisateur normal.
# Avertissement
Je ne suis pas responsable de vos actes, ce code est seulement là pour la connaissance et la sécurité.

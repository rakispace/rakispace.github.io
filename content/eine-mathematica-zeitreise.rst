======================================================================
Die Zeitreise von Mathematica : Portierung auf eine virtuelle Maschine
======================================================================

:title: Die Zeitreise von Mathematica : Portierung auf eine virtuelle Maschine
:author: Ralf Kinast 
:date: 2009-03-15
:tags: mathematica, virtual box, windows 3.11
:category: blog
:copyright: This document has been placed in the public domain

.. contents: Inhalt

Herzlich willkommen, liebe Leser, zu einem weiteren Blogeintrag, in dem ich meine Experimente mit Software und Technik teile.
Dieses Mal tauchen wir in die Welt von Mathematica ein, dem Programm von Stephen Wolfram.
Ich werde euch zeigen, wie ich es auf eine virtuelle Maschine (VM) portiert habe – und das Ganze von einer uralten Diskettenversion!

Hintergrund
-----------
Mathematica ist schon seit Jahren ein fester Bestandteil der wissenschaftlichen und mathematischen Softwarelandschaft. Aber wie wäre es, wenn wir einen Blick zurück in die Vergangenheit werfen und versuchen würden, dieses Tool auf einer virtuellen Maschine laufen zu lassen?

Schritt 1: Beschaffung der Diskettenversion von Mathematica
-----------------------------------------------------------

Zuerst musste ich meine Hände an einer alten Diskettenversion von Mathematica bekommen. Nach einigen Online-Recherchen und dem Stöbern
 auf Flohmärkten hatte ich endlich Erfolg. Ich konnte eine originalversiegelte Diskettenbox der Version 3.0 ergattern – ein wahres Schmuckstück aus der Vergangenheit.
 
Schritt 2: Aufbereitung der Disketteninhalte
--------------------------------------------
Das Öffnen der versiegelten Box war fast wie eine Zeitreise. Die 3,5-Zoll-Disketten glänzten im grellen Neonlicht meines Arbeitszimmers. Nachdem ich meinen alten
 Diskettenlaufwerkstaub abgepustet hatte, extrahierte ich die Dateien und begann mit der Reise durch den Code von

Mathematica 3.0.Schritt 3: Auswahl der virtuellen Maschine
----------------------------------------------------------
Für die Portierung entschied ich mich für VirtualBox, eine kostenlose, quelloffene Virtualisierungssoftware. Sie schien die perfekte Wahl für dieses Experiment zu sein, da sie eine breite Palette von Betriebssystemen unterstützt und eine benutzerfreundliche Oberfläche bietet.

Schritt 4: Anpassungen für die Virtualisierung
----------------------------------------------

Der Code von Mathematica 3.0 stammte aus einer Ära, in der an VMs kaum zu denken war. Daher mussten einige Anpassungen vorgenommen werden.
  Das Ändern von Hardwarezugriffen und das Beheben von Kompatibilitätsproblemen waren entscheidend, um
  sicherzustellen, dass Mathematica auf der VM reibungslos lief.

Schritt 5: Installation und Test
--------------------------------
Nachdem ich alle



 Vorbereitungen abgeschlossen hatte, startete ich die Installation auf der virtuellen Maschine. Es war faszinierend zu
 sehen, wie ein so altes Programm auf einem modernen Setup zum Leben erwachte. Natürlich musste ich auch
 sicherstellen, dass alle Funktionen reibungslos funktionierten – von den grundlegenden mathematischen Operationen bis
 zu den beeindruckenden Grafikfunktionen.Fazit-----Die erfolgreiche Portierun



 g von Mathematica 3.0 auf eine virtuelle Maschine war nicht nur ein Nostalgie-Trip, sondern auch ein lehrreiches
 Experiment. Es zeigte, wie weit die Virtualisierungstechnologie seit 2009 gekommen ist und wie mächtige Software auch
 auf alten Plattformen zum Leben erweckt werden kann.Ich hoffe, euc

 h hat dieser Blick in die Vergangenheit und meine Experimente mit Mathematica gefallen. Bleibt dran für weitere
 aufregende Entdeckungen und Hacks aus der Welt der Software und Technik!User



Zugegebenermaßen ist das ausgraben von mehr als 20 Jahre alter Software aus Zeiten von Windo    ws 3.11 schon ein etwas
ungewöhnliches Projekt. Ich hatte die Studentenversion von Mathematica (Wolfram Research) wä    hrend meines Studiums
intensiv genutzt. Nun sind mir die Floppies, vier Stück an der Zahl bei einer Aufräumaktion     wieder in die Hände
gefallen. Aber anstatt sich von Altlasten zu trennen, manche Menschen gehören halt zu den Jä    ger und Sammlern, habe ich
mir gedacht das es doch schön wäre das Alte Schätzchen doch noch mal anzuschauen.

OK, soweit so gut.


Floppy sichern
===========================
Da ich allerdings über kein funktionsfähiges Lesegerät verfüge und mir auch keines mehr zule    gen wollte, wurden erstmal
alle verfügbaren Backups der letzten 25 Jahre zusammengeführt. Und siehe da, auf einer alten     HDD war dann doch ein
tar-Archiv der vier Floppies.

Das tar Archiv hatte dann ausgepackt folgende Struktur.

.. code-block:: console

   ralf@spectre:~/Develop/tmp$ tree Mathematica/
   Mathematica/
   ├── Disk1
   │   ├── files
   │   │   ├── document.pak
   │   │   ├── install1.bmp
   │   │   ├── install.ex$
   │   │   ├── install.ins
   │   │   ├── math.hl_
   │   │   ├── mma.bmp
   │   │   ├── setup.exe
   │   │   └── wmathexe.1
   │   └── minstall.exe
   ├── Disk2
   │   └── files
   │       ├── bttncur.dl_
   │       ├── commdlg.dll
   │       ├── ctl3d.dl_
   │       ├── defaults.m_
   │       ├── init.m_
   │       ├── install2.bmp
   │       ├── math22.ini
   │       ├── mathblst.dl_
   │       ├── math.ex_
   │       ├── mcomm.dl_
   │       ├── mmex.dl_
   │       ├── post.dl_
   │       ├── ps.tx_
   │       ├── shell.dll
   │       ├── winhelp.ex_
   │       ├── winmem32.dl_
   │       └── wmathexe.2
   ├── Disk3
   │   └── files
   │       ├── algebra.pak
   │       ├── calculus.pak
   │       ├── ccommon.pak
   │       ├── discrete.pak
   │       ├── examples.pak
   │       ├── gcommon.pak
   │       ├── geometry.pak
   │       ├── graphics.pak
   │       ├── install3.bmp
   │       ├── integrat.pak
   │       ├── linearal.pak
   │       ├── miscella.pak
   │       ├── numberth.pak
   │       ├── numerica.pak
   │       ├── preload.pak
   │       ├── programm.pak
   │       ├── scommon.pak
   │       ├── statisti.pak
   │       ├── utilitie.pak
   │       └── wmathexe.3
   └── Disk4
       └── files
           ├── install4.bmp
           ├── notebook.pak
           └── wmathexe.4

   8 directories, 49 files









Floppy Images erstellen
=======================

Im nächsten Schritt galt es aus den Backups wieder von einer virtuellen Maschine lesbare Floppy Images zu erstellen.

.. code-block:: console

  ralf@spectre:~/Develop/tmp$ mkfs.msdos disk1.img
  ralf@spectre:~/Develop/tmp$ mkfs.msdos disk2.img
  ralf@spectre:~/Develop/tmp$ mkfs.msdos disk3.img
  ralf@spectre:~/Develop/tmp$ mkfs.msdos disk4.img

  ralf@spectre:~/Develop/tmp$ ls -l disk*
  -rwxrwx--- 1 ralf ralf 1474560 Okt 17 22:14 disk1.img
  -rwxrwx--- 1 ralf ralf 1474560 Okt 17 22:16 disk2.img
  -rwxrwx--- 1 ralf ralf 1474560 Okt 17 22:17 disk3.img
  -rwxrwx--- 1 ralf ralf 1474560 Okt 17 22:17 disk4.img

  ralf@spectre:~/Develop/tmp$ sudo mkdir /media/floppy

  ralf@spectre:~/Develop/tmp$ sudo mount -o loop disk1.img /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo cp -av Mathematica/Disk1/* /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo umount floppy

  ralf@spectre:~/Develop/tmp$ sudo mount -o loop disk2.img /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo cp -av Mathematica/Disk2/* /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo umount /media/floppy

  ralf@spectre:~/Develop/tmp$ sudo mount -o loop disk3.img /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo cp -av Mathematica/Disk3/* /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo umount /media/floppy

  ralf@spectre:~/Develop/tmp$ sudo mount -o loop disk4.img /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo cp -av Mathematica/Disk4/* /media/floppy/
  ralf@spectre:~/Develop/tmp$ sudo umount /media/floppy

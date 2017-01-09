/*************************************************************************************
 * Plugin Written communications documentation
 *
 * Copyright    : (c) 2004 - 2017 The Admidio Team
 * Homepage     : http://www.admidio.org
 * Author       : Thomas-RCV
 * License      : GNU Public License 2 http://www.gnu.org/licenses/gpl-2.0.html
 * Version      : 3.1
 *
 ************************************************************************************/
 
 Dieses Plugin erm�glicht es Briefe und Serienbriefe zu erstellen. Basiernd auf einer *.docx Vorlage mit Platzhaltern (Template),
 generiert dieses Plugin das komplette Dokument und startet den Download der erstellten Datei.
 Das erstellte Dokument kann dann mit entsprechender Software auf dem PC weiter verarbeitet werden.
 Unterst�tzt werden MS Office, Open Office und Libre Office.
 
 

 1. Systemanforderungen
 ----------------------
 
 - Admidio Version 2.4.4 oder h�her
 
 


 2. Installation
 ---------------
 
 - keine Installation erforderlich. 
 - Das Plugin entpacken und in den Ordner adm_plugins kopieren.
 - Link zum Plugin in das Admidio Men� in den Themes einf�gen.
 
  
  
   Beispiel:
   ---------
   In der Datei my_body_bottom.php am Ende des Men�s folgenden Link anf�gen
   
   
   
   $moduleMenu->addItem('written_communications', '/adm_plugins/written_communications/written_communications.php',
        									'Brief erstellen', '/icons/page_white_word.png');
                                            
   
   
   Zugriffsrechte k�nnen an Rollen gekoppelt werden. Hier verwende bitte die Admidio Funktion hasRole()
   
   Beispiel f�r Zugriff nur f�r den Webmaster und den Vorstand:
   ------------------------------------------------------------
   
   if(hasRole('Administrator', 'Vorstand')
   {
        $moduleMenu->addItem('written_communications', '/adm_plugins/written_communications/written_communications.php',
        									'Brief erstellen', '/icons/page_white_word.png');
   } 
   
   
 
 
 
 3. Updates
 ----------
 
 - Bei einem neuen Release werden die alle Dateien und Ordner durch neuere Versionsscripte ersetzt.
 
 INFO: Seit der Admidio Version 3.2 wurde die Rolle "Webmaster" in "Administrator" umbenannt und die alte Bezeichnung wird k�nftig entfernt.
       Deshalb aktualisiere bitte deine config.php des Plugins und �ndere bitte die Rollen�berwachung in $plg_wc_roleArray = array('Administrator');, sofern du diese verwendest, um Programmfehler zu vermeiden.
       
 
 


 4. Eigene Briefvorlage erstellen:
 ---------------------------------

Zur Erstellung eigener Vorlagen ist das Plugin an das Downloadmodul von Admidio gekoppelt. 
Eigene Briefvorlagen sollten nicht in dem Beispiel Ordner "Templates" des Plugins erstellt werden, da dieser Ordner unter Umst�nden
bei Updates ersetzt wird.

 - Im Download Modul einen Ordner "MSWord_Templates" erstellen. Sobald ein solches Verzeichnis existiert wird dieser Ordner zur Auswahl genutzt.
 - Jetzt k�nnen die eigenen Vorlagen bequem �ber den Upload bereitgestellt werden. Die Templates m�ssen das Format *.docx haben ! 
   Die alten *.doc Formate und auch Vorlagenformate sind nicht zul�ssig!
 - Die zuverwendenden Platzhalter sind in den Demo Templates demo_de.docx und demo_en.docx im Ordner templates des Plugins enthalten. 
 
   



    
    
   
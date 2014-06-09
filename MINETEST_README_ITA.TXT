<-------------------- larghezza: 80 caratteri monospazio ---------------------->

Scarico di responsabilità
-------------------------

La presente traduzione viene fornita come forma di cortesia a titolo gratuito
e non può essere ritenuta come un valido sostitutivo del documento originale
ufficiale in lingua Inglese perché:

  - Non è promossa, né supportata, né appoggiata, né autorizzata dagli
    sviluppatori di Minetest.
  - Il traduttore non è un traduttore professionista.
  - Il traduttore non è un esperto di termini legali.
  - Al momento della lettura potrebbe essere diventata obsoleta in quanto
    potrebbe essere stata scritta una nuova versione in Inglese.

per questi motivi il testo seguente potrebbe contenere inesattezze e errori di
vario tipo e perciò il traduttore non si assume nessuna responsabilità legata a
problemi di qualsiasi tipo derivanti dall'utilizzo di questa traduzione, né il
traduttore potrà esserne ritenuto responsabile in alcun modo.

Il traduttore consiglia espressamente di fare sempre riferimento al testo
originale ufficiale in lingua Inglese fornito assieme a Minetest.

Questa traduzione è stata fatta in buona fede e al meglio delle possibilità del
traduttore, come contributo effettivo per gli utilizzatori di lingua Italiana
di Minetest.

Utilizzando la presente traduzione accettate di sollevare il traduttore da
qualsiasi responsabilità così come accettate quanto prima espresso.

Enki, Lunedì 6 giugno 2014
Copyright: CC BY-SA 4.0 https://creativecommons.org/licenses/by-sa/4.0/deed.it
(Attribuzione - Condividi allo stesso modo 4.0 Internazionale)

--------------------------------------------------------------------------------


Minetest
========

Un gioco ispirato a InfiniMiner/Minecraft.

Copyright (c) 2010-2013 Perttu Ahola <celeron55@gmail.com>
e collaboratori (si vedano i commenti ai file sorgente e il registro del
controllo di versione)


In caso abbiate scaricato il codice sorgente:
---------------------------------------------

Se avete scaricato il codice sorgente del motore di Minecraft in cui è contenuto
questo file, probabilmente vorrete scaricare anche il progetto minetest_game:

https://github.com/minetest/minetest_game/

Si veda il file README.txt in esso.


Documentazione ulteriore:
-------------------------

- Sito web: http://minetest.net/
- Wiki: http://wiki.minetest.net/
- Wiki dello sviluppatore: http://dev.minetest.net/
- Forum: http://forum.minetest.net/
- Github: https://github.com/minetest/minetest/
- doc/ cartella della distribuzione in formato sorgente


Questo gioco non è completato
-----------------------------

- Non aspettatevi che funzioni bene come un gioco completato.
- Per favore segnalate qualsiasi errore. Quando lo fate, debug.txt è utile.


Controlli predefiniti
---------------------

- W A S D: muoversi
- Spazio: saltare/arrampicarsi
- Maiusc: strisciare/scendere
- Q: scartare l'oggetto
- I: inventario
- Mouse: girarsi/guardare
- Tasto sinistro del mouse: scavare/colpire
- Tasto destro del mouse: posizionare/usare
- Rotellina del mouse: scegliere l'oggetto
- Esc: menù di pausa
- T: chat
- Impostabili nel file di configurazione, si veda la sezione sottostante.


Percorsi
--------

$bin - File binari compilati
$share - Dati di sola lettura distribuiti
$user - Dati modificabili creati dall'utente

Windows .zip / RUN_IN_PLACE sorgente:
$bin = bin
$share = .
$user = .

Installato su GNU/Linux:
$bin = /usr/bin
$share = /usr/share/minetest
$user = ~/.minetest

OS X:
$bin = ?
$share = ?
$user = ~/Library/Application Support/minetest


Cartella dei mondi
------------------

- I mondi possono essere trovati come cartelle separate in:
    $user/worlds/


File di configurazione:
-----------------------

- Posizione predefinita:
    $user/minetest.conf

- Viene creato da Minetest al primo avvio.

- E' possibile indicare un file specifico dalla linea di comando:
  --config <percorso-del-file>


Opzioni della linea di comando:
-------------------------------

- Usate --help


Compilare su GNU/Linux:
-----------------------

- Installate le dipendenze. Ecco un esempio per Debian/Ubuntu:

$ apt-get install build-essential gettext libirrlicht-dev cmake libbz2-dev libpng12-dev libjpeg8-dev libxxf86vm-dev libgl1-mesa-dev libsqlite3-dev libogg-dev libvorbis-dev libopenal-dev libcurl4-gnutls-dev libfreetype6-dev

- Scaricate i file sorgente, estraeteli (questo è lo URL del deposito sorgente,
che potrebbe non funzionare sempre):

$ wget https://github.com/minetest/minetest/tarball/master -O master.tar.gz
$ tar xf master.tar.gz
$ cd minetest-minetest-286edd4 (or similar)

- Scaricate minetest_game (altrimenti è disponibile solo il gioco
"Minimal development test" ("Prova minima di sviluppo", n.d.t.)

$ cd games/
$ wget https://github.com/minetest/minetest_game/tarball/master -O minetest_game.tar.gz
$ tar xf minetest_game.tar.gz
$ mv minetest-minetest_game-* minetest_game
$ cd ..

- Costruite una versione che funzioni direttamente dalla cartella di
  installazione:

$ cmake . -DRUN_IN_PLACE=1 -DENABLE_FREETYPE=ON -DENABLE_GETTEXT=ON
$ make -j2

Avviatela:

$ cd bin
$ ./minetest

- Usate cmake . -LH per vedere tutte le opzioni di CMake e il loro stato
  corrente.

- Se volete installarla per tutto il sistema operativo (o state creando un
  pacchetto di distribuzione), vorrete usare -DRUN_IN_PLACE=0

- Potete costruire un client o un server essenziali specificando

-DBUILD_CLIENT=0 o -DBUILD_SERVER=0

- Potete scegliere tra costruire una versione di rilascio o di debug tramite

-DCMAKE_BUILD_TYPE=<Debug o Release>

  - La costruzione di quella di debug è più lenta, ma fornisce informazioni più
    utili in un debugger

- Se costruite un server essenziale, non vi serve avere Irrlicht installato. In
  quel caso usate -DIRRLICHT_SOURCE_DIR=/la/sorgente/irrlicht


Opzioni di CMake
----------------

- Opzioni generali:

BUILD_CLIENT - Costruire il client di Minetest

BUILD_SERVER - Costruire il server di Minetest

CMAKE_BUILD_TYPE - Tipo di costruzione (Release o Debug)

    Release - Costruzione di rilascio

    Debug - Costruzione di debug

    RelWithDebInfo - Costruzione di rilascio con le informazioni di debug

    MinSizeRel - Costruzione di rilascio con -Os fornito al compilatore per
                 rendere l'eseguibile il più piccolo possibile.

ENABLE_CURL - Costruire con cURL; abilita l'utilizzo in linea del deposito dei
              moduli, l'elenco dei server pubblici e il recupero dei file
              multimediali tramite http

ENABLE_FREETYPE - Costruire con Freetype2; permette l'uso dei caratteri TTF

ENABLE_GETTEXT - Costruire con Gettext; permette l'uso delle traduzioni

ENABLE_GLES - Cerca gli header e le librerie di Open GLES e li usa

ENABLE_LEVELDB - Costruire con LevelDB; abilita l'uso di LevelDB, che è molto
più veloce di SQLite, come base per la mappa

ENABLE_SOUND - Costruire con OpenAL, libogg e libvorbis; suoni nel gioco

DISABLE_LUAJIT - Non cercare gli header e la libreria di LuaJIT

RUN_IN_PLACE - Creare una installazione portatile (mondi, impostazioni, ecc.
               nella cartella attuale)

USE_GPROF - Abilita l'analisi comportamentale a fini investigativi tramite GProf
            ( http://www.wordreference.com/enit/profiling , n.d.t.)

VERSION_EXTRA - Testo da posporre alla versione, ad es.: 
                VERSION_EXTRA=esempio -> Minetest 0.4.9-esempio)


Opzioni specifiche della libreria:
----------------------------------

BZIP2_INCLUDE_DIR - Solo GNU/Linux; cartella in cui sta bzlib.h

BZIP2_LIBRARY - Solo GNU/Linux; percorso di libbz2.a/libbz2.so

CURL_DLL - Solo se si costruisce con cURL in Windows; percorso di libcurl.dll

CURL_INCLUDE_DIR - Solo se si costruisce con cURL; cartella dove sta curl.h

CURL_LIBRARY - Solo se si costruisce con cURL; percorso di
               libcurl.a/libcurl.so/libcurl.lib

EGL_INCLUDE_DIR - Solo se si costruisce con GLES; cartella contenente egl.h

EGL_egl_LIBRARY - Solo se si costruisce con GLES; percorso di libEGL.a/libEGL.so

FREETYPE_INCLUDE_DIR_freetype2 - Solo se si costruisce con Freetype2; cartella
                                 che contiene una cartella freetype con i file
                                 come ftimage.h in essa

FREETYPE_INCLUDE_DIR_ft2build - Solo se si costruisce con Freetype2; cartella
                                che contiene ft2build.h

FREETYPE_LIBRARY - Solo se si costruisce con Freetype2; percorso di
                   libfreetype.a/libfreetype.so/freetype.lib

GETTEXT_DLL - Solo quando si costruisce con Gettext in Windows; percorso di
              libintl3.dll

GETTEXT_ICONV_DLL - Solo quando si costruisce con Gettext in Windows; percorso
                    di libiconv2.dll

GETTEXT_INCLUDE_DIR - Solo quando si costruisce con Gettext; cartella che
                      contiene iconv.h

GETTEXT_LIBRARY - Solo quando si costruisce con Gettext in Windows; percorso di
                  libintl.dll.a

GETTEXT_MSGFMT - Solo quando si costruisce con; percorso di msgfmt/msgfmt.exe

IRRLICHT_DLL - percorso di Irrlicht.dll

IRRLICHT_INCLUDE_DIR - cartella che contiene IrrCompileConfig.h

IRRLICHT_LIBRARY - percorso di libIrrlicht.a/libIrrlicht.so/libIrrlicht.dll.a

LEVELDB_INCLUDE_DIR - Solo quando si costruisce con LevelDB; cartella che
                      contiene db.h

LEVELDB_LIBRARY - Solo quando si costruisce con LevelDB; percorso di
                  libleveldb.a/libleveldb.so/libleveldb.dll

LUA_INCLUDE_DIR - Solo se volete usare LuaJIT; cartella dove sta luajit.h

LUA_LIBRARY - Solo se volete usare LuaJIT; percorso di libluajit.a/libluajit.so

MINGWM10_DLL - Solo se volete compilare con MinGW; percorso di mingwm10.dll

OGG_DLL - Solo se costruite col suono in Windows; percorso di libogg.dll

OGG_INCLUDE_DIR - Solo se costruite col suono; cartella che contiene una
                  cartella ogg contenente ogg.h

OGG_LIBRARY - Solo se costruite col suono; percorso di
              libogg.a/libogg.so/libogg.dll.a

OPENAL_DLL - Solo se costruite col suono in Windows; percorso di OpenAL32.dll

OPENAL_INCLUDE_DIR - Solo se costruite col suono; cartella dove sta al.h

OPENAL_LIBRARY - Solo se costruite col suono; percorso di
                 libopenal.a/libopenal.so/OpenAL32.lib

OPENGLES2_INCLUDE_DIR - Solo se costruite con GLES; cartella che contiene gl2.h

OPENGLES2_gl_LIBRARY - Solo se costruite con GLES; percorso di
                       libGLESv2.a/libGLESv2.so

SQLITE3_INCLUDE_DIR - Solo se volete usare SQLite dal vostro s.o.; cartella che
                      contiene sqlite3.h

SQLITE3_LIBRARY - Solo se volete usare SQLite dal vostro s.o.; percorso di
                  libsqlite3.a/libsqlite3.so

VORBISFILE_DLL - Solo se costruite col suono su Windows; percorso di
                 libvorbisfile-3.dll

VORBISFILE_LIBRARY - Solo se costruite col suono; percorso di
                     libvorbisfile.a/libvorbisfile.so/libvorbisfile.dll.a

VORBIS_DLL - Solo se costruite col suono su Windows; percorso di libvorbis-0.dll

VORBIS_INCLUDE_DIR - Solo se costruite col suono; cartella che contiene una
                     cartella vorbis con vorbisenc.h al suo interno

VORBIS_LIBRARY - Solo se costruite col suono; percorso di
                 libvorbis.a/libvorbis.so/libvorbis.dll.a

XXF86VM_LIBRARY - Solo in GNU/Linux; percorso di libXXf86vm.a/libXXf86vm.so

ZLIB_DLL - Solo in Windows; percorso di zlibwapi.dll

ZLIB_INCLUDE_DIR - cartella dove sta zlib.h

ZLIB_LIBRARY - percorso di libz.a/libz.so/zlibwapi.lib


Compilare in Windows:
---------------------

- Questa sezione è antiquata. In aggiunta a quanto qui descritto:
  - In aggiunta a minetest, dovete scaricare minetest_game.
  - Se desiderate avere il supporto audio, vi servono libogg, libvorbis e
    libopenal

- Vi servono:

* CMake:
http://www.cmake.org/cmake/resources/software.html

* MinGW o Visual Studio
http://www.mingw.org/
http://msdn.microsoft.com/it-it/vstudio/default

* Irrlicht SDK 1.7:
http://irrlicht.sourceforge.net/downloads.html

* Header Zlib (zlib125.zip)
http://www.winimage.com/zLibDll/index.html

* Libreria Zlib (zlibwapi.lib e zlibwapi.dll da zlib125dll.zip):
http://www.winimage.com/zLibDll/index.html

* Facoltativi: libreria gettext e strumenti:
http://gnuwin32.sourceforge.net/downlinks/gettext.php

- Questi vengono usati per le lingue dell'interfaccia utente. Sentitevi liberi
  di tralasciarli.

* E, certamente, Minetest:
http://minetest.net/download.php

- Passi:

- Scegliete una cartella in cui opererete, d'ora in poi la chiameremo "CART".

- Assicuratevi di avere installato CMake e un compilatore.

- Scaricate tutto il resto in CART e estraetelo lì dentro.
  ("estrai qui", non "estrai in nomepacchetto/")

NOTA: zlib125dll.zip deve essere estratta in zlib125dll

- Tutti quei pacchetti contengono una bella cartella di base in essi, che
  dovrebbero finire per essere le sottocartelle dirette di CART.

- Vi ritroverete con una struttura di cartelle come questa
  (+ = cartella, - = file):

-----------------
+ CART
- zlib-1.2.5.tar.gz
- zlib125dll.zip
- irrlicht-1.7.1.zip
- 110214175330.zip (o quello che è, questo è il sorgente di minetest)
+ zlib-1.2.5
- zlib.h
+ win32
...
+ zlib125dll
- readme.txt
+ dll32
...
+ irrlicht-1.7.1
+ lib
+ include
...
+ gettext (facoltativo)
+bin
+include
+lib
+ minetest
+ src
+ doc
- CMakeLists.txt
...
-----------------

- Avviate l'interfaccia grafica di CMake
- Scegliete "Mostra sorgente..." e scegliete CART/minetest

- Adesso, se usate MSVC: 
- Scegliete "Mostra Build..." e scegliete CART/minetest-build

- Altrimenti, se usate MinGW:
- Scegliete "Mostra Build..." e scegliete CART/minetest

- Scegliete "Configura"
- Scegliete il vostro compilatore
- Vi avvertirà delle cose mancanti, per adesso ignoratelo. (Più tardi no.)
- Assicuratevi che la configurazione sia come segue (notate che le versioni per
voi potrebbero essere differenti):

-----------------
BUILD_CLIENT [X]
BUILD_SERVER [ ]
CMAKE_BUILD_TYPE Release
CMAKE_INSTALL_PREFIX CART/minetest-install
IRRLICHT_SOURCE_DIR CART/irrlicht-1.7.1
RUN_IN_PLACE [X]
WARN_ALL [ ]
ZLIB_DLL CART/zlib125dll/dll32/zlibwapi.dll
ZLIB_INCLUDE_DIR CART/zlib-1.2.5
ZLIB_LIBRARIES CART/zlib125dll/dll32/zlibwapi.lib
GETTEXT_BIN_DIR CART/gettext/bin
GETTEXT_INCLUDE_DIR CART/gettext/include
GETTEXT_LIBRARIES CART/gettext/lib/intl.lib
GETTEXT_MSGFMT CART/gettext/bin/msgfmt
-----------------

- Premete "Configura"
- Premete "Configura" ancora una volta 8)
- Se qualcosa è ancora colorato in rosso, avete un problema.
- Premete "Genera"


Se usate MSVC:

- Aprite il minetest.sln generato
- Il progetto è configurato in modalità "Debug" in modo predefinito. Accertatevi
per bene di scegliere "Release", a meno che vogliate correggere un po' di roba
(è più lento e potrebbe persino non funzionare affatto)

- Costruite il progetto ALL_BUILD
- Costruite il progetto INSTALL
- Adesso dovreste avere un gioco funzionante con l'eseguibile in
  CART/minetest-install/bin/minetest.exe

- In aggiunta potreste creare un pacchetto zip costruendo il progetto PACKAGE.


Se usate MinGW:

- Tramite la riga di comando, andate alla cartella di costruzione e eseguite
'make' (o mingw32-make o qualunque sia)
- Potreste dovere copiare qualcuna delle dll scaricate in bin/, vedete quale,
provando l'eseguibile ottenuto vi dirà cosa manca.
- Adesso dovreste avere un gioco funzionante con l'eseguibile in
  CART/minetest/bin/minetest.exe


I rilasci di Windows sono costruiti utilizzando uno script .bat come questo:
----------------------------------------------------------------------------

set sourcedir=%CD%
set installpath="C:\tmp\minetest_install"
set irrlichtpath="C:\tmp\irrlicht-1.7.2"

set builddir=%sourcedir%\bvc10
mkdir %builddir%
pushd %builddir%
cmake %sourcedir% -G "Visual Studio 10" -DIRRLICHT_SOURCE_DIR=%irrlichtpath% -DRUN_IN_PLACE=1 -DCMAKE_INSTALL_PREFIX=%installpath%
if %errorlevel% neq 0 goto fail
"C:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\MSBuild.exe" ALL_BUILD.vcxproj /p:Configuration=Release
if %errorlevel% neq 0 goto fail
"C:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\MSBuild.exe" INSTALL.vcxproj /p:Configuration=Release
if %errorlevel% neq 0 goto fail
"C:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\MSBuild.exe" PACKAGE.vcxproj /p:Configuration=Release
if %errorlevel% neq 0 goto fail
popd
echo Finito.
exit /b 0

:fail
popd
echo Fallito.
exit /b 1


Licenza delle immagini e dei suoni di Minetest
----------------------------------------------

Ciò vale per le immagini e i suoni contenuti nella distribuzione principale di
Minetest.

Attribuzione - Condividi allo stesso modo 3.0 Unported (CC BY-SA 3.0)
https://creativecommons.org/licenses/by-sa/3.0/deed.it


Autori dei file multimediali
----------------------------

Per tutto quanto non qui elencato:
Copyright (C) 2010-2012 celeron55, Perttu Ahola <celeron55@gmail.com>

BlockMen:
  textures/base/pack/menuheader.png

erlehmann:
  misc/minetest-icon-24x24.png
  misc/minetest-icon.ico
  misc/minetest-icon.svg
  textures/base/pack/logo.png


Licenza del codice sorgente di Minetest
---------------------------------------

Minetest
Copyright (C) 2010-2013 celeron55, Perttu Ahola <celeron55@gmail.com>

Questo programma è software libero; potete ridistribuirlo e/o modificarlo sotto
i termini della GNU Lesser General Public License come pubblicata dalla
Free Software Foundation; sia la versione della licenza la 2.1, o (a vostra
scelta) qualsiasi versione successiva.

Questo programma è distribuito nella speranza che sarà utile,
ma SENZA NESSUNA GARANZIA; senza nemmeno la garanzia implicita
di COMMERCIABILITA' o ADEGUATEZZA PER UNO SCOPO PARTICOLARE.
Per maggiori dettagli si veda la GNU Lesser General Public License.

Dovreste avere ricevuto una copia della GNU Lesser General Public License
assieme a questo programma; se no, scrivete alla

Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor,
Boston, MA 02110-1301 USA.


Irrlicht
---------------

Questo programma usa il Motore Irrlicht. http://irrlicht.sourceforge.net/


La licenza del Motore Irrlicht

Copyright © 2002-2005 Nikolaus Gebhardt

Questo programma è fornito 'così-come-è', senza nessuna garanzia implicita
o esplicita. In nessun caso gli autori potranno essere ritenuti responsabili
per qualsiasi danno provocato dall'utilizzo di questo programma.

E' garantito a chiunque il permesso di usare questo programma per qualsiasi
scopo, applicazioni commerciali incluse, e di alterarlo e ridistribuirlo
liberamente, soggetto alle seguenti restrizioni:

   1. L'origine di questo programma non deve essere rappresentata
      scorrettamente; non dovete sostenere di avere scritto il programma
      originale. Se usate questo programma in un prodotto, sarebbe
      gradito un riconoscimento nella documentazione del programma, ma non
      è richiesto.

   2. Le versioni sorgente alterate devono essere chiaramente marcate
      come tali, e non devono rappresentare scorrettamente di essere il
      programma originale.

   3. Questo avviso non può essere alterato o rimosso da qualsiasi
      distribuzione sorgente.


JThread
---------------

Questo programma usa la libreria JThread. Segue la licenza per JThread:

Copyright (c) 2000-2006 Jori Liesenborgs (jori.liesenborgs@gmail.com)

Con la presente si garantisce il premesso, senza costo, a qualsiasi persona
che ottenga una copia di questo programma e i file di documentazione
associati (il "programma"), di includere il programma senza restrizione,
inclusa nessuna limitazione dei diritti di utilizzo, copia, modifica,
unione, pubblicazione, distribuzione, sottolicenza e/o vendita di copie
del programma, e di permettere di fare altrettanto alle persone a cui
viene fornito il programma, soggetti alle condizioni seguenti:

L'avviso di copyright soprastante e questo avviso di permesso dovranno
essere inclusi in tutte le copie o porzioni considerevoli del programma.

IL PROGRAMMA VIENE FORNITO "COSI' COME E'", SENZA GARANZIA DI QUALSIASI
TIPO, IMPLICITA O ESPLICITA, INCLUSE MA NON LIMITATE ALLE GARANZIE DI
COMMERCIABILITA', ADEGUATEZZA PER UNO SCOPO PARTICOLARE E NON INFRAZIONE.
IN NESSUN CASO GLI AUTORI O I DETENTORI DEL COPYRIGHT POTRANNO ESSERE
CONSIDERATI RESPONSABILI PER QUALSIASI RECLAMO, DANNO O ALTRE
RESPONSABILITA', SIANO IN UN ATTO CONTRATTUALE, ILLECITO CIVILE O
ALTRIMENTI, DERIVANTI DA O IN CONNESSIONE COL PROGRAMMA O L'USO O ALTRO
TRATTAMENTO DEL PROGRAMMA.


Lua
---------------

Lua è licenziato sotto i termini della licenza MIT riportata sotto.
Questo significa che Lua è un programma libero e può essere usato
sia per propositi accademici e commerciali senza assolutamente nessun
costo.

Per spiegazione e dettagli, si veda http://www.lua.org/license.html .

Copyright (C) 1994-2008 Lua.org, PUC-Rio.

Con la presente si garantisce il premesso, senza costo, a qualsiasi persona
che ottenga una copia di questo programma e i file di documentazione
associati (il "programma"), di includere il programma senza restrizione,
inclusa nessuna limitazione dei diritti di utilizzo, copia, modifica,
unione, pubblicazione, distribuzione, sottolicenza e/o vendita di copie
del programma, e di permettere di fare altrettanto alle persone a cui
viene fornito il programma, soggetti alle condizioni seguenti:

L'avviso di copyright soprastante e questo avviso di permesso dovranno
essere inclusi in tutte le copie o porzioni considerevoli del programma.

IL PROGRAMMA VIENE FORNITO "COSI' COME E'", SENZA GARANZIA DI QUALSIASI
TIPO, IMPLICITA O ESPLICITA, INCLUSE MA NON LIMITATE ALLE GARANZIE DI
COMMERCIABILITA', ADEGUATEZZA PER UNO SCOPO PARTICOLARE E NON INFRAZIONE.
IN NESSUN CASO GLI AUTORI O I DETENTORI DEL COPYRIGHT POTRANNO ESSERE
CONSIDERATI RESPONSABILI PER QUALSIASI RECLAMO, DANNO O ALTRE
RESPONSABILITA', SIANO IN UN ATTO CONTRATTUALE, ILLECITO CIVILE O
ALTRIMENTI, DERIVANTI DA O IN CONNESSIONE COL PROGRAMMA O L'USO O ALTRO
TRATTAMENTO DEL PROGRAMMA.

Caratteri
---------------

DejaVu Sans Mono:

  I caratteri sono (c) Bitstream (si veda sotto).
  Le modifiche di DejaVu sono in pubblico dominio.
  I glifi importati dai caratteri Arev sono (c) Tavmjong Bah (si veda sotto).


Copyright dei caratteri Bitstream Vera:

  Copyright (c) 2003 di Bitstream, Inc. Tutti i diritti sono riservati.
  Bitstream Vera è un marchio commerciale di Bitstream, Inc.


Copyright dei caratteri Arev:

  Copyright (c) 2006 di Tavmjong Bah. Tutti i diritti sono riservati.


Copyright Liberation Fonts:

  Copyright (c) 2007 Red Hat, Inc. Tutti i diritti sono riservati.
  LIBERATION è un marchio commerciale di Red Hat, Inc.


DroidSansFallback:

  Copyright (C) 2008 The Android Open Source Project

  Licenziato sotto la licenza Apache, Versione 2.0 (la "licenza");
  non potete utilizzare questo file eccetto che in accordo con la
  licenza. Potete ottenere una copia della licenza da:

     http://www.apache.org/licenses/LICENSE-2.0

  A meno che sia richiesto da una legge applicabile o concordato in forma
  scritta, il programma distribuito sotto la licenza è distribuito su una
  base "COSI' COME E'", SENZA GARANZIE O CONDIZIONI DI NESSUN TIPO, siano
  implicite o esplicite. Si veda la licenza per i permessi e le limitazioni
  specifiche del linguaggio di governo sotto la licenza.
  

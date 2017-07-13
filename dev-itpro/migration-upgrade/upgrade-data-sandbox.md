---
title: "Uaktualnianie danych w środowisku piaskownicy"
description: "W tym temacie opisano sposób przeprowadzenia uaktualnienia danych z systemu AX 2012 do programu Dynamics 365 for Finance and Operations w środowisku piaskownicy."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 7140bf740f37a5eb970a5103750a7095d12a33cc
ms.contentlocale: pl-pl
ms.lasthandoff: 06/15/2017

---

# Uaktualnianie danych w środowisku piaskownicy
<a id="data-upgrade-in-a-sandbox-environment" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

Produktem wyjściowym tego zadania jest uaktualniona baza danych, której można używać w środowisku piaskownicy. Środowisko piaskownicy to środowisko, gdzie użytkownicy biznesowi i członkowie zespołu funkcjonalnego mogą weryfikować funkcjonalność aplikacji. Ta funkcjonalność obejmuje dostosowania i dane, które zostało przeniesione z systemu Microsoft Dynamics AX 2012.

Stanowczo zalecamy, aby wykonać proces uaktualniania danych w środowisku projektowym, zanim zostanie wykonany we współużytkowanym środowisku piaskownicy, ponieważ pomoże to ograniczyć łączny czas potrzeby na pomyślne uaktualnienie danych. Aby uzyskać więcej informacji, zobacz [Uaktualnianie danych w środowisku projektowym](prepare-data-upgrade.md).

## Omówienie procesu uaktualniania danych w piaskownicy
<a id="overview-of-the-sandbox-data-upgrade-process" class="xliff"></a>

Przed rozpoczęciem uaktualniania danych w środowisku piaskownicy trzeba mieć już przeprowadzone uaktualnianie danych w środowisku projektowym, jak wyjaśniono w temacie [Uaktualnianie danych w środowisku projektowym](prepare-data-upgrade.md). Te dwa procesy są bardzo podobne. Główna różnica polega na tym, że środowisku piaskownicy używa systemu bazodanowego Microsoft Azure SQL do przechowywania danych, a środowisko projektowe używa programu Microsoft SQL Server. Ta różnica techniczna w warstwie bazy danych wymaga pewnego zmodyfikowania procedury uaktualniania danych w środowisku piaskownicy, ponieważ kopii zapasowej z wystąpienia bazy danych w systemie AX 2012 nie można po prostu przywrócić do bazy danych SQL.

![Proces uaktualniania danych w piaskownicy](./media/data-upgrade-sandbox.png)

Poniżej przedstawiono ogólne zadania w procesie uaktualniania.

1. Utworzenie kopii bazy danych systemu AX 2012. Stanowczo zalecamy korzystanie z kopii, ponieważ należy usunąć niektóre obiekty w kopii przeznaczonej do wyeksportowania.
2. Wyeksportowanie skopiowanej bazy danych do pliku bacpac za pomocą bezpłatnego narzędzia programu SQL Server o nazwie SQLPackage.exe. To narzędzie tworzy specjalny typ kopii zapasowej bazy danych, który można importować do systemu bazodanowego SQL Database.
3. Przekazanie pliku bacpac do magazynu Azure.
4. Pobranie pliku bacpac do komputera serwera obiektów aplikacji (AOS) w środowisku piaskownicy, a następnie zaimportowanie go za pomocą narzędzia SQLPackage.exe. Następnie należy uruchomić skrypt wobec zaimportowanej bazy danych, aby zresetować użytkowników bazy danych SQL.
5. Uruchomienie pakietu MajorVersionDataUpgrade.zip w celu przeprowadzenia uaktualnienia danych w zaimportowanej bazie danych.

## Tworzenie kopii bazy danych systemu AX 2012
<a id="create-a-copy-of-the-ax-2012-database" class="xliff"></a>

Należy utworzyć kopię bazy danych systemu AX 2012, która będzie uaktualniania, ponieważ trzeba usunąć niektóre obiekty z bazy. Do obiektów tych należą wszyscy uwierzytelnieni użytkownicy systemu Microsoft Windows. Te zmiany sprawiają, że zmodyfikowana baza danych nie będzie działać w systemie AX 2012. W tym kroku utworzysz kopię bazy danych i usuniesz obiekty.

Ten krok musi być wykonywany przez administratora baz danych (DBA) lub osobę mającą podobną wiedzę i doświadczenie.

W celu utworzenia kopii bazy danych utwórz kopię oryginalnej bazy, a następnie przywrócić ją pod nową nazwą. Upewnij się, że masz wystarczającą ilość miejsca na obie bazy danych. Kopię można utworzyć na innym serwerze. Wersja programu SQL Server, w którym jest uruchomiona baza danych, nie ma znaczenia.

Poniżej przedstawiono przykładowy kod źródłowy powodujący utworzenie kopii bazy danych. Należy zmodyfikować ten przykład o własne nazwy baz danych.

    BACKUP DATABASE [AxDB] TO  DISK = N'D:\Backups\axdb_copyForUpgrade.bak' WITH NOFORMAT, NOINIT,  
    NAME = N'AxDB_copyForUpgrade-Full Database Backup', SKIP, NOREWIND, NOUNLOAD, COMPRESSION,  STATS = 10
    GO

    RESTORE DATABASE [AxDB_copyForUpgrade] FROM  DISK = N'D:\Backups\axdb_copyForUpgrade.bak'   WITH  FILE = 1,  
    MOVE N'AXDBBuild_Data' TO N'F:\MSSQL_DATA\AxDB_copyForUpgrade.mdf',  
    MOVE N'AXDBBuild_Log' TO N'G:\MSSQL_LOGS\AxDB_CopyForUpgrade.ldf',  
    NOUNLOAD,  STATS = 5

Po utworzeniu kopii wykonaj na niej następujący skrypt języka Transact-SQL (T-SQL).
TODO 

### Eksportowanie skopiowanej bazy danych do pliku bacpac
<a id="export-the-copied-database-to-a-bacpac-file" class="xliff"></a>

Wyeksportuj skopiowaną bazę danych do pliku bacpac za pomocą narzędzia SQLPackage.exe. Ten krok powinno zostać wykonany przez administratora baz danych lub członka zespołu posiadającego analogiczną wiedzę.

Bardzo ważne jest, aby przed rozpoczęciem tego kroku zainstalować najnowszą wersję programu SQL Server Management Studio. Chociaż narzędzie SQLPackage jest obecne we wcześniejszych wersjach programu Management Studio, nie będzie działało poprawnie w tym kroku, jeśli najpierw nie zainstalujesz najnowszej wersji.

Ten krok jest ważny, ponieważ eksport trzeba będzie wykonać ponownie podczas przestoju przed rozpoczęciem eksploatacji. Oto kilka porad:

- Proces bacpac bardzo intensywnie wykorzystuje interfejsy we/wy i procesor CPU. Z tego względu eksport należy uruchomić na komputerze o dużej mocy.
- Narzędzie SQLPackage należy uruchomić lokalnie na komputerze zawierającym bazę danych. Nie uruchamiaj narzędzia SQLPackage na lokalnym komputerze przenośnym podłączonym do komputera z bazą danych, ponieważ ten proces także intensywnie obciąża sieć.

Następnie otwórz okno **Wiersz polecenia** jako administrator i uruchom następujące polecenia.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:export /ssn:localhost /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false

Poniżej znajduje się wyjaśnienie parametrów:

- **ssn** (nazwa serwera źródłowego) — Nazwa serwera SQL Server, z którego zostanie wykonany eksport. W naszym procesie w tym parametrze zawsze należy ustawić wartość **localhost**.
- **sdn** (nazwa źródłowej bazy danych) — Nazwa bazy danych do wyeksportowania.
- **tf** (plik docelowy) — Ścieżka i nazwa pliku, do którego ma zostać wykonany eksport. Folder powinien już istnieć, ale plik zostanie utworzony przez proces.
- **/p:CommandTimeout** — Wartość limitu czasu dla konkretnego zapytania. Ten parametr umożliwia eksportowanie większych tabel bez przekroczenie limitu czasu.

### Przekazanie pliku bacpac do magazynu Azure
<a id="upload-the-bacpac-file-to-azure-storage" class="xliff"></a>

Przekazanie pliku bacpac do magazynu Azure. Zobacz temat UsingStorageExplorer.docx TODO

### Importowanie pliku bacpac do systemu bazodanowego SQL Database
<a id="import-the-bacpac-file-into-sql-database" class="xliff"></a>

W tym kroku zaimportujesz wyeksportowany plik bacpac do wystąpienia programu SQL Database używanego przez środowisko piaskownicy. Najpierw należy zainstalować najnowszą wersję programu Management Studio na komputerze serwera AOS w środowisku piaskownicy. Następnie zaimportujesz plik za pomocą narzędzia SQLPackage.exe.

Wykonasz te zadania bezpośrednio na komputerze serwera AOS w swoim środowisku piaskownicy, ponieważ istnieją reguły zapory ograniczające dostęp do wystąpienia programu SQL Database. Jednak komputer serwera AOS umożliwia konieczny dostęp.

Podobnie jak z etapem eksportu, przed rozpoczęciem importu musisz mieć najnowszą wersję programu Management Studio. Ten krok nie będzie działał, jeśli masz starszą wersję.

Ze względu na wydajność zalecamy umieszczenie pliku bacpac na dysku D na komputerze serwera AOS. Na maszynach wirtualnych w chmurze Azure dysk D to dysk fizyczny, który zwykle działa szybciej niż inne dostępne dyski.

Otwórz okno **Wiersz polecenia** jako administrator i uruchom następujące polecenia.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:<azure sql database server name>.database.windows.net /tu:sqladmin /tp:<password from LCS> /tdn:<New database name> /p:CommandTimeout=1200 /p:DatabaseEdition=Premium /p:DatabaseServiceObjective=P1

Poniżej znajduje się wyjaśnienie parametrów:

- **tsn** (nazwa serwera docelowego) — Nazwa serwera w usłudze SQL Azure, do którego nastąpi import. Można ją znaleźć w usłudze LCS. Do nazwy dodaj sufiks **.database.windows.net**.
- **tdn** (nazwa docelowej bazy danych) — Nazwa bazy danych, do której nastąpi import. Ta baza danych nie powinna jeszcze istnieć. Proces importu ją utworzy.
- **sf** (plik źródłowy) — Ścieżka i nazwa pliku, z którego ma zostać wykonany import.
- **tp** (hasło docelowej bazy) — Hasło SQL do docelowego wystąpienia programu SQL Database.
- **tu** (docelowy użytkownik) — Nazwa użytkownika SQL dla docelowego wystąpienia programu SQL Database. Zalecamy użycie nazwy **sqladmin**. Hasło tego użytkownika można pobrać z projektu w usłudze LCS.
- **/p:CommandTimeout** — Wartość limitu czasu dla konkretnego zapytania. Ten parametr umożliwia eksportowanie większych tabel bez przekroczenie limitu czasu.
- **/p:DatabaseServiceObjective** — Warstwa usług dla tworzonej bazy danych. Wartość dla istniejącej bazy danych można sprawdzić za pomocą programu Management Studio. Kliknij bazę danych prawym przyciskiem myszy i wybierz polecenie **Właściwości**.

Po wykonaniu wszystkich poleceń zostanie wyświetlone następujące ostrzeżenie. Możesz je zignorować.

![Błąd piaskownicy](./media/sandbox-2.png)
 
### Uruchamianie pakietu MajorVersionDataUpgrade.zip
<a id="run-the-majorversiondataupgradezip-package" class="xliff"></a>

Uruchom wdrażalny pakiet uaktualniania danych w sposób opisany w temacie [Uaktualnianie danych w środowisku projektowym, demonstracyjnym lub piaskownicy](upgrade-data-to-latest-update.md).

### Uaktualnianie kopii bazy danych w środowisku projektowym
<a id="upgrade-a-copy-of-the-database-in-a-development-environment" class="xliff"></a>

Warto uaktualnić tę samą bazę danych w środowisku projektowym. Jeśli masz kopię bazy danych dostępną dla środowiska projektowego, będzie znacznie łatwiej badać usterki wykryte w uaktualnionym środowisku piaskownicy.


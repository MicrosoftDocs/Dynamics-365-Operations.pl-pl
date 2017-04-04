---
title: "Resetuj sprawozdawczości finansowej składnicy danych po przywróceniu bazy danych"
description: "W tym temacie opisano jak zresetować sprawozdawczości finansowej składnicy danych po przywróceniu usługi Microsoft Dynamics 365 dla operacji bazy danych."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-08 16 - 20 - 13
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3967cbb869fbb23d5d7716f619e4c22b4a273921
ms.lasthandoff: 03/29/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Resetuj sprawozdawczości finansowej składnicy danych po przywróceniu bazy danych

W tym temacie opisano jak zresetować sprawozdawczości finansowej składnicy danych po przywróceniu usługi Microsoft Dynamics 365 dla operacji bazy danych. 

Istnieje kilka scenariuszy, w których konieczne może być przywrócenie swój 365 Dynamics dla operacji bazy danych z kopii zapasowej lub skopiować bazę danych z innego środowiska. W takiej sytuacji należy wykonać odpowiednie kroki dla zapewnienia, że składnicy danych raportowania finansowego poprawnie używa przywróconych 365 Dynamics dla operacji bazy danych. Jeśli masz pytania dotyczące zerowania składnicy danych raportowania finansowego z powodu poza 365 Dynamics dla bazy danych operacji przywracania, odnoszą się do [Resetowanie składnicy danych Management Reporter](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) uzyskać więcej informacji. Etapy tego procesu są obsługiwane dla usługi Dynamics 365 dla operacji wydanie maja 2016 (kompilacji aplikacji 7.0.1265.23014 i build raportowania finansowego 7.0.10000.4) oraz nowszych wersji. Jeśli masz wcześniejszą wersją usługi Dynamics 365 dla operacji, skontaktuj się działem pomocy technicznej o pomoc.

## <a name="export-report-definitions"></a>Eksportowanie definicji raportu
Najpierw wyeksportuj wzory raportów znajdujących się w Projektant raportów, wykonując następujące czynności:

1.  W Projektancie raportów, przejdź do **firmy**&gt;**blok konstrukcyjny grup**.
2.  Wybierz grupę blok konstrukcyjny do wyeksportowania, a następnie kliknij przycisk **wyeksportować**. **Uwaga:** Dynamics 365 dla operacji, obsługiwane są tylko jeden blok konstrukcyjny grupy, **domyślne**.
3.  Wybierz definicje raportów do wyeksportowania:
    -   Aby wyeksportować wszystkie definicje raportów i powiązane bloki konstrukcyjne, kliknij **Zaznacz wszystko**.
    -   Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, kliknij odpowiednią kartę i wybierz elementy do wyeksportowania. Naciśnij i przytrzymaj klawisz Ctrl, aby wybrać wiele elementów na karcie. Po wybraniu raportów do wyeksportowania skojarzonych wierszy, kolumn, drzew i zestawów wymiarów są zaznaczone.

4.  Kliknij **wyeksportować**.
5.  Wprowadź nazwę pliku i wybierz bezpiecznej lokalizacji, w której chcesz zapisać wyeksportowany raport definicje.
6.  Click **Save**.

Plik można skopiowany lub przesłane w bezpiecznej lokalizacji, dzięki czemu mają być zaimportowane do innego środowiska w innym czasie. Informacje dotyczące korzystania z konta magazynu Microsoft Azure znajdują się w [transferu danych za pomocą narzędzia wiersza polecenia AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). **Uwaga:** firma Microsoft nie zapewnia konto magazynu jako część sieci 365 Dynamics dla operacji umowy. Należy zakupić konto magazynu lub użyć konta magazynu z oddzielnych subskrypcji Azure. **Ważne:** należy pamiętać o zachowanie dysku D na maszynach wirtualnych Azure. Nie przechowuj grup programu eksportowanych blok konstrukcyjny trwale. Aby uzyskać więcej informacji o dyskach tymczasowych, zobacz [opis dysku tymczasowego na maszynach wirtualnych systemu Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Zatrzymaj usługi
Aby podłączyć się do komputerów w środowisku i zatrzymać następujące usługi systemu Windows przy użyciu services.msc korzystania z pulpitu zdalnego:

-   Publikowanie usługi (na wszystkich komputerach usługi AOS) sieci world wide web
-   Microsoft Dynamics 365 dla operacji usługi zarządzania partii (-prywatny serwer AOS tylko na komputerach)
-   Usługa proces Management Reporter 2012 (BI tylko na komputerach)

Usługi te mają otwarte połączenia 365 Dynamics dla operacji bazy danych.

## <a name="reset"></a>Zeruj
#### <a name="locate-the-latest-dataupgradezip-package"></a>Zlokalizuj najnowszy pakiet DataUpgrade.zip

Zlokalizuj najnowszy pakiet DataUpgrade.zip użyciu wskazówek: znaleziono [Pobierz skrypt DataUpgrade.zip](..\migration-upgrade\upgrade-data-to-latest-update.md). Instrukcje wyjaśniają jak zlokalizuj poprawną wersję danych pakiet uaktualniający dla danego środowiska.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Wykonywanie skryptów przeciwko Dynamics 365 dla operacji bazy danych

Uruchom następujące skrypty przeciwko 365 Dynamics dla operacji bazy danych (nie w bazie danych finansowych raportowania).

-   DataUpgrade.zip\\AosService\\skrypty\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\skrypty\\GrantAzViewChangeTracking.sql

Te skrypty upewnij się, czy użytkownicy, role i ustawienia oledzenia są poprawne.

#### <a name="execute-powershell-command-to-reset-database"></a>Wykonanie polecenia środowiska PowerShell, aby przywrócić bazę danych

Wydaj następujące polecenie, bezpośrednio na komputerze serwera AOS, aby zresetować integrację systemu Dynamics 365 dla operacji i sprawozdawczości finansowej:

1.  Otwórz środowisko Windows PowerShell jako Administrator.
2.  Wykonanie: F:
3.  Wykonanie: cd F:\\MRApplicationService\\MRInstallDirectory
4.  Wykonanie: Import-Module. \\Serwera\\MRDeploy\\MRDeploy.psd1
5.  Wykonanie: Reset-DatamartIntegration-inne przyczyny - ReasonDetail "&lt;Moje zresetowanie powodu&gt;"
    -   Będzie musiał wprowadzić "Y", aby potwierdzić.

Opis parametrów:

-   Prawidłowe wartości dla - przyczyny to: Obsługa, BADDATA, inne.
-   Parametr - ReasonDetail jest niezależnych.
-   Przyczyna i reasonDetail będą rejestrowane w monitorowaniu telemetrycznego i/lub środowiska.

## <a name="start-services"></a>Uruchom usługi
Umożliwia ponowne uruchomienie usługi, które zostało wcześniej przerwane services.msc:

-   Publikowanie usługi (na wszystkich komputerach usługi AOS) sieci world wide web
-   Microsoft Dynamics 365 dla operacji usługi zarządzania partii (-prywatny serwer AOS tylko na komputerach)
-   Usługa proces Management Reporter 2012 (BI tylko na komputerach)

## <a name="import-report-definitions"></a>Importowanie definicji raportu
Importowanie projektów raportu z Projektant raportów, używany jest plik tworzony podczas eksportowania:

1.  W Projektancie raportów, przejdź do **firmy**&gt;**blok konstrukcyjny grup**.
2.  Wybierz grupę blok konstrukcyjny do wyeksportowania, a następnie kliknij przycisk **wyeksportować**. **Uwaga:** Dynamics 365 dla operacji, obsługiwane są tylko jeden blok konstrukcyjny grupy, **domyślne**.
3.  Wybierz **domyślne** budynku i kliknij **importowania**.
4.  Wybierz plik zawierający definicje wyeksportowany raport i kliknij przycisk **Otwórz**.
5.  W oknie dialogowym Importowanie wybierz definicje raportów do zaimportowania:
    -   Aby zaimportować wszystkie definicje raportów i wspierające je bloki konstrukcyjne, kliknij opcję **Zaznacz wszystko**.
    -   Aby zaimportować konkretne raporty, wiersze, kolumny lub zestawy wymiarów, wybierz raporty, wiersze, kolumny, drzewa lub zestawy wymiarów do zaimportowania.

6.  Click **Import**.




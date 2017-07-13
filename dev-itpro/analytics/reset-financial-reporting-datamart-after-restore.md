---
title: "Resetowanie składnicy danych modułu raportowania finansowego po przywróceniu bazy danych"
description: "W tym temacie opisano, jak zresetować składnicę danych modułu raportowania finansowego po przywróceniu bazy danych programu Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: c132c04bc64f02201252f03830d3f8309306f19c
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Resetowanie składnicy danych modułu raportowania finansowego po przywróceniu bazy danych
<a id="reset-the-financial-reporting-data-mart-after-restoring-a-database" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym temacie opisano, jak zresetować składnicę danych modułu raportowania finansowego po przywróceniu bazy danych programu Microsoft Dynamics 365 for Finance and Operations. 

Istnieje kilka scenariuszy, w których może być konieczne przywrócenie bazy danych programu Finance and Operations z kopii zapasowej albo skopiowanie bazy danych z innego środowiska. W takiej sytuacji należy też wykonać odpowiednie kroki w celu zapewnienia, że składnica danych raportowania finansowego poprawnie używa przywróconej bazy danych programu Finance and Operations. Jeśli masz pytania dotyczące resetowania składnicy danych raportowania finansowego z powodów innych niż przywrócenie bazy danych programu Finance and Operations, więcej informacji znajdziesz w temacie [Resetowanie składnicy danych programu Management Reporter](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/). Należy zauważyć, że etapy tego procesu są obsługiwane dla programu Dynamics 365 for Operations w wydaniu z maja 2016 r. (kompilacja aplikacja 7.0.1265.23014 i kompilacja modułu raportowania finansowego 7.0.10000.4) oraz nowszych wydań. Jeśli masz wcześniejszą wersję programu Finance and Operations, poproś o pomoc nasz dział pomocy technicznej.

## Eksportowanie definicji raportów
<a id="export-report-definitions" class="xliff"></a>
Najpierw wyeksportuj projekty raportów znajdujące się w projektancie raportów, wykonując następujące czynności:

1.  W Projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.
2.  Wybierz grupę blok konstrukcyjny do wyeksportowania, a następnie kliknij przycisk **Eksportuj**. **Uwaga:** W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.
3.  Wybierz definicje raportów do wyeksportowania:
    -   Aby wyeksportować wszystkie definicje raportów i powiązane bloki konstrukcyjne, kliknij **Zaznacz wszystko**.
    -   Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, kliknij odpowiednią kartę i wybierz elementy do wyeksportowania. Naciśnij i przytrzymaj klawisz Ctrl, aby wybrać wiele elementów na karcie. Podczas zaznaczania raportów do wyeksportowania zaznaczane są skojarzone wiersze, kolumny, drzewa i zestawy wymiarów.

4.  Kliknij przycisk **Eksportuj**.
5.  Wprowadź nazwę pliku i wybierz bezpieczną lokalizację, w której chcesz zapisać wyeksportowane definicje raportów.
6.  Kliknij przycisk **Zapisz**.

Plik można skopiować lub przekazać do bezpiecznej lokalizacji, dzięki czemu będzie go można później zaimportować do innego środowiska. Informacje dotyczące korzystania z konta magazynu usługi Microsoft Azure znajdują się w temacie [Przenoszenie danych za pomocą narzędzia wiersza polecenia AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). 
> [!NOTE]
> Firma Microsoft nie zapewnia konta magazynu w ramach umowy na usługę Finance and Operations. Należy we własnym zakresie kupić konto magazynu lub użyć konta magazynu z oddzielnej subskrypcji usługi Azure. 
> [!WARNING]
> Należy pamiętać o zachowaniu dysku D na maszynach wirtualnych Azure. Nie przechowuj na nim trwale wyeksportowanych grup bloków konstrukcyjnych. Aby uzyskać więcej informacji o dyskach tymczasowych, zobacz [Opis koncepcji dysku tymczasowego na maszynach wirtualnych systemu Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## Zatrzymywanie usług
<a id="stop-services" class="xliff"></a>
Za pomocą narzędzia Pulpit zdalny połącz się z komputerami w środowisku i zatrzymaj następujące usługi systemu Windows przy użyciu konsoli services.msc:

-   Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)
-   Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)
-   Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)

Te usługi mają otwarte połączenia z bazą danych programu Finance and Operations.

## Zeruj
<a id="reset" class="xliff"></a>
#### Znajdowanie najnowszego pakietu DataUpgrade.zip
<a id="locate-the-latest-dataupgradezip-package" class="xliff"></a>

Odszukaj najnowszy pakiet DataUpgrade.zip przy użyciu instrukcji podanych w temacie [Pobieranie pliku skryptu DataUpgrade.zip](..\migration-upgrade\upgrade-data-to-latest-update.md). Instrukcje wyjaśniają, jak znaleźć poprawną wersję pakietu uaktualnienia danych dla używanego środowiska.

#### Wykonywanie skryptów w bazie danych programu Finance and Operations
<a id="execute-scripts-against-finance-and-operations-database" class="xliff"></a>

Uruchom następujące skrypty w bazie danych programu Finance and Operations (nie w bazie danych modułu raportowania finansowego).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Te skrypty zagwarantują, że użytkownicy, role i ustawienia śledzenia zmian są poprawne.

#### Wykonywanie poleceń narzędzia PowerShell w celu przywrócenia bazy danych
<a id="execute-powershell-command-to-reset-database" class="xliff"></a>

Wykonaj następujące polecenie bezpośrednio na komputerze serwera AOS, aby zresetować integrację między programem Finance and Operations a modułem raportowania finansowego:

1.  Otwórz narzędzie Windows PowerShell jako administrator.
2.  Wykonaj: F:
3.  Wykonaj: cd F:\\MRApplicationService\\MRInstallDirectory
4.  Wykonaj: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1
5.  Wykonaj: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;mój powód resetowania&gt;”
    -   Będzie trzeba nacisnąć klawisz „Y”, aby potwierdzić.

Wyjaśnienie parametrów:

-   Prawidłowe wartości parametru -Reason to: SERVICING, BADDATA, OTHER.
-   Parametr -ReasonDetail ma format zwykłego tekstu.
-   Wartości parametrów Reason i ReasonDetail zostaną zarejestrowane w funkcji telemetrii/monitorowania środowiska.

## Uruchamianie usług
<a id="start-services" class="xliff"></a>
Za pomocą konsoli services.msc uruchom usługi, które zostały wcześniej zatrzymane:

-   Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)
-   Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)
-   Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)

## Importowanie definicji raportów
<a id="import-report-definitions" class="xliff"></a>
Zaimportuj projekty raportów z projektanta raportów, używając pliku utworzony podczas eksportu:

1.  W Projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.
2.  Wybierz grupę blok konstrukcyjny do wyeksportowania, a następnie kliknij przycisk **Eksportuj**. 
    > [!NOTE]
    > W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.
3.  Zaznacz blok konstrukcyjny **Domyślne** i kliknij przycisk **Importuj**.
4.  Zaznacz plik zawierający wyeksportowane definicje raportów i kliknij przycisk **Otwórz**.
5.  W oknie dialogowym Importowanie wybierz definicje raportów do zaimportowania:
    -   Aby zaimportować wszystkie definicje raportów i wspierające je bloki konstrukcyjne, kliknij opcję **Zaznacz wszystko**.
    -   Aby zaimportować konkretne raporty, wiersze, kolumny lub zestawy wymiarów, wybierz raporty, wiersze, kolumny, drzewa lub zestawy wymiarów do zaimportowania.

6.  Kliknij przycisk **Importuj**.






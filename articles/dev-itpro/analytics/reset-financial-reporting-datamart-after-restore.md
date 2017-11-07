---
title: "Resetowanie składnicy danych modułu raportowania finansowego po przywróceniu bazy danych"
description: "W tym temacie opisano, jak zresetować składnicę danych modułu raportowania finansowego po przywróceniu bazy danych programu Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 200b1a03a0ea95ec2d75850f9a8aebda966e38d6
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Resetowanie składnicy danych modułu raportowania finansowego po przywróceniu bazy danych

[!include[banner](../includes/banner.md)]


W tym temacie opisano, jak zresetować składnicę danych modułu raportowania finansowego po przywróceniu bazy danych programu Microsoft Dynamics 365 for Finance and Operations.

Jeśli kiedykolwiek będziesz przywracać bazę danych programu Finance and Operations z kopii zapasowej albo kopiować bazę danych z innego środowiska, należy wykonać kroki opisane w tym temacie w celu zapewnienia, że składnica danych raportowania finansowego poprawnie używa przywróconej bazy danych programu Finance and Operations. 
> [!Note] 
> Etapy tego procesu są obsługiwane dla programu Dynamics 365 for Operations w wydaniu z maja 2016 r. (kompilacja aplikacja 7.0.1265.23014 i kompilacja modułu raportowania finansowego 7.0.10000.4) oraz nowszych wydań. Jeśli masz wcześniejszą wersję programu Finance and Operations, poproś o pomoc nasz dział pomocy technicznej.

## <a name="export-report-definitions"></a>Eksportowanie definicji raportów
Najpierw wyeksportuj projekty raportów znajdujące się w projektancie raportów, wykonując następujące czynności:

1.  W Projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.
2.  Wybierz grupę blok konstrukcyjny do wyeksportowania, a następnie kliknij przycisk **Eksportuj**. 

    > [!Note] 
    > W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.
    
3.  Wybierz definicje raportów do wyeksportowania:
    -   Aby wyeksportować wszystkie definicje raportów i powiązane bloki konstrukcyjne, kliknij **Zaznacz wszystko**.
    -   Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, kliknij odpowiednią kartę i wybierz elementy do wyeksportowania. Naciśnij i przytrzymaj klawisz Ctrl, aby zaznaczyć kilka elementów na karcie. Po wybraniu raportów do wyeksportowania zostaną wybrane skojarzone wiersze, kolumny, drzewa i zestawy wymiarów.

4.  Kliknij przycisk **Eksportuj**.
5.  Wprowadź nazwę pliku i wybierz bezpieczną lokalizację, w której chcesz zapisać wyeksportowane definicje raportów.
6.  Kliknij przycisk **Zapisz**.

Plik można skopiować lub przekazać do bezpiecznej lokalizacji, dzięki czemu będzie go można później zaimportować do innego środowiska. Informacje dotyczące korzystania z konta magazynu usługi Microsoft Azure znajdują się w temacie [Przenoszenie danych za pomocą narzędzia wiersza polecenia AzCopy](/azure/storage/storage-use-azcopy). 
> [!NOTE]
> Firma Microsoft nie zapewnia konta magazynu w ramach umowy na usługę Finance and Operations. Należy we własnym zakresie kupić konto magazynu lub użyć konta magazynu z oddzielnej subskrypcji usługi Azure. 
> [!WARNING]
> Należy pamiętać o zachowaniu dysku D na maszynach wirtualnych Azure. Nie przechowuj na nim trwale wyeksportowanych grup bloków konstrukcyjnych. Aby uzyskać więcej informacji o dyskach tymczasowych, zobacz [Opis koncepcji dysku tymczasowego na maszynach wirtualnych systemu Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Zatrzymywanie usług
Za pomocą narzędzia Pulpit zdalny połącz się z komputerami w środowisku i zatrzymaj następujące usługi systemu Windows przy użyciu konsoli services.msc:

-   Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)
-   Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)
-   Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)

Te usługi mają otwarte połączenia z bazą danych programu Finance and Operations.

## <a name="reset"></a>Zeruj
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a>Znajdowanie i pobieranie najnowszego pakietu MinorVersionDataUpgrade.zip

Odszukaj najnowszy pakiet MinorVersionDataUpgrade.zip przy użyciu instrukcji podanych w temacie [Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Instrukcje wyjaśniają, jak znaleźć i pobrać poprawną wersję pakietu uaktualnienia danych. Uaktualnienie nie jest wymagane w celu pobrania pakietu MinorVersionDataUpgrade.zip. Aby pobrać kopię pakietu MinorVersionDataUpgrade.zip, należy tylko wykonać kroki opisane w sekcji „Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych”, bez wykonywania żadnych innych czynności opisanych w tym artykule.

### <a name="execute-scripts-against-finance-and-operations-database"></a>Wykonywanie skryptów w bazie danych programu Finance and Operations

Uruchom następujące skrypty w bazie danych programu Finance and Operations (nie w bazie danych modułu raportowania finansowego).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Te skrypty zagwarantują, że użytkownicy, role i ustawienia śledzenia zmian są poprawne.

### <a name="execute-powershell-command-to-reset-database"></a>Wykonywanie poleceń narzędzia PowerShell w celu przywrócenia bazy danych

Na komputerze serwera AOS wykonaj następujące polecenia w programie PowerShell jako administrator, aby zresetować integrację między programem Finance and Operations a modułem raportowania finansowego:

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> Po wykonaniu poleceń będzie trzeba nacisnąć klawisz „Y”, aby potwierdzić.

Wyjaśnienie parametrów:

-   Prawidłowe wartości parametru -Reason to: SERVICING, BADDATA, OTHER.
-   Parametr -ReasonDetail ma format zwykłego tekstu.
-   Wartości parametrów Reason i ReasonDetail zostaną zarejestrowane w funkcji telemetrii/monitorowania środowiska.

## <a name="start-services"></a>Uruchamianie usług
Za pomocą konsoli services.msc uruchom usługi, które zostały wcześniej zatrzymane:

-   Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)
-   Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)
-   Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)

## <a name="import-report-definitions"></a>Importowanie definicji raportów
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






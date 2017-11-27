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
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e3f78fb2f6528449d2a411225cd0e14ca33443e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="58663-103">Resetowanie składnicy danych modułu raportowania finansowego po przywróceniu bazy danych</span><span class="sxs-lookup"><span data-stu-id="58663-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="58663-104">W tym temacie opisano, jak zresetować składnicę danych modułu raportowania finansowego po przywróceniu bazy danych programu Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58663-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="58663-105">Jeśli kiedykolwiek będziesz przywracać bazę danych programu Finance and Operations z kopii zapasowej albo kopiować bazę danych z innego środowiska, należy wykonać kroki opisane w tym temacie w celu zapewnienia, że składnica danych raportowania finansowego poprawnie używa przywróconej bazy danych programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58663-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
> [!Note] 
> <span data-ttu-id="58663-106">Etapy tego procesu są obsługiwane dla programu Dynamics 365 for Operations w wydaniu z maja 2016 r. (kompilacja aplikacja 7.0.1265.23014 i kompilacja modułu raportowania finansowego 7.0.10000.4) oraz nowszych wydań.</span><span class="sxs-lookup"><span data-stu-id="58663-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="58663-107">Jeśli masz wcześniejszą wersję programu Finance and Operations, poproś o pomoc nasz dział pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="58663-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="58663-108">Eksportowanie definicji raportów</span><span class="sxs-lookup"><span data-stu-id="58663-108">Export report definitions</span></span>
<span data-ttu-id="58663-109">Najpierw wyeksportuj projekty raportów znajdujące się w projektancie raportów, wykonując następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="58663-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="58663-110">W Projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.</span><span class="sxs-lookup"><span data-stu-id="58663-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="58663-111">Wybierz grupę blok konstrukcyjny do wyeksportowania, a następnie kliknij przycisk **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="58663-111">Select the building block group to export, and click **Export**.</span></span> 

    > [!Note] 
    > <span data-ttu-id="58663-112">W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.</span><span class="sxs-lookup"><span data-stu-id="58663-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="58663-113">Wybierz definicje raportów do wyeksportowania:</span><span class="sxs-lookup"><span data-stu-id="58663-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="58663-114">Aby wyeksportować wszystkie definicje raportów i powiązane bloki konstrukcyjne, kliknij **Zaznacz wszystko**.</span><span class="sxs-lookup"><span data-stu-id="58663-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="58663-115">Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, kliknij odpowiednią kartę i wybierz elementy do wyeksportowania.</span><span class="sxs-lookup"><span data-stu-id="58663-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="58663-116">Naciśnij i przytrzymaj klawisz Ctrl, aby zaznaczyć kilka elementów na karcie. Po wybraniu raportów do wyeksportowania zostaną wybrane skojarzone wiersze, kolumny, drzewa i zestawy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="58663-116">Press and hold the Ctrl key to select multiple items in a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="58663-117">Kliknij przycisk **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="58663-117">Click **Export**.</span></span>
5.  <span data-ttu-id="58663-118">Wprowadź nazwę pliku i wybierz bezpieczną lokalizację, w której chcesz zapisać wyeksportowane definicje raportów.</span><span class="sxs-lookup"><span data-stu-id="58663-118">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="58663-119">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="58663-119">Click **Save**.</span></span>

<span data-ttu-id="58663-120">Plik można skopiować lub przekazać do bezpiecznej lokalizacji, dzięki czemu będzie go można później zaimportować do innego środowiska.</span><span class="sxs-lookup"><span data-stu-id="58663-120">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="58663-121">Informacje dotyczące korzystania z konta magazynu usługi Microsoft Azure znajdują się w temacie [Przenoszenie danych za pomocą narzędzia wiersza polecenia AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="58663-121">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="58663-122">Firma Microsoft nie zapewnia konta magazynu w ramach umowy na usługę Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58663-122">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="58663-123">Należy we własnym zakresie kupić konto magazynu lub użyć konta magazynu z oddzielnej subskrypcji usługi Azure.</span><span class="sxs-lookup"><span data-stu-id="58663-123">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="58663-124">Należy pamiętać o zachowaniu dysku D na maszynach wirtualnych Azure.</span><span class="sxs-lookup"><span data-stu-id="58663-124">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="58663-125">Nie przechowuj na nim trwale wyeksportowanych grup bloków konstrukcyjnych.</span><span class="sxs-lookup"><span data-stu-id="58663-125">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="58663-126">Aby uzyskać więcej informacji o dyskach tymczasowych, zobacz [Opis koncepcji dysku tymczasowego na maszynach wirtualnych systemu Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="58663-126">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="58663-127">Zatrzymywanie usług</span><span class="sxs-lookup"><span data-stu-id="58663-127">Stop services</span></span>
<span data-ttu-id="58663-128">Za pomocą narzędzia Pulpit zdalny połącz się z komputerami w środowisku i zatrzymaj następujące usługi systemu Windows przy użyciu konsoli services.msc:</span><span class="sxs-lookup"><span data-stu-id="58663-128">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="58663-129">Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)</span><span class="sxs-lookup"><span data-stu-id="58663-129">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="58663-130">Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)</span><span class="sxs-lookup"><span data-stu-id="58663-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="58663-131">Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)</span><span class="sxs-lookup"><span data-stu-id="58663-131">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="58663-132">Te usługi mają otwarte połączenia z bazą danych programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58663-132">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="58663-133">Zeruj</span><span class="sxs-lookup"><span data-stu-id="58663-133">Reset</span></span>
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="58663-134">Znajdowanie i pobieranie najnowszego pakietu MinorVersionDataUpgrade.zip</span><span class="sxs-lookup"><span data-stu-id="58663-134">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="58663-135">Odszukaj najnowszy pakiet MinorVersionDataUpgrade.zip przy użyciu instrukcji podanych w temacie [Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="58663-135">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="58663-136">Instrukcje wyjaśniają, jak znaleźć i pobrać poprawną wersję pakietu uaktualnienia danych.</span><span class="sxs-lookup"><span data-stu-id="58663-136">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="58663-137">Uaktualnienie nie jest wymagane w celu pobrania pakietu MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="58663-137">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="58663-138">Aby pobrać kopię pakietu MinorVersionDataUpgrade.zip, należy tylko wykonać kroki opisane w sekcji „Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych”, bez wykonywania żadnych innych czynności opisanych w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="58663-138">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="58663-139">Wykonywanie skryptów w bazie danych programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58663-139">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="58663-140">Uruchom następujące skrypty w bazie danych programu Finance and Operations (nie w bazie danych modułu raportowania finansowego).</span><span class="sxs-lookup"><span data-stu-id="58663-140">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="58663-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="58663-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="58663-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="58663-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="58663-143">Te skrypty zagwarantują, że użytkownicy, role i ustawienia śledzenia zmian są poprawne.</span><span class="sxs-lookup"><span data-stu-id="58663-143">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="58663-144">Wykonywanie poleceń narzędzia PowerShell w celu przywrócenia bazy danych</span><span class="sxs-lookup"><span data-stu-id="58663-144">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="58663-145">Na komputerze serwera AOS wykonaj następujące polecenia w programie PowerShell jako administrator, aby zresetować integrację między programem Finance and Operations a modułem raportowania finansowego:</span><span class="sxs-lookup"><span data-stu-id="58663-145">On the AOS computer, execute the following commands in PowerShell as an Administrator to reset the integration between Finance and Operations and financial reporting:</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> <span data-ttu-id="58663-146">Po wykonaniu poleceń będzie trzeba nacisnąć klawisz „Y”, aby potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="58663-146">After executing the commands, you will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="58663-147">Wyjaśnienie parametrów:</span><span class="sxs-lookup"><span data-stu-id="58663-147">Explanation of parameters:</span></span>

-   <span data-ttu-id="58663-148">Prawidłowe wartości parametru -Reason to: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="58663-148">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="58663-149">Parametr -ReasonDetail ma format zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="58663-149">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="58663-150">Wartości parametrów Reason i ReasonDetail zostaną zarejestrowane w funkcji telemetrii/monitorowania środowiska.</span><span class="sxs-lookup"><span data-stu-id="58663-150">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="58663-151">Uruchamianie usług</span><span class="sxs-lookup"><span data-stu-id="58663-151">Start services</span></span>
<span data-ttu-id="58663-152">Za pomocą konsoli services.msc uruchom usługi, które zostały wcześniej zatrzymane:</span><span class="sxs-lookup"><span data-stu-id="58663-152">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="58663-153">Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)</span><span class="sxs-lookup"><span data-stu-id="58663-153">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="58663-154">Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)</span><span class="sxs-lookup"><span data-stu-id="58663-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="58663-155">Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)</span><span class="sxs-lookup"><span data-stu-id="58663-155">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="58663-156">Importowanie definicji raportów</span><span class="sxs-lookup"><span data-stu-id="58663-156">Import report definitions</span></span>
<span data-ttu-id="58663-157">Zaimportuj projekty raportów z projektanta raportów, używając pliku utworzony podczas eksportu:</span><span class="sxs-lookup"><span data-stu-id="58663-157">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="58663-158">W Projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.</span><span class="sxs-lookup"><span data-stu-id="58663-158">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="58663-159">Wybierz grupę blok konstrukcyjny do wyeksportowania, a następnie kliknij przycisk **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="58663-159">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="58663-160">W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.</span><span class="sxs-lookup"><span data-stu-id="58663-160">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="58663-161">Zaznacz blok konstrukcyjny **Domyślne** i kliknij przycisk **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="58663-161">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="58663-162">Zaznacz plik zawierający wyeksportowane definicje raportów i kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="58663-162">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="58663-163">W oknie dialogowym Importowanie wybierz definicje raportów do zaimportowania:</span><span class="sxs-lookup"><span data-stu-id="58663-163">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="58663-164">Aby zaimportować wszystkie definicje raportów i wspierające je bloki konstrukcyjne, kliknij opcję **Zaznacz wszystko**.</span><span class="sxs-lookup"><span data-stu-id="58663-164">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="58663-165">Aby zaimportować konkretne raporty, wiersze, kolumny lub zestawy wymiarów, wybierz raporty, wiersze, kolumny, drzewa lub zestawy wymiarów do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="58663-165">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="58663-166">Kliknij przycisk **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="58663-166">Click **Import**.</span></span>






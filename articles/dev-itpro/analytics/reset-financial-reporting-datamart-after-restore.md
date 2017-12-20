---
title: "Resetowanie składników danych aplikacji Raportowanie finansowe"
description: "W tym temacie opisano sposób resetowania składnicy danych modułu Raporty finansowe."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: pl-pl
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a><span data-ttu-id="39914-103">Resetowanie składników danych aplikacji Raportowanie finansowe</span><span class="sxs-lookup"><span data-stu-id="39914-103">Reset the Financial reporting data mart</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="39914-104">W tym temacie objaśniono, w jaki sposób zresetować składnicę danych modułu Raporty finansowe w następujących wersjach:</span><span class="sxs-lookup"><span data-stu-id="39914-104">This topic explains how to reset the Financial reporting data mart for the following versions:</span></span>

- <span data-ttu-id="39914-105">Microsoft Dynamics 365 for Finance and Operations — Raporty finansowe, wersja 7.2.6.0 lub nowsza</span><span class="sxs-lookup"><span data-stu-id="39914-105">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>
- <span data-ttu-id="39914-106">Microsoft Dynamics 365 for Finance and Operations — Raporty finansowe, wersja 7.0.10000.4 lub nowsza</span><span class="sxs-lookup"><span data-stu-id="39914-106">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>
- <span data-ttu-id="39914-107">Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (wersja lokalna)</span><span class="sxs-lookup"><span data-stu-id="39914-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises)</span></span>

<span data-ttu-id="39914-108">Wersję 7.2.6.0 modułu Raporty finansowe oprogramowania Finance and Operations można uzyskać, pobierając plik KB 4052514 ze strony <https://support.microsoft.com/en-us/help/4052514>.</span><span class="sxs-lookup"><span data-stu-id="39914-108">To get Finance and Operations Financial reporting release 7.2.6.0, you can download KB 4052514 from <https://support.microsoft.com/en-us/help/4052514>.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a><span data-ttu-id="39914-109">Resetowanie składnicy danych modułu Raporty finansowe w wersji 7.2.6.0 oprogramowania Finance and Operations lub nowszej</span><span class="sxs-lookup"><span data-stu-id="39914-109">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a><span data-ttu-id="39914-110">Resetuj składnicy danych modułu Raporty finansowe z poziomu projektanta raportów</span><span class="sxs-lookup"><span data-stu-id="39914-110">Reset the Financial reporting data mart from Report designer</span></span>

> [!NOTE]
> <span data-ttu-id="39914-111">Kroki tej procedury dotyczą wyłącznie modułu Raporty finansowe w wersji 7.2.6.0 oprogramowania Finance and Operations lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="39914-111">The steps in this process are supported for Finance and Operations Financial reporting release 7.2.6.0 and later.</span></span> <span data-ttu-id="39914-112">Jeśli masz starszą wersję, skontaktuj się z zespołem pomocy technicznej w celu uzyskania pomocy.</span><span class="sxs-lookup"><span data-stu-id="39914-112">If you have an earlier release, contact the Support team for assistance.</span></span>

<span data-ttu-id="39914-113">W określonych scenariuszach konieczne może być zresetowanie składnicy danych dla modułu Raporty finansowe.</span><span class="sxs-lookup"><span data-stu-id="39914-113">In specific scenarios, you might have to reset the data mart for Financial reporting.</span></span> <span data-ttu-id="39914-114">Zadanie to można wykonać za pomocą klienta z zainstalowanym projektantem raportów.</span><span class="sxs-lookup"><span data-stu-id="39914-114">You can complete this task in the Report designer client.</span></span> <span data-ttu-id="39914-115">Poniżej przedstawiono kilka scenariuszy, w których konieczne może być zresetowanie składnicy danych:</span><span class="sxs-lookup"><span data-stu-id="39914-115">Here are some scenarios where you might have to reset the data mart:</span></span>

- <span data-ttu-id="39914-116">Baza danych Finance and Operations została przywrócona, ale baza danych składnicy danych nie.</span><span class="sxs-lookup"><span data-stu-id="39914-116">The Finance and Operations database was restored, but the data mart database wasn't restored.</span></span>
- <span data-ttu-id="39914-117">Wyświetlane dane za okres są niepoprawne.</span><span class="sxs-lookup"><span data-stu-id="39914-117">You see incorrect data for a period.</span></span>
- <span data-ttu-id="39914-118">Pomoc techniczna zaleciła zresetowanie składnicy danych w ramach procedury rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="39914-118">Support instructs you to reset the data mart as part of a troubleshooting step.</span></span>

<span data-ttu-id="39914-119">Składnicę danych należy resetować wyłącznie w okresach, gdy ilość przetwarzania bazy danych jest niewielka.</span><span class="sxs-lookup"><span data-stu-id="39914-119">The data mart reset should be done only during times when the amount of processing on the database is small.</span></span> <span data-ttu-id="39914-120">W trakcie resetowania raporty finansowe będą niedostępne.</span><span class="sxs-lookup"><span data-stu-id="39914-120">Financial reporting will be unavailable during the reset process.</span></span>

#### <a name="reset-the-data-mart"></a><span data-ttu-id="39914-121">Resetowanie składnicy danych</span><span class="sxs-lookup"><span data-stu-id="39914-121">Reset the data mart</span></span>

<span data-ttu-id="39914-122">Aby zresetować składnicę danych, wybierz z menu **Narzędzia** w projektancie raportów opcję **Resetuj składnicę danych**.</span><span class="sxs-lookup"><span data-stu-id="39914-122">To reset the data mart, in Report designer, on the **Tools** menu, select **Reset Data Mart**.</span></span> <span data-ttu-id="39914-123">Pojawi się okno dialogowe składające się z dwóch części: **Statystyki** i **Reset**.</span><span class="sxs-lookup"><span data-stu-id="39914-123">The dialog box that appears has two sections: **Statistics** and **Reset**.</span></span>

<span data-ttu-id="39914-124">[![Okno dialogowe Resetowanie składnicy danych](./media/Statistics.png)](./media/Statistics.png)</span><span class="sxs-lookup"><span data-stu-id="39914-124">[![Reset Data Mart dialog box](./media/Statistics.png)](./media/Statistics.png)</span></span>

##### <a name="integration-attempts"></a><span data-ttu-id="39914-125">Próby integracji</span><span class="sxs-lookup"><span data-stu-id="39914-125">Integration attempts</span></span>

<span data-ttu-id="39914-126">Siatka **Próby integracji** pokazuje, ile razy system podjął próbę integracji transakcji.</span><span class="sxs-lookup"><span data-stu-id="39914-126">The **Integration attempts** grid shows how many times the system has tried to integrate transactions.</span></span> <span data-ttu-id="39914-127">Jeśli pierwsze kilka prób zakończy się niepowodzeniem, system będzie podejmował próby integracji danych w ciągu kilku dni.</span><span class="sxs-lookup"><span data-stu-id="39914-127">The system continues to try to integrate data over a period of days if the first few attempts aren't successful.</span></span> <span data-ttu-id="39914-128">Składnicę danych należy zresetować, jeśli liczba prób wyniesie co najmniej 8, a także w przypadku wielu kombinacji wymiarów lub rekordów transakcji.</span><span class="sxs-lookup"><span data-stu-id="39914-128">You will know that the data mart must be reset is if the number of attempts is 8 or more, and if there are many Dimension combination or Transaction records.</span></span> <span data-ttu-id="39914-129">W takiej sytuacji dane nie zostaną uwzględnione w raporcie.</span><span class="sxs-lookup"><span data-stu-id="39914-129">In this situation, the data won't be reported on.</span></span>

##### <a name="data-status"></a><span data-ttu-id="39914-130">Stan danych</span><span class="sxs-lookup"><span data-stu-id="39914-130">Data status</span></span>

<span data-ttu-id="39914-131">Siatka **Stan danych** zawiera migawkę transakcji, kursów wymiany i wartości wymiarów w składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="39914-131">The **Data status** grid provides a snapshot of the transactions, exchange rates, and dimension values in the data mart.</span></span> <span data-ttu-id="39914-132">Duża liczba starych rekordów wskazuje na liczne ich aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="39914-132">A large number of stale records indicates that numerous updates to the records have occurred.</span></span> <span data-ttu-id="39914-133">Taka sytuacja może spowodować wydłużenie czasu generowania raportów.</span><span class="sxs-lookup"><span data-stu-id="39914-133">This situation might cause slower report generation times.</span></span>

##### <a name="misaligned-main-account-categories"></a><span data-ttu-id="39914-134">Źle wyrównane kategorie konta głównego</span><span class="sxs-lookup"><span data-stu-id="39914-134">Misaligned main account categories</span></span>

<span data-ttu-id="39914-135">Jeśli korzystasz z modułu Raporty finansowe w wersji starszej niż 7.2.1 oprogramowania Microsoft Dynamics 365 for Finance and Operations zresetowanie składnicy danych może być konieczne w przypadku zmiany nazw kont oraz przeniesienia kont między kategoriami kont.</span><span class="sxs-lookup"><span data-stu-id="39914-135">If you're using a release that is earlier than Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.1, you might have to reset the data mart if you rename accounts and move accounts between account categories.</span></span> <span data-ttu-id="39914-136">Te akcje mogą spowodować nieprawidłowe wyrównanie kategorii konta głównego.</span><span class="sxs-lookup"><span data-stu-id="39914-136">These actions can cause main account categories to become misaligned.</span></span> <span data-ttu-id="39914-137">Pole **Źle wyrównane kategorie konta głównego** wskazuje, czy taki problem ma miejsce.</span><span class="sxs-lookup"><span data-stu-id="39914-137">The **Misaligned main account categories** field shows whether you're experiencing that issue.</span></span>

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a><span data-ttu-id="39914-138">Resetowanie składnicy danych modułu Raporty finansowe w wersji 7.2.6.0 oprogramowania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="39914-138">Reset the data mart in Finance and Operations Financial reporting release 7.2.6.0</span></span>

<span data-ttu-id="39914-139">Aby zresetować składnicę danych modułu Raporty finansowe w wersji 7.2.6.0 lub starszej oprogramowania Finance and Operations, w oknie dialogowym **Resetowanie składnicy danych** zaznacz pole wyboru **Resetuj składnicę danych**, a następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="39914-139">To reset the data mart in Finance and Operations Financial reporting release 7.2.6.0 and earlier, in the **Reset Data Mart** dialog box, select the **Reset data mart** check box, and then select **OK**.</span></span> <span data-ttu-id="39914-140">Składnicę danych należy resetować wyłącznie w czasie zaplanowanego przestoju.</span><span class="sxs-lookup"><span data-stu-id="39914-140">You should reset the data mart only during scheduled downtime.</span></span>

<span data-ttu-id="39914-141">[![Pole wyboru Resetuj składnicę danych](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="39914-141">[![Reset data mart check box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a><span data-ttu-id="39914-142">Zresetuj składnicę danych i wybierz przyczynę w module Raporty finansowe w wersji 7.3.0 oprogramowania Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="39914-142">Reset the data mart and select a reason in Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.3.0</span></span>

<span data-ttu-id="39914-143">W razie stwierdzenia konieczności zresetowania składnicy danych zaznacz pole wyboru **Resetuj składnicę danych**, a następnie w polu **Przyczyna** wybierz przyczynę.</span><span class="sxs-lookup"><span data-stu-id="39914-143">If you determine that a data mart reset is required, select the **Reset data mart** check box, and then select a reason in the **Reason** field.</span></span> <span data-ttu-id="39914-144">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="39914-144">The following options are available:</span></span>

- <span data-ttu-id="39914-145">**Dane nieprawidłowe lub ich brak** — na podstawie statystyk użytkownik stwierdził, że może brakować danych.</span><span class="sxs-lookup"><span data-stu-id="39914-145">**Missing or incorrect data** – Based on the statistics, you've determined that data might be missing.</span></span> <span data-ttu-id="39914-146">Przed podjęciem dalszych czynności zaleca się konsultację z pomocą techniczną w celu określenia głównej przyczyny.</span><span class="sxs-lookup"><span data-stu-id="39914-146">Before you continue, we recommend that you work with Support to determine the root cause.</span></span>
- <span data-ttu-id="39914-147">**Przywróć bazę danych** — baza danych oprogramowania Finance and Operations została przywrócona, ale baza danych składnicy danych modułu Raporty finansowe – nie.</span><span class="sxs-lookup"><span data-stu-id="39914-147">**Restore database** – The Finance and Operations database was restored, but the database for the Financial reporting data mart wasn't restored.</span></span>
- <span data-ttu-id="39914-148">**Inne** — resetowanie składnicy danych z innego powodu.</span><span class="sxs-lookup"><span data-stu-id="39914-148">**Other** – You're resetting the data mart for another reason.</span></span> <span data-ttu-id="39914-149">Jeśli istnieje podejrzenie, że występuje problem, skontaktuj się z obsługą techniczną, aby go zidentyfikować.</span><span class="sxs-lookup"><span data-stu-id="39914-149">If you're concerned that there is an issue, contact Support to identify it.</span></span>

> [!NOTE]
> <span data-ttu-id="39914-150">Przed wykonaniem tych kroków sprawdź, czy wszystkie zadania ukończyły integrację.</span><span class="sxs-lookup"><span data-stu-id="39914-150">Verify that all existing tasks have finished integrating before you complete the steps.</span></span> <span data-ttu-id="39914-151">Stan integracji można wyświetlić, wybierając kolejno opcje **Narzędzia** &gt; **Stan integracji**.</span><span class="sxs-lookup"><span data-stu-id="39914-151">You can view the status of the integration by selecting **Tools** &gt; **Integration status**.</span></span>

#### <a name="clear-users-and-companies"></a><span data-ttu-id="39914-152">Usuń użytkowników i firmy</span><span class="sxs-lookup"><span data-stu-id="39914-152">Clear users and companies</span></span>

<span data-ttu-id="39914-153">Jeśli baza danych została przywrócona, ale po jej przywróceniu wprowadzono zmiany w użytkownikach lub firmach, zaznacz pole wyboru **Usuń użytkowników i firmy**.</span><span class="sxs-lookup"><span data-stu-id="39914-153">Select the **Clear users and companies** check box if you restored your database, but you then made changes to users or companies.</span></span> <span data-ttu-id="39914-154">Najczęściej nie ma potrzeby zaznaczania tego pola wyboru.</span><span class="sxs-lookup"><span data-stu-id="39914-154">You should rarely have to select this check box.</span></span>

<span data-ttu-id="39914-155">Aby rozpocząć proces resetowania, naciśnij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="39914-155">When you're ready to start the reset process, select **OK**.</span></span> <span data-ttu-id="39914-156">Zostanie wyświetlony monit o potwierdzenie gotowości do rozpoczęcia procesu.</span><span class="sxs-lookup"><span data-stu-id="39914-156">You're prompted to confirm that you're ready to start the process.</span></span> <span data-ttu-id="39914-157">Należy pamiętać, że w trakcie resetowania oraz początkowej integracji danych, która nastąpi po jego zakończeniu, moduł Raporty finansowe będzie niedostępny.</span><span class="sxs-lookup"><span data-stu-id="39914-157">Note that Financial reporting won't be available during the reset and the initial data integration that occurs afterward.</span></span>

<span data-ttu-id="39914-158">Aby sprawdzić stan integracji, wybierz kolejno opcje **Narzędzia** &gt; **Stan integracji** w celu wyświetlenia czasu ostatniej integracji oraz jej stanu.</span><span class="sxs-lookup"><span data-stu-id="39914-158">If you want to review the status of the integration, select **Tools** &gt; **Integration status** to see the last time that the integration was run and the status.</span></span>

<span data-ttu-id="39914-159">[![Wyświetlanie stanu integracji](./media/Integration.png)](./media/Integration.png)</span><span class="sxs-lookup"><span data-stu-id="39914-159">[![View the status of the integration](./media/Integration.png)](./media/Integration.png)</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a><span data-ttu-id="39914-160">Resetowanie składnicy danych modułu Raporty finansowe w wersji 7.0.10000.4 lub nowszej oprogramowania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="39914-160">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>

<span data-ttu-id="39914-161">Jeśli kiedykolwiek baza danych oprogramowania Finance and Operations będzie przywracana z kopii zapasowej lub kopii bazy danych z innego środowiska, należy wykonać kroki opisane w tej części, aby mieć pewność, że składnica danych modułu Raporty finansowe poprawnie wykorzystuje przywróconą bazę danych oprogramowania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="39914-161">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this section to help guarantee that the Financial reporting data mart correctly uses the restored Finance and Operations database.</span></span>

> [!NOTE]
> <span data-ttu-id="39914-162">Ta procedura dotyczy aplikacji Microsoft Dynamics AX w wersji 7.0.1 (maj 2016 r.) (wersja aplikacji 7.0.1265.23014 i wersja modułu Raporty finansowe 7.0.10000.4) lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="39914-162">The steps in this process are supported for Microsoft Dynamics AX application version 7.0.1 (May 2016) (application build 7.0.1265.23014 and Financial reporting build 7.0.10000.4) and later.</span></span> <span data-ttu-id="39914-163">Jeśli posiadasz starszą wersję oprogramowania Finance and Operations, skontaktuj się z pomocą techniczną w celu uzyskania pomocy.</span><span class="sxs-lookup"><span data-stu-id="39914-163">If you have an earlier version of Finance and Operations, contact Support for assistance.</span></span>

### <a name="export-report-definitions"></a><span data-ttu-id="39914-164">Eksportowanie definicji raportów</span><span class="sxs-lookup"><span data-stu-id="39914-164">Export report definitions</span></span>

<span data-ttu-id="39914-165">Najpierw wykonaj przedstawione kroki, aby wyeksportować projekty raportów z projektanta raportów.</span><span class="sxs-lookup"><span data-stu-id="39914-165">First, follow these steps to export the report designs from Report designer.</span></span>

1. <span data-ttu-id="39914-166">W projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.</span><span class="sxs-lookup"><span data-stu-id="39914-166">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="39914-167">Wybierz grupę bloków konstrukcyjnych do wyeksportowania, a następnie wybierz opcję **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="39914-167">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="39914-168">W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.</span><span class="sxs-lookup"><span data-stu-id="39914-168">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="39914-169">Wybierz definicje raportów do wyeksportowania:</span><span class="sxs-lookup"><span data-stu-id="39914-169">Select the report definitions to export:</span></span>

    - <span data-ttu-id="39914-170">Aby wyeksportować wszystkie istniejące definicje raportów i powiązane z nimi bloki konstrukcyjne, wybierz opcję **Zaznacz wszystko**.</span><span class="sxs-lookup"><span data-stu-id="39914-170">To export all your report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="39914-171">Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, wybierz odpowiednią kartę i elementy do wyeksportowania.</span><span class="sxs-lookup"><span data-stu-id="39914-171">To export specific reports, rows, columns, trees, or dimension sets, select the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="39914-172">Naciśnij i przytrzymaj klawisz Ctrl, aby zaznaczyć kilka elementów na karcie. Po wybraniu raportów do wyeksportowania wybrane zostaną skojarzone wiersze, kolumny, drzewa i zestawy wymiarów.</span><span class="sxs-lookup"><span data-stu-id="39914-172">Press and hold the Ctrl key to select multiple items on a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4. <span data-ttu-id="39914-173">Wybierz opcję **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="39914-173">Select **Export**.</span></span>
5. <span data-ttu-id="39914-174">Wprowadź nazwę pliku i wybierz bezpieczną lokalizację, w której chcesz zapisać wyeksportowane definicje raportów.</span><span class="sxs-lookup"><span data-stu-id="39914-174">Enter a file name, and select a secure location where you want to save the exported report definitions.</span></span>
6. <span data-ttu-id="39914-175">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="39914-175">Select **Save**.</span></span>

<span data-ttu-id="39914-176">Plik można skopiować lub wczytać do bezpiecznej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="39914-176">You can copy or upload the file to a secure location.</span></span> <span data-ttu-id="39914-177">W ten sposób plik można zaimportować później do innego środowiska.</span><span class="sxs-lookup"><span data-stu-id="39914-177">In this way, the file can be imported into a different environment later.</span></span> <span data-ttu-id="39914-178">Więcej informacji na temat korzystania z konta magazynu usługi Microsoft Azure, zobacz [Przenoszenie danych za pomocą narzędzia wiersza polecenia AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="39914-178">For information about how to use a Microsoft Azure storage account, see [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span>

> [!NOTE]
> <span data-ttu-id="39914-179">Firma Microsoft nie zapewnia konta magazynu w ramach umowy na usługę Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="39914-179">Microsoft doesn't provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="39914-180">Należy we własnym zakresie kupić konto magazynu lub użyć konta magazynu z oddzielnej subskrypcji usługi Azure.</span><span class="sxs-lookup"><span data-stu-id="39914-180">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span>

> [!WARNING]
> <span data-ttu-id="39914-181">Należy pamiętać o zachowaniu dysku D na maszynach wirtualnych Azure (VM).</span><span class="sxs-lookup"><span data-stu-id="39914-181">Be aware of the behavior of drive D on Azure virtual machines (VMs).</span></span> <span data-ttu-id="39914-182">Nie należy trwale przechowywać wyeksportowanych grup bloków konstrukcyjnych na dysku D. Aby uzyskać więcej informacji na temat dysków tymczasowych, zobacz [Opis koncepcji dysku tymczasowego na maszynach wirtualnych systemu Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="39914-182">Don't permanently store your exported building block groups on drive D. For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

### <a name="stop-services"></a><span data-ttu-id="39914-183">Zatrzymywanie usług</span><span class="sxs-lookup"><span data-stu-id="39914-183">Stop services</span></span>

<span data-ttu-id="39914-184">Następujące usługi Microsoft Windows będą mieć otwarte połączenia z bazą danych programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="39914-184">The following Microsoft Windows services will have open connections to the Finance and Operations database.</span></span> <span data-ttu-id="39914-185">W związku z tym należy połączyć się ze wszystkimi komputerami w środowisku za pomocą usługi pulpitu zdalnego firmy Microsoft, a następnie zatrzymać te usługi za pomocą konsoli services.msc.</span><span class="sxs-lookup"><span data-stu-id="39914-185">Therefore, you must use Microsoft Remote Desktop to connect to all the computers in the environment and then use services.msc to stop these services.</span></span>

- <span data-ttu-id="39914-186">Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerami Application Object Server [AOS])</span><span class="sxs-lookup"><span data-stu-id="39914-186">World wide web publishing service (on all Application Object Servers [AOS] computers)</span></span>
- <span data-ttu-id="39914-187">Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)</span><span class="sxs-lookup"><span data-stu-id="39914-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="39914-188">Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem Business Intelligence [BI])</span><span class="sxs-lookup"><span data-stu-id="39914-188">Management Reporter 2012 Process Service (on Business intelligence [BI] computers only)</span></span>

### <a name="reset"></a><span data-ttu-id="39914-189">Zeruj</span><span class="sxs-lookup"><span data-stu-id="39914-189">Reset</span></span>

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="39914-190">Pobieranie najnowszego pakietu MinorVersionDataUpgrade.zip</span><span class="sxs-lookup"><span data-stu-id="39914-190">Download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="39914-191">Pobierz najnowszy pakiet MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="39914-191">Download the latest MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="39914-192">Aby dowiedzieć się, jak odnaleźć i pobrać odpowiednią wersję pakietu uaktualnienia danych, zobacz [Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="39914-192">For instructions about how to find and download the correct version of the data upgrade package, see the[Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="39914-193">Uaktualnienie nie jest wymagane w celu pobrania pakietu MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="39914-193">An upgrade isn't required in order to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="39914-194">W związku z tym wystarczy wykonać kroki opisane w części „Pobieranie najnowszego wdrażalnego pakietu uaktualniania danych” tego tematu.</span><span class="sxs-lookup"><span data-stu-id="39914-194">Therefore, you just have follow the steps in the "Download the latest data upgrade deployable package" section of that topic.</span></span> <span data-ttu-id="39914-195">Można pominąć wszystkie inne kroki opisane w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="39914-195">You can skip all the other steps in the topic.</span></span>

#### <a name="run-scripts-against-the-finance-and-operations-database"></a><span data-ttu-id="39914-196">Uruchamianie skryptów w bazie danych programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="39914-196">Run scripts against the Finance and Operations database</span></span>

<span data-ttu-id="39914-197">Uruchom następujące skrypty w bazie danych programu Finance and Operations (nie w bazie danych modułu Raporty finansowe):</span><span class="sxs-lookup"><span data-stu-id="39914-197">Run the following scripts against the Finance and Operations database (not against the Financial reporting database):</span></span>

- <span data-ttu-id="39914-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="39914-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
- <span data-ttu-id="39914-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="39914-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="39914-200">Te skrypty pomogą zagwarantować poprawność użytkowników, ról i ustawień śledzenia zmian.</span><span class="sxs-lookup"><span data-stu-id="39914-200">These scripts help guarantee that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a><span data-ttu-id="39914-201">Resetowanie bazy danych za pomocą polecenia programu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39914-201">Run a Windows PowerShell command to reset the database</span></span>

<span data-ttu-id="39914-202">Aby zresetować integrację między oprogramowaniem Finance and Operations a modułem Raporty finansowe, na komputerze z zainstalowanym serwerem AIS uruchom program Microsoft Windows PowerShell w roli administratora, a następnie uruchom podane polecenia.</span><span class="sxs-lookup"><span data-stu-id="39914-202">On the AOS computer, start Microsoft Windows PowerShell as an administrator, and run the following commands to reset the integration between Finance and Operations and Financial reporting.</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

<span data-ttu-id="39914-203">Objaśnienie parametrów w poleceniu**Reset-DatamartIntegration**:</span><span class="sxs-lookup"><span data-stu-id="39914-203">Here is an explanation of the parameters in the **Reset-DatamartIntegration** command:</span></span>

- <span data-ttu-id="39914-204">Prawidłowe wartości parametru **-Reason** to **SERVICING**, **BADDATA** i **OTHER**.</span><span class="sxs-lookup"><span data-stu-id="39914-204">The valid values for **-Reason** are **SERVICING**, **BADDATA**, and **OTHER**.</span></span>
- <span data-ttu-id="39914-205">Parametr **-ReasonDetail** ma format zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="39914-205">The **-ReasonDetail** parameter is free text.</span></span>
- <span data-ttu-id="39914-206">Wartości przyczyny oraz szczegółów przyczyny zostaną zarejestrowane w funkcji telemetrii/monitorowania środowiska.</span><span class="sxs-lookup"><span data-stu-id="39914-206">The reason and reason detail will be recorded in telemetry/environment monitoring.</span></span>

> [!NOTE]
> <span data-ttu-id="39914-207">Po uruchomieniu polecenia wyświetli się monit o wprowadzenie **Y** w celu potwierdzenia resetu bazy danych.</span><span class="sxs-lookup"><span data-stu-id="39914-207">After you run the commands, you will be asked to enter **Y** to confirm that you want to reset the database.</span></span>

#### <a name="restart-services"></a><span data-ttu-id="39914-208">Ponowne uruchamianie usług</span><span class="sxs-lookup"><span data-stu-id="39914-208">Restart services</span></span>

<span data-ttu-id="39914-209">Za pomocą konsoli services.msc uruchom usługi, które zostały wcześniej zatrzymane:</span><span class="sxs-lookup"><span data-stu-id="39914-209">Use services.msc to restart the services that you stopped earlier:</span></span>

- <span data-ttu-id="39914-210">Usługa publikowania w sieci World Wide Web (na wszystkich komputerach z serwerem AOS)</span><span class="sxs-lookup"><span data-stu-id="39914-210">World wide web publishing service (on all AOS computers)</span></span>
- <span data-ttu-id="39914-211">Usługa zarządzania wsadowego w programie Microsoft Dynamics 365 for Finance and Operations (tylko nieprywatne komputery z serwerem AOS)</span><span class="sxs-lookup"><span data-stu-id="39914-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="39914-212">Usługa procesu w programie Management Reporter 2012 (tylko na komputerach z oprogramowaniem BI)</span><span class="sxs-lookup"><span data-stu-id="39914-212">Management Reporter 2012 Process Service (on BI computers only)</span></span>

#### <a name="import-report-definitions"></a><span data-ttu-id="39914-213">Importowanie definicji raportów</span><span class="sxs-lookup"><span data-stu-id="39914-213">Import report definitions</span></span>

<span data-ttu-id="39914-214">Zaimportuj projekty raportów z projektanta raportów, korzystając z pliku utworzonego podczas eksportu.</span><span class="sxs-lookup"><span data-stu-id="39914-214">Import your report designs from Report designer by using the file that was created during the export.</span></span>

1. <span data-ttu-id="39914-215">W projektancie raportów wybierz kolejno opcje **Firma** &gt; **Grupy bloków konstrukcyjnych**.</span><span class="sxs-lookup"><span data-stu-id="39914-215">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="39914-216">Wybierz grupę bloków konstrukcyjnych do wyeksportowania, a następnie wybierz opcję **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="39914-216">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="39914-217">W programie Finance and Operations obsługiwana jest tylko jedna grupa bloków konstrukcyjnych — **Domyślne**.</span><span class="sxs-lookup"><span data-stu-id="39914-217">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="39914-218">Zaznacz blok konstrukcyjny **Domyślne** i wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="39914-218">Select the **Default** building block, and then select **Import**.</span></span>
4. <span data-ttu-id="39914-219">Zaznacz plik zawierający wyeksportowane definicje raportów i wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="39914-219">Select the file that contains the exported report definitions, and then select **Open**.</span></span>
5. <span data-ttu-id="39914-220">W oknie dialogowym **Import** zaznacz definicje raportów przeznaczone do zaimportowania:</span><span class="sxs-lookup"><span data-stu-id="39914-220">In the **Import** dialog box, select the report definitions to import:</span></span>

    - <span data-ttu-id="39914-221">Aby zaimportować wszystkie istniejące definicje raportów i powiązane z nimi bloki konstrukcyjne, wybierz opcję **Zaznacz wszystko**.</span><span class="sxs-lookup"><span data-stu-id="39914-221">To import all the report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="39914-222">W celu zaimportowania konkretnych raportów, wierszy, kolumn, drzew lub zestawów wymiarów zaznacz te pozycje.</span><span class="sxs-lookup"><span data-stu-id="39914-222">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6. <span data-ttu-id="39914-223">Wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="39914-223">Select **Import**.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a><span data-ttu-id="39914-224">Resetowanie składnicy danych modułu Raporty finansowe dla oprogramowania Finance and Operations (lokalnie)</span><span class="sxs-lookup"><span data-stu-id="39914-224">Reset the Financial reporting data mart for Finance and Operations (on-premises)</span></span>

1. <span data-ttu-id="39914-225">Poleć wszystkim użytkownikom zamknięcie projektanta raportów oraz modułu Raporty finansowe oprogramowania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="39914-225">Instruct all users to exit Report designer and the Financial reporting area of Finance and Operations.</span></span>
2. <span data-ttu-id="39914-226">Uruchom podany skrypt w bazie danych modułu Raporty finansowe (MRDB).</span><span class="sxs-lookup"><span data-stu-id="39914-226">Run the following script against the Financial reporting database (MRDB).</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. <span data-ttu-id="39914-227">Przytnij lub usuń wszystkie rekordy z tabeli FINANCIALREPORTS w bazie danych oprogramowania Finance and Operations (AXDB).</span><span class="sxs-lookup"><span data-stu-id="39914-227">Truncate or delete all records from the FINANCIALREPORTS table in the Finance and Operations database (AXDB).</span></span>
4. <span data-ttu-id="39914-228">Przytnij lub usuń wszystkie rekordy z tabeli FINANCIALREPORTVERSION w bazie danych oprogramowania Finance and Operations (jeśli taka tabela istnieje).</span><span class="sxs-lookup"><span data-stu-id="39914-228">Truncate or delete all records from the FINANCIALREPORTVERSION table, if this table exists in the Finance and Operations database.</span></span> <span data-ttu-id="39914-229">Jeśli w bazie danych oprogramowania Finance and Operations nie ma takiej tabeli, pomiń ten krok.</span><span class="sxs-lookup"><span data-stu-id="39914-229">If the table doesn't exist in the Finance and Operations database, skip this step.</span></span>
5. <span data-ttu-id="39914-230">Uruchom skrypt **ResetDatamaer.sql** w bazie danych modułu Raporty finansowe.</span><span class="sxs-lookup"><span data-stu-id="39914-230">Run the **ResetDatamart.sql** script against the Financial reporting database.</span></span> <span data-ttu-id="39914-231">Ten skrypt wyłącza integrację składnicy danych, powoduje usunięcie wszystkich danych ze składnicy danych, a następnie ponownie włącza integrację składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="39914-231">This script disables the data mart integration, deletes all the data mart data, and then reenables the data mart integration.</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. <span data-ttu-id="39914-232">Po zresetowaniu użytkownik może ręcznie sprawdzić, czy dane zostały ponownie wczytane, uruchamiając następującą kwerendę w bazie danych modułu Raporty finansowe.</span><span class="sxs-lookup"><span data-stu-id="39914-232">After the reset, you can manually verify the data reload by running the following query against the Financial reporting database.</span></span>

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    <span data-ttu-id="39914-233">Sprawdź, czy we wszystkich wierszach występuje wartość **LastRunTime**, a parametr **StateType** ma wartość **5**.</span><span class="sxs-lookup"><span data-stu-id="39914-233">Confirm that all rows have a **LastRunTime** value, and that **StateType** is set to **5**.</span></span> <span data-ttu-id="39914-234">Ustawienie dla parametru **StateType** wartości **5** wskazuje, że dane zostały pomyślnie wczytane ponownie.</span><span class="sxs-lookup"><span data-stu-id="39914-234">A **StateType** value of **5** indicates that the data was successfully reloaded.</span></span> <span data-ttu-id="39914-235">Wartość **7** wskazuje stan błędu.</span><span class="sxs-lookup"><span data-stu-id="39914-235">A value of **7** indicates a faulted state.</span></span> <span data-ttu-id="39914-236">Czasami mapa hierarchii organizacji ma taki stan przy pierwszym jej uruchomieniu.</span><span class="sxs-lookup"><span data-stu-id="39914-236">Sometimes, the Organization Hierarchy map has this state the first time that it runs.</span></span> <span data-ttu-id="39914-237">Jednak stan błędu powinien być automatycznie rozwiązywany.</span><span class="sxs-lookup"><span data-stu-id="39914-237">However, the faulted state but should be automatically resolved.</span></span>


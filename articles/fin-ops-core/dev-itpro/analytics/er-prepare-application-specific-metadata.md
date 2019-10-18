---
title: Przygotuj metadane dla konkretnej aplikacji dla RCS i ER
description: Kroki w tym temacie wyjaśniają, w jaki sposób można przygotować metadane konkretnej aplikacji dla usługi Regulatory configuration service (RCS) oraz Elektronicznego raportowania (ER).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c036eab38845db8427c447b27cce0be8048669fd
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248661"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a><span data-ttu-id="1a66b-103">Przygotuj metadane dla konkretnej aplikacji dla RCS</span><span class="sxs-lookup"><span data-stu-id="1a66b-103">Prepare application-specific metadata for RCS</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1a66b-104">W tym temacie przedstawiono przykłady następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="1a66b-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="1a66b-105">Przygotuj metadane dla konkretnej aplikacji dla użycia w RCS</span><span class="sxs-lookup"><span data-stu-id="1a66b-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="1a66b-106">Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="1a66b-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="1a66b-107">Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji</span><span class="sxs-lookup"><span data-stu-id="1a66b-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="1a66b-108">Przygotuj metadane dla konkretnej aplikacji dla użycia w RCS</span><span class="sxs-lookup"><span data-stu-id="1a66b-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="1a66b-109">Poniższa procedura pokazuje, w jaki sposób użytkownik, który ma rolę **Administratora Systemu** lub **Programisty Elektronicznego Reportowania**, może utworzyć konfigurację raportowania elektronicznego (ER), która zawiera metadane aplikacji, która jest używana do projektowania konfiguracji mapowania modeli ER w usłudze Regulatory configuration service (RCS).</span><span class="sxs-lookup"><span data-stu-id="1a66b-109">The following procedure shows how a user who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="1a66b-110">Przykładowe mapowanie modelu ER zostanie stworzone w tym przykładzie do uzyskania dostępu do transakcji handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="1a66b-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="1a66b-111">W tym przykładzie chcesz użyć RCS do zaprojektowania rozwiązania ER dla aplikacji, które będzie wykorzystywane do generowania dokumentów elektronicznych zawierających informacje z dziedziny handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="1a66b-111">For this example, you want to use RCS to design an ER solution for the application that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="1a66b-112">Aby określić mapowanie między modelem danych ER a źródłami wymaganych danych, musisz mieć dostęp do metadanych aplikacji w RCS.</span><span class="sxs-lookup"><span data-stu-id="1a66b-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata in RCS.</span></span> <span data-ttu-id="1a66b-113">Dlatego też, w ramach procesu projektowania rozwiązania ER, należy skonfigurować nową konfigurację metadanych ER, która zawiera wszystkie metadane, które są obecnie wymagane w celu wygenerowania raportów ER dla wybranej domeny biznesowej.</span><span class="sxs-lookup"><span data-stu-id="1a66b-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="1a66b-114">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Te kroki można wykonać dla dowolnej firmy.</span><span class="sxs-lookup"><span data-stu-id="1a66b-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="1a66b-115">Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="1a66b-116">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="1a66b-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="1a66b-117">Jeśli nie widzisz dostawcy konfiguracji, musisz wykonać kroki opisane w procedurze, [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1a66b-117">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="1a66b-118">Wybierz **Konfiguracja metadanych**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="1a66b-119">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="1a66b-120">W rozwijanym menu w polu **Nazwa** wpisz nazwę.</span><span class="sxs-lookup"><span data-stu-id="1a66b-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="1a66b-121">Dla tego przykładu wpisz **Metadane handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="1a66b-122">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="1a66b-123">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-123">Select **Designer**.</span></span>
8. <span data-ttu-id="1a66b-124">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a66b-125">Możesz wybrać wszystkie metadane dla całej aplikacji lub dla wybranych modeli lub modułów.</span><span class="sxs-lookup"><span data-stu-id="1a66b-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="1a66b-126">W obu przypadkach należy pamiętać, że następujące metadane zostaną automatycznie dodane: tabele, wyliczenia i rozszerzone typy danych (EDT).</span><span class="sxs-lookup"><span data-stu-id="1a66b-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="1a66b-127">Gdy wymagane są dodatkowe typy metadanych, należy je ręcznie dodać.</span><span class="sxs-lookup"><span data-stu-id="1a66b-127">When additional types of metadata are required, they must be manually added.</span></span>

<span data-ttu-id="1a66b-128">Musisz dodać kilka metadanych związanych z transakcjami handlu zagranicznego i ręcznie wybrać elementy metadanych.</span><span class="sxs-lookup"><span data-stu-id="1a66b-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="1a66b-129">Wybierz **Dodaj źródło danych \> Tabele**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="1a66b-130">Filtruj wartość **Intrastat** w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="1a66b-131">Wybierz tabelę **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="1a66b-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-132">Select **OK**.</span></span>

<span data-ttu-id="1a66b-133">Musisz dodać informacje metadanych o tabeli Intrastat.</span><span class="sxs-lookup"><span data-stu-id="1a66b-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="1a66b-134">W widoku drzewa wybierz **Tabele Intrastat \> \>Relacje \> IntrastatCommodity (Tabele EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="1a66b-135">Wybierz **Dodaj metadane**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a66b-136">Metadane dotyczące wymaganych relacji dla wybranej tabeli muszą zostać dodane ręcznie.</span><span class="sxs-lookup"><span data-stu-id="1a66b-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="1a66b-137">Wybierz **Dodaj źródło danych**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="1a66b-138">Wybierz **Wyliczenie**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="1a66b-139">Filtruj wartość **IntrastatDirection** w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="1a66b-140">Wybierz dane wyliczenia w **IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="1a66b-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-141">Select **OK**.</span></span>
20. <span data-ttu-id="1a66b-142">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-142">Select **Save**.</span></span>
21. <span data-ttu-id="1a66b-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1a66b-143">Close the page.</span></span>
22. <span data-ttu-id="1a66b-144">Wypełnij wersję roboczą konfiguracji metadanych:</span><span class="sxs-lookup"><span data-stu-id="1a66b-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="1a66b-145">Wybierz **Zmień status \> Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="1a66b-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-146">Select **OK**.</span></span>
    3. <span data-ttu-id="1a66b-147">Wybierz ukończoną wersję 1.</span><span class="sxs-lookup"><span data-stu-id="1a66b-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="1a66b-148">Wyeksportuj ukończoną wersję konfiguracji metadanych z aplikacji jako plik XML:</span><span class="sxs-lookup"><span data-stu-id="1a66b-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="1a66b-149">Wybierz **Zamień \> Eksportuj jako plik XML**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="1a66b-150">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-150">Select **OK**.</span></span>

<span data-ttu-id="1a66b-151">Utworzona konfiguracja metadanych ER jest zapisywana jako plik **Zagraniczny handel metadane.xml**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="1a66b-152">Możesz teraz zaimportować go do RCS, aby mógł być używany jako źródło metadanych dla domeny handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="1a66b-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain.</span></span> <span data-ttu-id="1a66b-153">Na podstawie tych informacji można określić mapowanie między metadanymi aplikacji a modelem danych ER.</span><span class="sxs-lookup"><span data-stu-id="1a66b-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="1a66b-154">Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="1a66b-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="1a66b-155">Poniższa procedura pokazuje, w jaki sposób użytkownik RCS, który ma rolę **Administratora Systemu** lub **Programisty Elektronicznego Reportowania**, może zaprojektować nowe mapowanie modelu ER przy użyciu metadanych z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the application.</span></span> <span data-ttu-id="1a66b-156">Dostęp do metadanych aplikacji będzie możliwy za pomocą konfiguracji metadanych ER, która zawiera przykładowy zestaw metadanych umożliwiających dostęp do transakcji handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="1a66b-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="1a66b-157">Przed zakończeniem tej procedury, należy najpierw wypełnić następujące procedury:</span><span class="sxs-lookup"><span data-stu-id="1a66b-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="1a66b-158">Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego</span><span class="sxs-lookup"><span data-stu-id="1a66b-158">Create a configuration provider and mark it as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="1a66b-159">Przygotuj metadane dla konkretnej aplikacji dla użycia w RCS</span><span class="sxs-lookup"><span data-stu-id="1a66b-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="1a66b-160">Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="1a66b-161">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="1a66b-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="1a66b-162">Jeśli nie widzisz dostawcy konfiguracji, musisz wykonać kroki opisane w procedurze, [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1a66b-162">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="1a66b-163">Zaimportuj konfigurację metadanych ER, która zawiera metadane z aplikacji, i która jest skonfigurowana do generowania dokumentów elektronicznych dla domeny biznesowej handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="1a66b-163">Import the ER metadata configuration that contains metadata for the application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="1a66b-164">Stworzona konfiguracja metadanych ER została wyeksportowana jako plik XML w opisanej wcześniej procedurze [Przygotuj metadane aplikacji do użycia w RCS](#prepare-application-metadata-that-can-be-used-in-rcs).</span><span class="sxs-lookup"><span data-stu-id="1a66b-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="1a66b-165">Wybierz **Konfiguracje metadanych**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="1a66b-166">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="1a66b-167">Wybierz **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="1a66b-168">Przeglądaj i wybierz plik **Handel zagraniczny metadane.xml**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="1a66b-169">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-169">Select **OK**.</span></span>
    6. <span data-ttu-id="1a66b-170">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1a66b-170">Close the page.</span></span>

4. <span data-ttu-id="1a66b-171">Stwórz model danych konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="1a66b-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="1a66b-172">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="1a66b-173">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="1a66b-174">W rozwijanym menu w polu **Nazwa** wpisz **Model handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="1a66b-175">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="1a66b-176">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="1a66b-177">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="1a66b-178">W polu **Nazwa** wpisz **Źródło**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="1a66b-179">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="1a66b-180">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="1a66b-181">W polu **Nazwa** wpisz **Transakcje**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="1a66b-182">W polu **Kod przedmiotu** wybierz **Lista tabel**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="1a66b-183">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="1a66b-184">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="1a66b-185">W polu **Nazwa** wpisz **Kod towaru**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="1a66b-186">W polu **Typ przedmiotu** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="1a66b-187">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-187">Select **Add**.</span></span>

    9. <span data-ttu-id="1a66b-188">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="1a66b-189">W polu Nazwa wpisz **Kwota zafakturowana**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="1a66b-190">W polu **Typ przedmiotu** wybierz **Rzeczywisty**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="1a66b-191">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-191">Select **Add**.</span></span>

    10. <span data-ttu-id="1a66b-192">Wybierz **Nowe**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="1a66b-193">W polu **Nazwa** wpisz **Data**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="1a66b-194">W polu **Typ przedmiotu** wybierz **Data**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="1a66b-195">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="1a66b-196">Wybierz **Dodaj \> Odniesienia do źródeł**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="1a66b-197">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-197">Select **OK**.</span></span>
    13. <span data-ttu-id="1a66b-198">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-198">Select **Save**.</span></span>
    14. <span data-ttu-id="1a66b-199">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1a66b-199">Close the page.</span></span>
    15. <span data-ttu-id="1a66b-200">Wybierz **Zmień status \> Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="1a66b-201">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-201">Select **OK**.</span></span>

5. <span data-ttu-id="1a66b-202">Stwórz model konfiguracji mapowania:</span><span class="sxs-lookup"><span data-stu-id="1a66b-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="1a66b-203">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="1a66b-204">W rozwijanym polu **Nowe** wpisz **Model mapowania oparty na modelu danych Model handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="1a66b-205">W polu **Nazwa** wpisz **Mapowanie handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="1a66b-206">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="1a66b-207">Na skróconej karcie **Wymagania** wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="1a66b-208">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-208">Select **New**.</span></span>
    7. <span data-ttu-id="1a66b-209">W polu **Wymagany typ komponentu** wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="1a66b-210">Wybierz konfigurację **Metadane handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="1a66b-211">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-211">Select **Save**.</span></span> <span data-ttu-id="1a66b-212">Dodaliśmy odniesienie do wersji pierwszej konfiguracji **Metadane handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="1a66b-213">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="1a66b-214">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1a66b-214">Close the page.</span></span>
    11. <span data-ttu-id="1a66b-215">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="1a66b-216">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="1a66b-217">W widoku drzewa wybierz **Dynamics 365 for Operations \> Tabele**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="1a66b-218">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="1a66b-219">W polu **Nazwa** wpisz **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="1a66b-220">Wybierz tabelę danych **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="1a66b-221">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1a66b-222">Jedynie 2 tabele są proponowane, ponieważ tylko 2 tabele zostały dodane do zestawu metadanych, który jest aktualnie używany.</span><span class="sxs-lookup"><span data-stu-id="1a66b-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="1a66b-223">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="1a66b-224">W widoku drzewa wybierz **Intrastat \> AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="1a66b-225">W widoku drzewa wybierz **Transakcja = Intrastat \> Kwota zafakturowana**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="1a66b-226">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="1a66b-227">W widoku drzewa wybierz **Intrastat \> TransDate**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="1a66b-228">W widoku drzewa wybierz **Transakcja = Intrastat \> Data**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="1a66b-229">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="1a66b-230">W widoku drzewa wybierz **Intrastat \> \>Relacje \> IntrastatCommodity \> Kod**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="1a66b-231">W widoku drzewa wybierz **Transakcja = Intrastat \> Kod towaru**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="1a66b-232">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="1a66b-233">Wybierz **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1a66b-234">Po zakończeniu zatwierdzania, udało nam się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych aplikacji, do której odwołanie znajduje się w konfiguracji metadanych ER.</span><span class="sxs-lookup"><span data-stu-id="1a66b-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="1a66b-235">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-235">Select **Save**.</span></span>

<span data-ttu-id="1a66b-236">Jeśli musisz rozszerzyć istniejący zestaw metadanych, możesz to zrobić w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-236">As you require, you can extend the existing set of metadata in the application.</span></span> <span data-ttu-id="1a66b-237">Następnie można wyeksportować nową ukończoną wersję konfiguracji metadanych ER, zaimportować ją do RCS i zaktualizować wymagania wstępne skonfigurowanej konfiguracji mapowania modelu w odniesieniu do nowej wersji importowanej konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="1a66b-237">You can then export the new completed version of the ER metadata configuration, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="1a66b-238">Ten sposób uzyskiwania informacji o metadanych aplikacji jest jedynym dostępnym dla aplikacji wdrażanych lokalnie (w przypadku gdy używany jest lokalny model danych biznesowych \[LBD\] lub lokalny model wdrażania jest używany dla aplikacji).</span><span class="sxs-lookup"><span data-stu-id="1a66b-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for the application).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="1a66b-239">Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji</span><span class="sxs-lookup"><span data-stu-id="1a66b-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="1a66b-240">Poniższa procedura pokazuje, w jaki sposób użytkownik RCS, który ma rolę **Administratora Systemu** lub **Programisty Elektronicznego Reportowania**, może zaprojektować nowe mapowanie modelu ER przy użyciu metadanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the application.</span></span> <span data-ttu-id="1a66b-241">Metadane aplikacji będą dostępne online za pomocą aplikacji połączonej z RCS.</span><span class="sxs-lookup"><span data-stu-id="1a66b-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="1a66b-242">Przykładowe mapowanie modelu ER zostanie skonfigurowane dla dostępu do transakcji handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="1a66b-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="1a66b-243">Żeby zakończyć tą procedurę, musisz wykonać kroki opisane w procedurze, [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md) w RCS.</span><span class="sxs-lookup"><span data-stu-id="1a66b-243">To complete this procedure, you must first complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="1a66b-244">Jeśli jeszcze nie ukończyłeś [Dostęp do metadanych aplikacji przy użyciu konfiguracji ER](#access-application-metadata-by-using-an-er-configuration) procedury opisanej wcześniej w tym temacie, przejdź do strony [Przewodniki zadań elktronicznego raportowania dla Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739), aby pobrać z następujące pliki konfiguracyjne ER i zapisać je lokalnie: **Handel zagraniczny metadane.xml**, **Handel zagraniczny model.xml** i **Handel zagraniczny mapowanie.xml**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="1a66b-245">Uzyskaj wymagane konfiguracje ER</span><span class="sxs-lookup"><span data-stu-id="1a66b-245">Get required ER configurations</span></span>

<span data-ttu-id="1a66b-246">Jeśli wykonałeś już kroki w procedurze [Uzyskaj dostęp do metadanych aplikacji przy użyciu konfiguracji ER](#access-application-metadata-by-using-an-er-configuration) i masz już wszystkie niezbędne konfiguracje ER (metadane handlu zagranicznego, model i konfiguracje mapowania) w bieżącej instancji RCS.</span><span class="sxs-lookup"><span data-stu-id="1a66b-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="1a66b-247">W takim przypadku pomiń tą procedurę.</span><span class="sxs-lookup"><span data-stu-id="1a66b-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="1a66b-248">Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="1a66b-249">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="1a66b-250">Załaduj pliki konfiguracyjne **handel zagraniczny metadane.xml**, **Handel zagraniczny model.xml**, and **Handel zagraniczny mapowanie.xml** i powtórz następujące czynności dla każdego z nich:</span><span class="sxs-lookup"><span data-stu-id="1a66b-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="1a66b-251">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="1a66b-252">Wybierz **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="1a66b-253">Wybierz **Przeglądaj** i wybierz plik.</span><span class="sxs-lookup"><span data-stu-id="1a66b-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="1a66b-254">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-the-application"></a><span data-ttu-id="1a66b-255">Zarejestruj połączenie z aplikacją</span><span class="sxs-lookup"><span data-stu-id="1a66b-255">Register the connection with the application</span></span>

1. <span data-ttu-id="1a66b-256">Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="1a66b-257">Wybierz **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="1a66b-258">Upewnij się, że skonfigurowana aplikacja jest oparta na Microsoft Azure i ogólnie dostępna dla użytkowników RCS.</span><span class="sxs-lookup"><span data-stu-id="1a66b-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="1a66b-259">Wymagane jest również, aby bieżący użytkownik RCS miał dostęp do konfigurowanej aplikacji i został zarejestrowany jako użytkownik tej aplikacji, odgrywając rolę dającą mu uprawnienia dostępu do metadanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives him or her privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="1a66b-260">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-260">Select **New**.</span></span>
5. <span data-ttu-id="1a66b-261">W polu **Nazwa** wpisz **MyConnectedApp** jako nazwę połączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="1a66b-262">W polu **Aplikacja** wpisz URL aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="1a66b-263">W polu **Dzierżawca** wpisz dostawcę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="1a66b-264">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-264">Select **Save**.</span></span> 
9. <span data-ttu-id="1a66b-265">Po sprawdzeniu połączenia ze skonfigurowaną aplikacją na **Połącz ze zdalną aplikacją** kliknij link **Kliknij tutaj, aby połączyć się z wybraną aplikacją zdalną**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="1a66b-266">Wybierz **Sprawdź połączenie**, żeby sprawdzić dostęp do skonfigurowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="1a66b-267">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-267">Select **Close**.</span></span>

<span data-ttu-id="1a66b-268">Gdy wykonasz tą procedurę i sprawdzenie poprawności połączenia powiedzie się, szczegóły wersji i dzierżawcy zostaną zaktualizowane dla skonfigurowanej aplikacji w bieżącej sieci.</span><span class="sxs-lookup"><span data-stu-id="1a66b-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="1a66b-269">Przejrzyj istniejącą konfigurację mapowania konfiguracji</span><span class="sxs-lookup"><span data-stu-id="1a66b-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="1a66b-270">Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="1a66b-271">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="1a66b-272">W widoku drzewa wybierz **Model handlu zagranicznego \> Handel zagraniczny mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="1a66b-273">Na skróconej karcie wybierz **Wymagania**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a66b-274">Obecnie to mapowanie odnosi się do konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="1a66b-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="1a66b-275">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania danego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="1a66b-276">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-276">Select **Designer**.</span></span>
5. <span data-ttu-id="1a66b-277">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-277">Select **Designer**.</span></span>
6. <span data-ttu-id="1a66b-278">W widoku drzewa wybierz **Dynamics 365 for Operations \> Tabele**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="1a66b-279">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-279">Select **Add root**.</span></span>
8. <span data-ttu-id="1a66b-280">W polu **Tabela** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1a66b-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a66b-281">Obecnie to mapowanie odnosi się do konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="1a66b-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="1a66b-282">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania danego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="1a66b-283">Wybierz **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="1a66b-284">Przypisz daną podłączoną aplikację do mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="1a66b-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="1a66b-285">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-285">Select **Edit**.</span></span>
2. <span data-ttu-id="1a66b-286">W polu **Połączona aplikacja** wybierz aplikaję **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a66b-287">To mapowanie odnosi się do metadanych wybranej połączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="1a66b-288">Jeśli to samo mapowanie odnosi się do konfiguracji metadanych i połączonej aplikacji w tym samym czasie, zostaną użyte metadane połączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a66b-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="1a66b-289">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-289">Select **Designer**.</span></span>
4. <span data-ttu-id="1a66b-290">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-290">Select **Designer**.</span></span>
5. <span data-ttu-id="1a66b-291">W widoku drzewa wybierz **Dynamics 365 for Operations \> Tabele**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="1a66b-292">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-292">Select **Add root**.</span></span>
7. <span data-ttu-id="1a66b-293">W polu **Tabela** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1a66b-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a66b-294">W tym momencie, zaproponowano więcej niż dwie tabele aplikacji, ponieważ to mapowanie wykorzystuje wszystkie metadane połączonej aplikacji, która została do niej przypisana.</span><span class="sxs-lookup"><span data-stu-id="1a66b-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="1a66b-295">Wybierz **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="1a66b-296">Wybierz **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="1a66b-296">Select **Validate**.</span></span>

<span data-ttu-id="1a66b-297">Udało się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych połączonej aplikacji, która została przypisana do tego mapowania.</span><span class="sxs-lookup"><span data-stu-id="1a66b-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="1a66b-298">Jeśli trzeba ocenić ten model mapowania przy użyciu metadanych innej wersji aplikacji, zarejestruj inną połączoną aplikację, przypisz ją do tego mapowania modelu i sprawdź poprawność względem nowych metadanych.</span><span class="sxs-lookup"><span data-stu-id="1a66b-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a66b-299">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1a66b-299">Additional resources</span></span>

<span data-ttu-id="1a66b-300">Możesz również otworzyć instrukcje **Przygotuj metadane aplikacji, które mogą być użyte w RCS** w aplikacji lub **Uzyskaj dostęp do metadanych aplikacji przez konfigurację ER** i **Uzyskaj dostęp do metadanych aplikacji przez inne połączone aplikacje** w RCS.</span><span class="sxs-lookup"><span data-stu-id="1a66b-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in the application as as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="1a66b-301">Te przewodniki mogą zostać pobrane ze strony [Przewodniki Elektronicznego Raportowania dla Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).</span><span class="sxs-lookup"><span data-stu-id="1a66b-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>

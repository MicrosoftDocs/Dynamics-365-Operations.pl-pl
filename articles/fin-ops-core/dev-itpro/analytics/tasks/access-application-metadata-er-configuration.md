---
title: Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER
description: Kroki w tym temacie wyjaśniają, w jaki sposób użytkownik usługi Regulatory configuration service (RCS) może zaprojektować nowe mapowanie modelu Elektronicznego raportowania (ER) przy użyciu metadanych w Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4c7341941df3ba7bf0a0dfeef8cb3009726838e
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142715"
---
# <a name="access-application-metadata-by-using-er-configuration"></a><span data-ttu-id="b7b7e-103">Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="b7b7e-103">Access application metadata by using ER configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b7b7e-104">W następujących krokach wyjaśnimy, w jaki sposób użytkownik usługi Regulatory configuration service (RCS) w roli Administratora Systemu lub Dewelopera elektronicznego raportowania może zaprojektować nowe mapowanie modelu Elektronicznego raportowania (ER) przy użyciu metadanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using the application metadata.</span></span> <span data-ttu-id="b7b7e-105">Dostęp do metadanych aplikacji będzie możliwy za pomocą konfiguracji metadanych ER, która zawiera przykładowy zestaw metadanych umożliwiających dostęp do transakcji handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-105">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span> <span data-ttu-id="b7b7e-106">Aby wykonać te kroki, w RCS musisz najpierw wykonać kroki podane w niniejszym temacie, [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="b7b7e-106">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> <span data-ttu-id="b7b7e-107">Następnie wykonaj kroki opisane w temacie [Przygotowywanie metadanych aplikacji używanych w RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="b7b7e-107">Then complete the steps in the topic, [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b7b7e-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b7b7e-108">Prerequisites</span></span>
1. <span data-ttu-id="b7b7e-109">Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-109">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="b7b7e-110">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="b7b7e-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="b7b7e-111">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="b7b7e-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="import-metadata-configuration"></a><span data-ttu-id="b7b7e-112">Import metadanych konfiguracji</span><span class="sxs-lookup"><span data-stu-id="b7b7e-112">Import metadata configuration</span></span> 
1. <span data-ttu-id="b7b7e-113">Kliknij **Konfiguracja metadanych**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-113">Click **Metadata configurations**.</span></span> 
2. <span data-ttu-id="b7b7e-114">Zaimportuj konfigurację metadanych ER, która zawiera metadane, które zostały skonfigurowane do generowania dokumentów elektronicznych dla handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-114">Import the ER metadata configuration that contains metadata that has been configured to generate electronic documents for foreign trade business.</span></span> <span data-ttu-id="b7b7e-115">Ta konfiguracja metadanych ER została wyeksportowana jako plik XML, podczas gdy kroki opisane w [Przygotuj metadane aplikacji do użycia w RCS](prepare-application-metadata-rcs.md) zostały wypełnione.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-115">This ER metadata configuration has been exported as XML file while the steps in the [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md) procedure have been completed.</span></span> 
3. <span data-ttu-id="b7b7e-116">Kliknij opcję **Wymiana**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-116">Click **Exchange**.</span></span> 
4. <span data-ttu-id="b7b7e-117">Kliknij **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-117">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="b7b7e-118">Kliknij **Przeglądaj** i wybierz plik „Handel zagraniczny metadane.xml”.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-118">Click **Browse** and select the 'Foreign trade metadata.xml' file.</span></span> 
6. <span data-ttu-id="b7b7e-119">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-119">Click **OK**.</span></span> 
7. <span data-ttu-id="b7b7e-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-120">Close the page.</span></span> 

## <a name="create-data-model-configuration"></a><span data-ttu-id="b7b7e-121">Stwórz model danych konfiguracji</span><span class="sxs-lookup"><span data-stu-id="b7b7e-121">Create data model configuration</span></span>
1. <span data-ttu-id="b7b7e-122">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-122">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="b7b7e-123">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-123">Click **Create configuration** to open the drop dialog.</span></span> 
3. <span data-ttu-id="b7b7e-124">W polu **Nazwa** wpisz "Model handlu zagranicznego".</span><span class="sxs-lookup"><span data-stu-id="b7b7e-124">In the **Name** field, type 'Foreign trade model'.</span></span> 
4. <span data-ttu-id="b7b7e-125">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-125">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="b7b7e-126">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-126">Click **Designer**.</span></span> 
6. <span data-ttu-id="b7b7e-127">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-127">Click **New** to open the drop dialog.</span></span> 
7. <span data-ttu-id="b7b7e-128">W polu **Nazwa** wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-128">In the **Name** field, type 'Root'.</span></span> 
8. <span data-ttu-id="b7b7e-129">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-129">Click **Add**.</span></span> 
9. <span data-ttu-id="b7b7e-130">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-130">Click **New** to open the drop dialog.</span></span> 
10.    <span data-ttu-id="b7b7e-131">W polu **Nazwa** wpisz 'Transakcje'.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-131">In the **Name** field, type 'Transaction'.</span></span> 
11.    <span data-ttu-id="b7b7e-132">W polu **Kod przedmiotu** wybierz **Lista tabel**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-132">In the **Item type** field, select **Record list**.</span></span> 
12.    <span data-ttu-id="b7b7e-133">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-133">Click **Add**.</span></span> 
13.    <span data-ttu-id="b7b7e-134">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-134">Click **New** to open the drop dialog.</span></span> 
14.    <span data-ttu-id="b7b7e-135">W polu **Nazwa** wpisz 'Kod towaru'.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-135">In the **Name** field, type 'Commodity code'.</span></span> 
15.    <span data-ttu-id="b7b7e-136">W polu **Typ przedmiotu** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-136">In the **Item type** field, select **String**.</span></span> 
16.    <span data-ttu-id="b7b7e-137">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-137">Click **Add**.</span></span> 
17.    <span data-ttu-id="b7b7e-138">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-138">Click **New** to open the drop dialog.</span></span> 
18.    <span data-ttu-id="b7b7e-139">W polu **Nazwa** wpisz "Kwota zafakturowana".</span><span class="sxs-lookup"><span data-stu-id="b7b7e-139">In the **Name** field, type 'Invoiced amount'.</span></span> 
19.    <span data-ttu-id="b7b7e-140">W polu **Typ przedmiotu** wybierz **Rzeczywisty**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-140">In the **Item type** field, select **Real**.</span></span> 
20.    <span data-ttu-id="b7b7e-141">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-141">Click **Add**.</span></span> 
21.    <span data-ttu-id="b7b7e-142">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-142">Click **New** to open the drop dialog.</span></span> 
22.    <span data-ttu-id="b7b7e-143">W polu **Nazwa** wpisz 'Data'.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-143">In the **Name** field, type 'Date'.</span></span> 
23.    <span data-ttu-id="b7b7e-144">W polu **Typ przedmiotu** wybierz **Data**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-144">In the **Item type** field, select **Date**.</span></span> 
24.    <span data-ttu-id="b7b7e-145">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-145">Click **Add**.</span></span> 
25.    <span data-ttu-id="b7b7e-146">Kliknij **Odniesienia do źródeł"**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-146">Click **Root reference**.</span></span> 
26.    <span data-ttu-id="b7b7e-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-147">Click **OK**.</span></span> 
27.    <span data-ttu-id="b7b7e-148">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-148">Click **Save**.</span></span> 
28.    <span data-ttu-id="b7b7e-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-149">Close the page.</span></span> 
29.    <span data-ttu-id="b7b7e-150">Kliknij **Zmień status**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-150">Click **Change status**.</span></span> 
30.    <span data-ttu-id="b7b7e-151">Naciśnij **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-151">Click **Complete**.</span></span> 
31.    <span data-ttu-id="b7b7e-152">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-152">Click **OK**.</span></span> 

## <a name="create-model-mapping-configuration"></a><span data-ttu-id="b7b7e-153">Stwórz model konfiguracji mapowania</span><span class="sxs-lookup"><span data-stu-id="b7b7e-153">Create model mapping configuration</span></span> 
1. <span data-ttu-id="b7b7e-154">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-154">Click **Create configuration** to open the drop dialog.</span></span> 
2. <span data-ttu-id="b7b7e-155">W polu **Nowe** wpisz "Model mapowania oparty na modelu danych Model handlu zagranicznego".</span><span class="sxs-lookup"><span data-stu-id="b7b7e-155">In the **New** field, enter 'Model Mapping based on data model Foreign trade model'.</span></span> 
3. <span data-ttu-id="b7b7e-156">W polu **Nazwa** wpisz "Mapowanie handlu zagranicznego".</span><span class="sxs-lookup"><span data-stu-id="b7b7e-156">In the **Name** field, type 'Foreign trade mapping'.</span></span> 
4. <span data-ttu-id="b7b7e-157">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-157">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="b7b7e-158">Rozwiń sekcję **Wymagania**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-158">Expand the **Prerequisites** section.</span></span> 
6. <span data-ttu-id="b7b7e-159">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-159">Click **Edit**.</span></span> 
7. <span data-ttu-id="b7b7e-160">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-160">Click **New**.</span></span> 
8. <span data-ttu-id="b7b7e-161">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-161">In the list, mark the selected row.</span></span> 
9. <span data-ttu-id="b7b7e-162">W polu **Wymagany typ komponentu** wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-162">In the **Prerequisite component type** field, select **Configuration**.</span></span> 
10.    <span data-ttu-id="b7b7e-163">Wyierz konfigurację **Metadane handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-163">Select **Foreign trade metadata** configuration.</span></span> 
11.    <span data-ttu-id="b7b7e-164">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-164">Click **Save**.</span></span> 
12.    <span data-ttu-id="b7b7e-165">Dodaliśmy odniesienie do wersji pierwszej konfiguracji „Metadane handlu zagranicznego”.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-165">We added the reference to the version 1 of the 'Foreign trade metadata' configuration.</span></span> <span data-ttu-id="b7b7e-166">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-166">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 
13.    <span data-ttu-id="b7b7e-167">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-167">Close the page.</span></span> 
14.    <span data-ttu-id="b7b7e-168">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-168">Click **Designer**.</span></span> 
15.    <span data-ttu-id="b7b7e-169">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-169">Click **Designer**.</span></span> 
16.    <span data-ttu-id="b7b7e-170">W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
17.    <span data-ttu-id="b7b7e-171">Kliknij **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-171">Click **Add root**.</span></span> 
18.    <span data-ttu-id="b7b7e-172">W polu **Nazwa** wpisz 'Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-172">In the **Name** field, type 'Intrastat'.</span></span> 
19.    <span data-ttu-id="b7b7e-173">Wybierz tabelę danych **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-173">Select **Intrastat** table records.</span></span> 
20.    <span data-ttu-id="b7b7e-174">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-174">Click **OK**.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7b7e-175">Jedynie 2 tabele zostały zaproponowane, ponieważ tylko 2 tabele zostały dodane do zestawu metadanych, który jest aktualnie używany.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-175">The only 2 tables were offered as the only 2 tables were added into the set of metadata which is currently in use.</span></span> 

21.    <span data-ttu-id="b7b7e-176">Kliknij **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-176">Click **Bind**.</span></span> 
22.    <span data-ttu-id="b7b7e-177">W widoku drzewa otwórz **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-177">In the tree, expand **Intrastat**.</span></span> 
23.    <span data-ttu-id="b7b7e-178">W widoku drzewa wybierz **Intrastat\AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-178">In the tree, select **Intrastat\AmountMST**.</span></span> 
24.    <span data-ttu-id="b7b7e-179">W widoku drzewa rozwiń **Transakcja = Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-179">In the tree, expand **Transaction = Intrastat**.</span></span> 
25.    <span data-ttu-id="b7b7e-180">W widoku drzewa wybierz **Transakcja = Intrastat\Kwota zafakturowana**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-180">In the tree, select **Transaction = Intrastat\Invoiced amount**.</span></span> 
26.    <span data-ttu-id="b7b7e-181">Kliknij **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-181">Click **Bind**.</span></span> 
27.    <span data-ttu-id="b7b7e-182">W widoku drzewa wybierz **Intrastat\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-182">In the tree, select **Intrastat\TransDate**.</span></span> 
28.    <span data-ttu-id="b7b7e-183">W widoku drzewa wybierz **Transakcja = Intrastat\Data**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-183">In the tree, select **Transaction = Intrastat\Date**.</span></span> 
29.    <span data-ttu-id="b7b7e-184">Kliknij **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-184">Click **Bind**.</span></span> 
30.    <span data-ttu-id="b7b7e-185">W widoku drzewa rozwiń **Intrastat\>Relacje**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-185">In the tree, expand **Intrastat\>Relations**.</span></span> 
31.    <span data-ttu-id="b7b7e-186">W widoku drzewa rozwiń **Intrastat\>Relacje\IntrastatCommodity**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-186">In the tree, expand **Intrastat\>Relations\IntrastatCommodity**.</span></span> 
32.    <span data-ttu-id="b7b7e-187">W widoku drzewa rozwiń **Intrastat\>Relacje\IntrastatCommodity\Kod**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-187">In the tree, select **Intrastat\>Relations\IntrastatCommodity\Code**.</span></span> 
33.    <span data-ttu-id="b7b7e-188">W widoku drzewa wybierz **Transakcja = Intrastat\Kod towaru**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-188">In the tree, select **Transaction = Intrastat\Commodity code**.</span></span> 
34.    <span data-ttu-id="b7b7e-189">Kliknij **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-189">Click **Bind**.</span></span> 
35.    <span data-ttu-id="b7b7e-190">Kliknij **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-190">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7b7e-191">Udało nam się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych aplikacji, do której odwołanie znajduje się w konfiguracji metadanych ER.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-191">We have successfully bound elements of data model with items of data sources that are described by using details of application metadata from the referred ER metadata configuration.</span></span> 
36.    <span data-ttu-id="b7b7e-192">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-192">Click **Save**.</span></span> 
37.    <span data-ttu-id="b7b7e-193">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-193">Close the page.</span></span> 
38.    <span data-ttu-id="b7b7e-194">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-194">Close the page.</span></span> 
39.    <span data-ttu-id="b7b7e-195">W razie potrzeby można rozszerzyć istniejący zbiór metadanych, a następnie wyeksportować nową skompletowaną wersję konfiguracji metadanych programu ER</span><span class="sxs-lookup"><span data-stu-id="b7b7e-195">When needed, you can extend the existing set of metadata and then export the new completed version of ER metadata configuration.</span></span> <span data-ttu-id="b7b7e-196">Następnie można zaimportować ją do RCS i zaktualizować wymagania wstępne skonfigurowanego mapowania modeli odnosząc się do nowej wersji zaimportowanej konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-196">You can then import it to RCS, and update the prerequisites of the configured model mapping configuration referring to a new version of imported metadata configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7b7e-197">Ten sposób uzyskiwania informacji o metadanych aplikacji jest jedynym dostępnym dla aplikacji wdrażanych lokalnie (w przypadku gdy używany jest lokalny model danych biznesowych (LBD) lub lokalny model wdrażania).</span><span class="sxs-lookup"><span data-stu-id="b7b7e-197">This way of getting information about application metadata is the only one available for locally deployed applications (when local business data (LBD), or on-premises, deployment model is used).</span></span>
        

---
title: Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji
description: Kroki w tym temacie wyjaśniają, w jaki sposób użytkownik usługi Regulatory configuration service (RCS) może zaprojektować nowe mapowanie modelu Elektronicznego raportowania (ER) przy użyciu metadanych w Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
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
ms.openlocfilehash: 8d3581f6ae2d91b9648da3ba69e6b1d36cd08196
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727059"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="e3dc7-103">Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji</span><span class="sxs-lookup"><span data-stu-id="e3dc7-103">Access application metadata by using connected applications</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3dc7-104">Kroki w tym temacie wyjaśniają, w jaki sposób użytkownik usługi Regulatory configuration service (RCS) może zaprojektować nowe mapowanie modelu Elektronicznego raportowania (ER) przy użyciu metadanych w Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="e3dc7-105">Metadane aplikacji będą dostępne online za pomocą aplikacji połączonej z RCS.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="e3dc7-106">Przykładowe mapowanie modelu ER zostanie skonfigurowane do dostępu do transakcji handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="e3dc7-107">Aby wykonać te kroki, w RCS musisz najpierw wykonać kroki podane w niniejszym temacie, [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="e3dc7-108">Jeśli nie wykonałeś wszystkich podanych kroków [Dostęp do metadanych aplikacji przy użyciu konfiguracji ER](access-application-metadata-er-configuration.md), przejdź do strony [Przykłady elektronicznego raportowania](https://go.microsoft.com/fwlink/?linkid=862266), aby pobrać i zapisać następujące konfiguracje ER: Handel zagraniczny metadane.xml; Model handlu zagranicznego.xml; Mapowanie handlu zagranicznego.xml, a następnie wykonaj kroki procedury.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3dc7-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="e3dc7-109">Prerequisites</span></span>
1. <span data-ttu-id="e3dc7-110">Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="e3dc7-111">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="e3dc7-112">Jeśli nie widzisz dostawcy konfiguracji, musisz wykonać kroki w procedurze, [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-112">If you don’t see this configuration provider, complete the steps in the procedure [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="e3dc7-113">Uzyskaj wymagane konfiguracje ER</span><span class="sxs-lookup"><span data-stu-id="e3dc7-113">Get required ER configurations</span></span>
1. <span data-ttu-id="e3dc7-114">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="e3dc7-115">Jeśli wykonałeś już kroki w procedurze [(RCS) Uzyskaj dostęp do metadanych aplikacji przy użyciu konfiguracji ER](access-application-metadata-er-configuration.md) i masz już wszystkie niezbędne konfiguracje ER (metadane handlu zagranicznego, model i konfiguracje mapowania) w bieżącej instancji RCS.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-115">If you already completed the steps in the [(RCS) Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="e3dc7-116">Możesz pominąć wszystkie pozostałe kroki tego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="e3dc7-117">Kliknij **Zmień**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="e3dc7-118">Kliknij **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="e3dc7-119">Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny metadane.xml**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="e3dc7-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-120">Click **OK**.</span></span> 
7. <span data-ttu-id="e3dc7-121">Kliknij **Zmień**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="e3dc7-122">Kliknij **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="e3dc7-123">Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny model.xml**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="e3dc7-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-124">Click **OK**.</span></span> 
11. <span data-ttu-id="e3dc7-125">Kliknij **Zmień**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="e3dc7-126">Kliknij **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="e3dc7-127">Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny mapowanie.xml**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="e3dc7-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-128">Click **OK**.</span></span> 

## <a name="register-connected-dynamics-365-for-finance-and-operations-application"></a><span data-ttu-id="e3dc7-129">Zarejestruj połączoną z Dynamics 365 for Finance and Operations aplikację</span><span class="sxs-lookup"><span data-stu-id="e3dc7-129">Register connected Dynamics 365 for Finance and Operations application</span></span>
1. <span data-ttu-id="e3dc7-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-130">Close the page.</span></span> 
2. <span data-ttu-id="e3dc7-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-131">Close the page.</span></span> 
3. <span data-ttu-id="e3dc7-132">Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="e3dc7-133">Kliknij **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="e3dc7-134">Upewnij się, że skonfigurowana aplikacja jest oparta na Azurze i dostępna dla bieżącego użytkownika RCS.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-134">Make sure that the configured application is Azura based and accessible for the current RCS user.</span></span> <span data-ttu-id="e3dc7-135">Wymagane jest również, aby bieżący użytkownik RCS miał dostęp do wybranej aplikacji i został zarejestrowany jako użytkownik tej aplikacji, odgrywając rolę dającą mu uprawnienia dostępu do metadanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving him privileges to access application’s metadata.</span></span> 
6. <span data-ttu-id="e3dc7-136">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-136">Click **New**.</span></span> 
7. <span data-ttu-id="e3dc7-137">W polu **Nazwa** wpisz 'MyConnectedApp'.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="e3dc7-138">W polu **Aplikacja** wpisz 'https:// mycompany.operations.dynamics.com'.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="e3dc7-139">W polu **Dzierżawca** wpisz ‘mycompany.onmicrosoft.com’.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-139">In the **Tenant** field, type ‘mycompany.onmicrosoft.com’.</span></span> 
10. <span data-ttu-id="e3dc7-140">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-140">Click **Save**.</span></span> 
11. <span data-ttu-id="e3dc7-141">Po sprawdzeniu połączenia ze skonfigurowaną aplikacją na stronie **Połącz ze zdalną aplikacją** kliknij link **Kliknij tutaj, aby połączyć się z wybraną aplikacją zdalną**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="e3dc7-142">Kliknij **Sprawdź połączenie**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="e3dc7-143">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-143">Click **Close**.</span></span> 
14. <span data-ttu-id="e3dc7-144">Gdy sprawdzenie poprawności połączenia powiedzie się, szczegóły wersji i dzierżawcy zostaną zaktualizowane dla skonfigurowanej aplikacji w bieżącej sieci.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="e3dc7-145">Przejrzyj istniejącą konfigurację mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="e3dc7-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="e3dc7-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-146">Close the page.</span></span> 
2. <span data-ttu-id="e3dc7-147">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="e3dc7-148">W widoku drzewa otwórz **Model handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="e3dc7-149">W widoku drzewa wybierz **Model handlu zagranicznego\Handel zagraniczny mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="e3dc7-150">Rozwiń sekcję **Wymagania**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-150">Expand the **Prerequisites** section.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3dc7-151">Obecnie to mapowanie odnosi się do konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="e3dc7-152">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="e3dc7-153">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="e3dc7-154">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="e3dc7-155">W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="e3dc7-156">Kliknij **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="e3dc7-157">W polu **Tabela** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-157">In the **Table** field, enter or select a value.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3dc7-158">Obecnie to mapowanie odnosi się do konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="e3dc7-159">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="e3dc7-160">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="e3dc7-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-161">Close the page.</span></span> 
13. <span data-ttu-id="e3dc7-162">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="e3dc7-163">Przypisz podłączoną aplikację do mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="e3dc7-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="e3dc7-164">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="e3dc7-165">Wybierz aplikację **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-165">Select **MyConnectedApp** application.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3dc7-166">Obecnie to mapowanie odnosi się do metadanych wybranej połączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="e3dc7-167">Gdy to samo mapowanie odnosi się do konfiguracji metadanych i połączonej aplikacji w tym samym czasie, zostaną użyte metadane połączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="e3dc7-168">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="e3dc7-169">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="e3dc7-170">W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="e3dc7-171">Kliknij **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="e3dc7-172">W polu **Tabela** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-172">In the **Table** field, enter or select a value.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3dc7-173">Zaproponowano więcej niż dwie tabele aplikacji, ponieważ to mapowanie wykorzystuje wszystkie metadane połączonej aplikacji, która została do niej przypisana.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="e3dc7-174">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="e3dc7-175">Kliknij **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-175">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3dc7-176">Udało nam się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych połączonej aplikacji, która została przypisana do tego mapowania.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="e3dc7-177">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-177">Close the page.</span></span> 
11. <span data-ttu-id="e3dc7-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-178">Close the page.</span></span> 

<span data-ttu-id="e3dc7-179">Gdy trzeba ocenić ten model mapowania przy użyciu metadanych innej wersji aplikacji, zarejestruj inną połączoną aplikację, przypisz ją do tego mapowania modelu i sprawdź poprawność względem nowych metadanych.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>

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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 751ac21dc056373e1cd89a5149bf38789134e0cc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682148"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="d2777-103">Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji</span><span class="sxs-lookup"><span data-stu-id="d2777-103">Access application metadata by using connected applications</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d2777-104">Kroki w tym temacie wyjaśniają, w jaki sposób użytkownik usługi Regulatory configuration service (RCS) może zaprojektować nowe mapowanie modelu Elektronicznego raportowania (ER) przy użyciu metadanych w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d2777-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Finance and Operations.</span></span> <span data-ttu-id="d2777-105">Metadane aplikacji będą dostępne online za pomocą aplikacji połączonej z RCS.</span><span class="sxs-lookup"><span data-stu-id="d2777-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="d2777-106">Przykładowe mapowanie modelu ER zostanie skonfigurowane do dostępu do transakcji handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="d2777-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="d2777-107">Aby wykonać te kroki, w RCS należy najpierw wykonać kroki w procedurze [Tworzenie dostawców konfiguracji i oznacz je jako aktywne](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="d2777-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="d2777-108">Jeśli nie wykonałeś wszystkich podanych kroków [Dostęp do metadanych aplikacji przy użyciu konfiguracji ER](access-application-metadata-er-configuration.md), przejdź do strony [Przykłady elektronicznego raportowania](https://go.microsoft.com/fwlink/?linkid=862266), aby pobrać i zapisać następujące konfiguracje ER: Handel zagraniczny metadane.xml; Model handlu zagranicznego.xml; Mapowanie handlu zagranicznego.xml, a następnie wykonaj kroki procedury.</span><span class="sxs-lookup"><span data-stu-id="d2777-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d2777-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d2777-109">Prerequisites</span></span>
1. <span data-ttu-id="d2777-110">Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="d2777-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="d2777-111">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="d2777-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="d2777-112">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="d2777-112">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="d2777-113">Uzyskaj wymagane konfiguracje ER</span><span class="sxs-lookup"><span data-stu-id="d2777-113">Get required ER configurations</span></span>
1. <span data-ttu-id="d2777-114">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="d2777-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="d2777-115">Jeśli wykonałeś już kroki w procedurze [Uzyskaj dostęp do metadanych aplikacji przy użyciu konfiguracji ER](access-application-metadata-er-configuration.md) i masz już wszystkie niezbędne konfiguracje ER (metadane handlu zagranicznego, model i konfiguracje mapowania) w bieżącej instancji RCS.</span><span class="sxs-lookup"><span data-stu-id="d2777-115">If you already completed the steps in the [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="d2777-116">Możesz pominąć wszystkie pozostałe kroki tego zadania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="d2777-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="d2777-117">Kliknij **Zmień**</span><span class="sxs-lookup"><span data-stu-id="d2777-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="d2777-118">Kliknij **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="d2777-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="d2777-119">Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny metadane.xml**.</span><span class="sxs-lookup"><span data-stu-id="d2777-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="d2777-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2777-120">Click **OK**.</span></span> 
7. <span data-ttu-id="d2777-121">Kliknij **Zmień**</span><span class="sxs-lookup"><span data-stu-id="d2777-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="d2777-122">Kliknij **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="d2777-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="d2777-123">Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny model.xml**.</span><span class="sxs-lookup"><span data-stu-id="d2777-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="d2777-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2777-124">Click **OK**.</span></span> 
11. <span data-ttu-id="d2777-125">Kliknij **Zmień**</span><span class="sxs-lookup"><span data-stu-id="d2777-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="d2777-126">Kliknij **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="d2777-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="d2777-127">Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny mapowanie.xml**.</span><span class="sxs-lookup"><span data-stu-id="d2777-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="d2777-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2777-128">Click **OK**.</span></span> 

## <a name="register-a-connected-application"></a><span data-ttu-id="d2777-129">Zarejestruj połączoną aplikację</span><span class="sxs-lookup"><span data-stu-id="d2777-129">Register a connected application</span></span>
1. <span data-ttu-id="d2777-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2777-130">Close the page.</span></span> 
2. <span data-ttu-id="d2777-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2777-131">Close the page.</span></span> 
3. <span data-ttu-id="d2777-132">Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="d2777-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="d2777-133">Kliknij **Połączone aplikacje**.</span><span class="sxs-lookup"><span data-stu-id="d2777-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="d2777-134">Upewnij się, że skonfigurowana aplikacja jest oparta na Azure i dostępna dla bieżącego użytkownika RCS.</span><span class="sxs-lookup"><span data-stu-id="d2777-134">Make sure that the configured application is Azure based and accessible for the current RCS user.</span></span> <span data-ttu-id="d2777-135">Wymagane jest również, aby bieżący użytkownik RCS miał dostęp do wybranej aplikacji i został zarejestrowany jako jej użytkownik z rolą dającą mu uprawnienia dostępu do metadanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d2777-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving them privileges to access application's metadata.</span></span> 
6. <span data-ttu-id="d2777-136">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d2777-136">Click **New**.</span></span> 
7. <span data-ttu-id="d2777-137">W polu **Nazwa** wpisz 'MyConnectedApp'.</span><span class="sxs-lookup"><span data-stu-id="d2777-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="d2777-138">W polu **Aplikacja** wpisz 'https:// mycompany.operations.dynamics.com'.</span><span class="sxs-lookup"><span data-stu-id="d2777-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="d2777-139">W polu **Dzierżawca** wpisz „mycompany.onmicrosoft.com”.</span><span class="sxs-lookup"><span data-stu-id="d2777-139">In the **Tenant** field, type 'mycompany.onmicrosoft.com'.</span></span> 
10. <span data-ttu-id="d2777-140">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d2777-140">Click **Save**.</span></span> 
11. <span data-ttu-id="d2777-141">Po sprawdzeniu połączenia ze skonfigurowaną aplikacją na stronie **Połącz ze zdalną aplikacją** kliknij link **Kliknij tutaj, aby połączyć się z wybraną aplikacją zdalną**.</span><span class="sxs-lookup"><span data-stu-id="d2777-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="d2777-142">Kliknij **Sprawdź połączenie**.</span><span class="sxs-lookup"><span data-stu-id="d2777-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="d2777-143">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="d2777-143">Click **Close**.</span></span> 
14. <span data-ttu-id="d2777-144">Gdy sprawdzenie poprawności połączenia powiedzie się, szczegóły wersji i dzierżawcy zostaną zaktualizowane dla skonfigurowanej aplikacji w bieżącej sieci.</span><span class="sxs-lookup"><span data-stu-id="d2777-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="d2777-145">Przejrzyj istniejącą konfigurację mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="d2777-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="d2777-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2777-146">Close the page.</span></span> 
2. <span data-ttu-id="d2777-147">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="d2777-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="d2777-148">W widoku drzewa otwórz **Model handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="d2777-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="d2777-149">W widoku drzewa wybierz **Model handlu zagranicznego\Handel zagraniczny mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="d2777-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="d2777-150">Rozwiń sekcję **Wymagania**.</span><span class="sxs-lookup"><span data-stu-id="d2777-150">Expand the **Prerequisites** section.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d2777-151">Obecnie to mapowanie odnosi się do konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="d2777-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="d2777-152">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="d2777-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="d2777-153">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="d2777-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="d2777-154">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="d2777-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="d2777-155">W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**.</span><span class="sxs-lookup"><span data-stu-id="d2777-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="d2777-156">Kliknij **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="d2777-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="d2777-157">W polu **Tabela** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2777-157">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d2777-158">Obecnie to mapowanie odnosi się do konfiguracji metadanych.</span><span class="sxs-lookup"><span data-stu-id="d2777-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="d2777-159">Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania.</span><span class="sxs-lookup"><span data-stu-id="d2777-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="d2777-160">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="d2777-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="d2777-161">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2777-161">Close the page.</span></span> 
13. <span data-ttu-id="d2777-162">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2777-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="d2777-163">Przypisz podłączoną aplikację do mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="d2777-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="d2777-164">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="d2777-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="d2777-165">Wybierz aplikację **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="d2777-165">Select **MyConnectedApp** application.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d2777-166">Obecnie to mapowanie odnosi się do metadanych wybranej połączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d2777-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="d2777-167">Gdy to samo mapowanie odnosi się do konfiguracji metadanych i połączonej aplikacji w tym samym czasie, zostaną użyte metadane połączonej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d2777-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="d2777-168">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="d2777-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="d2777-169">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="d2777-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="d2777-170">W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**.</span><span class="sxs-lookup"><span data-stu-id="d2777-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="d2777-171">Kliknij **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="d2777-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="d2777-172">W polu **Tabela** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2777-172">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d2777-173">Zaproponowano więcej niż dwie tabele aplikacji, ponieważ to mapowanie wykorzystuje wszystkie metadane połączonej aplikacji, która została do niej przypisana.</span><span class="sxs-lookup"><span data-stu-id="d2777-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="d2777-174">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="d2777-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="d2777-175">Kliknij **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="d2777-175">Click **Validate**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d2777-176">Udało nam się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych połączonej aplikacji, która została przypisana do tego mapowania.</span><span class="sxs-lookup"><span data-stu-id="d2777-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="d2777-177">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2777-177">Close the page.</span></span> 
11. <span data-ttu-id="d2777-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2777-178">Close the page.</span></span> 

<span data-ttu-id="d2777-179">Gdy trzeba ocenić ten model mapowania przy użyciu metadanych innej wersji aplikacji, zarejestruj inną połączoną aplikację, przypisz ją do tego mapowania modelu i sprawdź poprawność względem nowych metadanych.</span><span class="sxs-lookup"><span data-stu-id="d2777-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>

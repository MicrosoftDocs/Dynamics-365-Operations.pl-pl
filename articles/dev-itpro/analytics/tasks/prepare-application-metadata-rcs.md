---
title: Przygotowywanie metadanych aplikacji używanych w RCS
description: W tym temacie opisano sposób, w jaki użytkownik może utworzyć nową konfigurację sprawozdawczości elektronicznej (ER), zawierającą metadane aplikacji finansowej i operacyjnej i służące do projektowania konfiguracji mapowania modeli ER w usłudze Regulatory configuration service (RCS).
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
ms.openlocfilehash: c1bd2298240fa789762a350e90888201c5a7ce45
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/04/2019
ms.locfileid: "1726990"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="55b42-103">Przygotowywanie metadanych aplikacji używanych w RCS</span><span class="sxs-lookup"><span data-stu-id="55b42-103">Prepare application metadata to be used in RCS</span></span>
[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55b42-104">W tym temacie opisano sposób, w jaki użytkownik w roli administratora systemu lub programisty raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą metadane aplikacji Microsoft Dynamics 365 for Finance and Operations w celu projektowania konfiguracji mapowania modeli ER w usłudze Regulatory configuration service (RCS).</span><span class="sxs-lookup"><span data-stu-id="55b42-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains Microsoft Dynamics 365 for Finance and Operations application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="55b42-105">Ta konfiguracja będzie używana do projektowania konfiguracji mapowania przykładowego modelu ER w celu uzyskania dostępu do transakcji handlu zagranicznego. </span><span class="sxs-lookup"><span data-stu-id="55b42-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="55b42-106">W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Kroki te można wykonać w dowolnej firmie.</span><span class="sxs-lookup"><span data-stu-id="55b42-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="55b42-107">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze [Tworzenie dostawców konfiguracji i oznacz je jako aktywne](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="55b42-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55b42-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="55b42-108">Prerequisites</span></span>
1.  <span data-ttu-id="55b42-109">Wybierz kolejno opcje **Administrowanie organizacją** > **Obszary robocze** > **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="55b42-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.  <span data-ttu-id="55b42-110">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="55b42-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="55b42-111">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="55b42-111">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.  <span data-ttu-id="55b42-112">Kliknij przycisk **Konfiguracje metadanych**.</span><span class="sxs-lookup"><span data-stu-id="55b42-112">Click **Metadata configurations**.</span></span> 
4.  <span data-ttu-id="55b42-113">Załóżmy, że oprogramowanie RCS zostanie użyte do zaprojektowania rozwiązania ER dla aplikacji finansowej i operacyjnej, która będzie generować dokumenty elektroniczne zawierające informacje z domeny biznesowej handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="55b42-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="55b42-114">Aby określić mapowanie między modelem danych ER a źródłami wymaganych danych, w oprogramowaniu RCS musi mieć dostęp do metadanych aplikacji Finanse i operacje.</span><span class="sxs-lookup"><span data-stu-id="55b42-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="55b42-115">Dlatego w ramach projektowania rozwiązania ER konfigurowana jest nowa konfiguracja metadanych ER zawierającą wszystkie metadane, które są obecnie wymagane w przypadku generowania raportów ER dla wybranej domeny biznesowej.</span><span class="sxs-lookup"><span data-stu-id="55b42-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="55b42-116">Dodaj konfigurację metadanych</span><span class="sxs-lookup"><span data-stu-id="55b42-116">Add metadata configuration</span></span> 
1.  <span data-ttu-id="55b42-117">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="55b42-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.  <span data-ttu-id="55b42-118">W polu **Nazwa** wpisz „Metadane handlu zagranicznego”.</span><span class="sxs-lookup"><span data-stu-id="55b42-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.  <span data-ttu-id="55b42-119">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="55b42-119">Click **Create configuration**.</span></span> 
4.  <span data-ttu-id="55b42-120">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="55b42-120">Click **Designer**.</span></span> 
5.  <span data-ttu-id="55b42-121">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="55b42-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="55b42-122">Można wybrać wszystkie metadane dla całej aplikacji lub dla wybranych modeli lub wybranych modułów.</span><span class="sxs-lookup"><span data-stu-id="55b42-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="55b42-123">Należy pamiętać, że w tym przypadku zostaną automatycznie dodane następujące metadane: tabele rekordów, wyliczenia i rozszerzone typy danych.</span><span class="sxs-lookup"><span data-stu-id="55b42-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="55b42-124">Gdy są potrzebne dodatkowe typy metadanych, należy je dodać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="55b42-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="55b42-125">Istnieją metadane związane z transakcjami handlu zagranicznego przez wybranie elementów metadanych ręcznie.</span><span class="sxs-lookup"><span data-stu-id="55b42-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.  <span data-ttu-id="55b42-126">Kliknij opcję **Dodaj źródło danych**.</span><span class="sxs-lookup"><span data-stu-id="55b42-126">Click **Add data source**.</span></span> 
7.  <span data-ttu-id="55b42-127">Kliknij **Rekordy tabeli**.</span><span class="sxs-lookup"><span data-stu-id="55b42-127">Click **Table records**.</span></span> 
8.  <span data-ttu-id="55b42-128">Użyj szybkiego filtru, aby wyfiltrować pole **Nazwa** według wartości „intrastat”.</span><span class="sxs-lookup"><span data-stu-id="55b42-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.  <span data-ttu-id="55b42-129">Wybierz tabelę **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="55b42-129">Select the **Intrastat** table record.</span></span> 
10. <span data-ttu-id="55b42-130">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55b42-130">Click **OK**.</span></span>
  
<span data-ttu-id="55b42-131">Dodano informacje metadanych dotyczące tabeli rekordów Intrastat.</span><span class="sxs-lookup"><span data-stu-id="55b42-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11. <span data-ttu-id="55b42-132">W drzewie rozwiń **Tabele rekordów Intrastat**\>**Relacje**.</span><span class="sxs-lookup"><span data-stu-id="55b42-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12. <span data-ttu-id="55b42-133">W drzewie wybierz pozycję **Tabela rekordów Intrastat**\>**Relacje\IntrastatCommodity (tabela rekordów EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="55b42-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>   
13. <span data-ttu-id="55b42-134">Kliknij przycisk **Dodaj metadane**</span><span class="sxs-lookup"><span data-stu-id="55b42-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="55b42-135">Metadane dotyczące relacji wymaganych dla wybranych tabel muszą zostać dodane ręcznie.</span><span class="sxs-lookup"><span data-stu-id="55b42-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16. <span data-ttu-id="55b42-136">Kliknij opcję **Dodaj źródło danych**.</span><span class="sxs-lookup"><span data-stu-id="55b42-136">Click **Add data source**.</span></span> 
17. <span data-ttu-id="55b42-137">Kliknij przycisk **Wyliczenie**.</span><span class="sxs-lookup"><span data-stu-id="55b42-137">Click **Enumeration**.</span></span> 
18. <span data-ttu-id="55b42-138">Użyj szybkiego filtru, aby wyfiltrować pole **Nazwa** według wartości „IntrastatKierunek".</span><span class="sxs-lookup"><span data-stu-id="55b42-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19. <span data-ttu-id="55b42-139">Wybierz rekord **IntrastatDirection wyliczenia**.</span><span class="sxs-lookup"><span data-stu-id="55b42-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20. <span data-ttu-id="55b42-140">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55b42-140">Click **OK**.</span></span> 
21. <span data-ttu-id="55b42-141">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="55b42-141">Click **Save**.</span></span>  
22. <span data-ttu-id="55b42-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="55b42-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="55b42-143">Zakończ wersję roboczą konfiguracji metadanych</span><span class="sxs-lookup"><span data-stu-id="55b42-143">Complete the draft version of metadata configuration</span></span>
1.  <span data-ttu-id="55b42-144">Kliknij przycisk **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="55b42-144">Click **Change status**.</span></span> 
2.  <span data-ttu-id="55b42-145">Kliknij przycisk **Wykonaj.**</span><span class="sxs-lookup"><span data-stu-id="55b42-145">Click **Complete**.</span></span> 
3.  <span data-ttu-id="55b42-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55b42-146">Click **OK**.</span></span> 
4.  <span data-ttu-id="55b42-147">Wybierz ukończoną wersję **1**.</span><span class="sxs-lookup"><span data-stu-id="55b42-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="55b42-148">Eksportowanie ukończonej wersji konfiguracji metadanych z aplikacji jako pliku XML</span><span class="sxs-lookup"><span data-stu-id="55b42-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.  <span data-ttu-id="55b42-149">Kliknij opcję **Wymiana**.</span><span class="sxs-lookup"><span data-stu-id="55b42-149">Click **Exchange**.</span></span> 
2.  <span data-ttu-id="55b42-150">Kliknij przycisk **Eksportuj jako plik XML**.</span><span class="sxs-lookup"><span data-stu-id="55b42-150">Click **Export as XML file**.</span></span> 
3.  <span data-ttu-id="55b42-151">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="55b42-151">Click **OK**.</span></span> 
    
<span data-ttu-id="55b42-152">Utworzona konfiguracja metadanych ER została zapisana jako plik XML, który można importować do RCS i użyć jako źródło informacji o metadanych dla domeny biznesowej w handlu zagranicznym w module Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55b42-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain in Finance and Operations.</span></span> <span data-ttu-id="55b42-153">Na podstawie tych informacji można określić mapowanie między metadanymi aplikacji a modelem danych ER.</span><span class="sxs-lookup"><span data-stu-id="55b42-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>

---
title: Integracja z klientem Microsoft Project
description: "Planowanie harmonogramu projektu i zarządzanie nim może być skomplikowane, dlatego menedżerowie projektów powinni używać narzędzi, które pomogą wykonywać to zadanie. Integracja z klientem programu Microsoft Project umożliwia otwieranie struktury podziału pracy projektu oraz zarządzanie nią."
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 48feb0182c623714b2acffafc42016c0471ba6c1
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="microsoft-project-client-integration"></a><span data-ttu-id="14734-104">Integracja z klientem Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="14734-104">Microsoft Project client integration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14734-105">Planowanie harmonogramu projektu i zarządzanie nim może być skomplikowane, dlatego menedżerowie projektów powinni używać narzędzi, które pomogą wykonywać to zadanie.</span><span class="sxs-lookup"><span data-stu-id="14734-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="14734-106">Integracja z klientem programu Microsoft Project umożliwia otwieranie struktury podziału pracy projektu oraz zarządzanie nią.</span><span class="sxs-lookup"><span data-stu-id="14734-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="14734-107">Menedżer projektu może publikować wszelkie zmiany z powrotem w strukturze podziału pracy projektu w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="14734-107">The project manager can publish any changes back to the Finance and Operations project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="14734-108">Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations z lipcową aktualizacją, należy zainstalować poprawki KB 4054797 i 4055884.</span><span class="sxs-lookup"><span data-stu-id="14734-108">If you are using Microsoft Dynamics 365 for Finance and Operations, July update, you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="14734-109">Konfigurowanie dodatku klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="14734-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="14734-110">Aby umożliwić integrację z klientem programu Microsoft Project, w aplikacji klienckiej Microsoft Project u użytkownika musi być zainstalowany dodatek usługi Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="14734-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="14734-111">W tym celu należy otworzyć **obszar roboczy Zarządzanie projektami**.</span><span class="sxs-lookup"><span data-stu-id="14734-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="14734-112">•   W obszarze roboczym w sekcji **Łącza** > **Ustawienia** kliknij przycisk **Konfiguruj dodatek klienta programu Project** .</span><span class="sxs-lookup"><span data-stu-id="14734-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="14734-113">•   Kliknij przycisk **Otwórz**, następnie po pojawieniu się monitu kliknij przycisk **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="14734-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="14734-114">Otwieranie i edytowanie istniejącej wersji roboczej struktury podziału pracy w kliencie programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="14734-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="14734-115">Jeżeli projekt w programie Finance and Operations ma już utworzoną strukturę podziału pracy, można ją otworzyć w aplikacji klienckiej Microsoft Project, o ile tylko struktura jest wersją roboczą.</span><span class="sxs-lookup"><span data-stu-id="14734-115">If a project in Finance and Operations already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="14734-116">Aby otworzyć strukturę ze strony **Projekt**, na karcie **Plan** kliknij łącze **Otwórz w programie Microsoft Project**. Tę stronę można również otworzyć z poziomu aplikacji klienckiej Microsoft Project, klikając przycisk **Otwórz** na karcie **Microsoft Dynamics 365**. Wybierz opcję **Firma**, a następnie na liście pozycję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="14734-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="14734-117">Jeśli używasz przeglądarki Internet Explorer, trzeba będzie kliknąć przycisk **Zapisz** i ręcznie otworzyć plik z lokalizacji, do której zostanie pobrany.</span><span class="sxs-lookup"><span data-stu-id="14734-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="14734-118">Można też kliknąć opcję **Zapisz i otwórz** i otworzyć plik w kliencie programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="14734-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="14734-119">Podczas zapisywania nie zmieniaj nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="14734-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="14734-120">Przed wprowadzeniem jakichkolwiek zmian w pliku przy użyciu klienta programu Microsoft Project należy go wyewidencjonować. Kliknij przycisk **Wyewidencjonuj** na karcie **Microsoft Dynamics 365**. Uniemożliwi to innym użytkownikom edytowanie struktury podziału pracy w tym samym czasie z poziomu programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="14734-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance and Operations at the same time.</span></span> <span data-ttu-id="14734-121">Aby opublikować strukturę podziału pracy po wprowadzeniu wszelkich zmian, na karcie **Microsoft Dynamics 365** kliknij przycisk **Zaewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="14734-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="14734-122">Jeśli zespół projektu został już dodany do projektu w programie Finance and Operations, na liście zasobów zostaną wstawieni członkowie zespołu.</span><span class="sxs-lookup"><span data-stu-id="14734-122">If a project team has already been added to the project in Finance and Operations, the resource list will be populated with the team members.</span></span> <span data-ttu-id="14734-123">Jeśli zespół projektu nie został jeszcze dodany do projektu, można wybrać zasoby i zbudować zespół w kliencie programu Microsoft Project, klikając przycisk **Zasoby** znajdujący się na karcie **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="14734-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="14734-124">Następujące dane zostaną zsynchronizowane z powrotem z programem Finance and Operations w ramach procesu ewidencjonowania:</span><span class="sxs-lookup"><span data-stu-id="14734-124">The following data will be synced back to Finance and Operations as part of the check in process:</span></span>

<span data-ttu-id="14734-125">•   Nazwa zadania</span><span class="sxs-lookup"><span data-stu-id="14734-125">•   Task name</span></span>

<span data-ttu-id="14734-126">•   Data rozpoczęcia</span><span class="sxs-lookup"><span data-stu-id="14734-126">•   Start date</span></span>

<span data-ttu-id="14734-127">•   Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="14734-127">•   Finish date</span></span>

<span data-ttu-id="14734-128">•   Zdarzenia poprzedzające</span><span class="sxs-lookup"><span data-stu-id="14734-128">•   Predecessors</span></span>

<span data-ttu-id="14734-129">•   Nazwy zasobów</span><span class="sxs-lookup"><span data-stu-id="14734-129">•   Resource names</span></span>

<span data-ttu-id="14734-130">•   Kategoria</span><span class="sxs-lookup"><span data-stu-id="14734-130">•   Category</span></span>

<span data-ttu-id="14734-131">•   Kategoria zasobów</span><span class="sxs-lookup"><span data-stu-id="14734-131">•   Resource category</span></span>

<span data-ttu-id="14734-132">•   Godziny pracy</span><span class="sxs-lookup"><span data-stu-id="14734-132">•   Work hours</span></span>

<span data-ttu-id="14734-133">•   Notatki</span><span class="sxs-lookup"><span data-stu-id="14734-133">•   Notes</span></span>

<span data-ttu-id="14734-134">•   Priorytet</span><span class="sxs-lookup"><span data-stu-id="14734-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="14734-135">Jeśli do pliku klienta programu Microsoft Project zostaną dodane jakiekolwiek inne kolumny, nie zostaną one zapisane w pliku i nie pojawią się po ponownym otwarciu pliku.</span><span class="sxs-lookup"><span data-stu-id="14734-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="14734-136">Tworzenie struktury podziału pracy dla istniejącego projektu przy użyciu klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="14734-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="14734-137">Aby utworzyć nową strukturę podziału pracy przy użyciu klienta programu Microsoft Project, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="14734-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="14734-138">Otwórz klienta programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="14734-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="14734-139">Na karcie **Microsoft Dynamics 365** kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="14734-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="14734-140">Wybierz dla projektu wartość w polu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="14734-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="14734-141">Wybierz opcję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="14734-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="14734-142">Na karcie **Microsoft Dynamics 365** kliknij przycisk **Wyewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="14734-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="14734-143">Gotowy masz wszystko przygotowane do publikowania w programie Finance and Operations, na karcie **Microsoft Dynamics 365** kliknij przycisk **Zaewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="14734-143">When ready to publish to Finance and Operations, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="14734-144">Zastępowanie istniejącej struktury podziału pracy dla istniejącego projektu przy użyciu klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="14734-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="14734-145">Aby utworzyć nową strukturę podziału pracy za pomocą klienta programu Microsoft Project i zastąpić nią istniejącą strukturę podziału pracy dla istniejącego projektu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="14734-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="14734-146">Otwórz klienta programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="14734-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="14734-147">Utwórz harmonogram w kliencie programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="14734-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="14734-148">Na karcie **Microsoft Dynamics 365** kliknij kolejno opcje **Zapisz zmiany** > **Zastąp istniejący projekt**.</span><span class="sxs-lookup"><span data-stu-id="14734-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="14734-149">Wybierz dla projektu wartość w polu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="14734-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="14734-150">Wybierz opcję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="14734-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="14734-151">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="14734-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="14734-152">Tworzenie nowego projektu z klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="14734-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="14734-153">Otwórz klienta programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="14734-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="14734-154">Utwórz harmonogram w kliencie programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="14734-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="14734-155">Na karcie **Microsoft Dynamics 365** kliknij kolejno opcje **Zapisz zmiany** > **Zapisz do nowego projektu**.</span><span class="sxs-lookup"><span data-stu-id="14734-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="14734-156">Wybierz dla projektu wartość w polu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="14734-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="14734-157">W razie potrzeby wypełnij pole **Identyfikatora projektu**.</span><span class="sxs-lookup"><span data-stu-id="14734-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="14734-158">Wypełnij pole **Nazwa projektu**.</span><span class="sxs-lookup"><span data-stu-id="14734-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="14734-159">Wybierz wartości w polach **Typ projektu**, **Grupa projektów** i **Identyfikator umowy dotyczącej projektu**.</span><span class="sxs-lookup"><span data-stu-id="14734-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="14734-160">Alternatywnie można utworzyć nową umowę na projekt, klikając przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="14734-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="14734-161">Wybierz wartość w polu **Kalendarz** na potrzeby pozyskiwania zasobów.</span><span class="sxs-lookup"><span data-stu-id="14734-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="14734-162">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="14734-162">Click **OK**.</span></span>


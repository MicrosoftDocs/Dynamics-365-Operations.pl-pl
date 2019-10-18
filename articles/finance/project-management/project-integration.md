---
title: Integracja z klientem Microsoft Project
description: Planowanie harmonogramu projektu i zarządzanie nim może być skomplikowane, dlatego menedżerowie projektów powinni używać narzędzi, które pomogą wykonywać to zadanie. Integracja z klientem programu Microsoft Project umożliwia otwieranie struktury podziału pracy projektu oraz zarządzanie nią.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 610990612d5fb38025bf39cc648d0c9572da37b6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174987"
---
# <a name="microsoft-project-client-integration"></a><span data-ttu-id="44b0d-104">Integracja z klientem Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="44b0d-104">Microsoft Project client integration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44b0d-105">Planowanie harmonogramu projektu i zarządzanie nim może być skomplikowane, dlatego menedżerowie projektów powinni używać narzędzi, które pomogą wykonywać to zadanie.</span><span class="sxs-lookup"><span data-stu-id="44b0d-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="44b0d-106">Integracja z klientem programu Microsoft Project umożliwia otwieranie struktury podziału pracy projektu oraz zarządzanie nią.</span><span class="sxs-lookup"><span data-stu-id="44b0d-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="44b0d-107">Menedżer projektu może publikować wszelkie zmiany z powrotem w strukturze podziału pracy projektu w Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="44b0d-107">The project manager can publish any changes back to the Dynamics 365 Finance project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="44b0d-108">Jeśli używasz wersji po aktualizacji z lipca (wersja 10.0.4), musisz zainstalować aktualizacje KB 4054797 i 4055884.</span><span class="sxs-lookup"><span data-stu-id="44b0d-108">If you are using the July update (version 10.0.4), you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="44b0d-109">Konfigurowanie dodatku klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="44b0d-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="44b0d-110">Aby umożliwić integrację z klientem programu Microsoft Project, w aplikacji klienckiej Microsoft Project u użytkownika musi być zainstalowany dodatek usługi Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="44b0d-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="44b0d-111">W tym celu należy otworzyć **obszar roboczy Zarządzanie projektami**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="44b0d-112">•   W obszarze roboczym w sekcji **Łącza** > **Ustawienia** kliknij przycisk **Konfiguruj dodatek klienta programu Project** .</span><span class="sxs-lookup"><span data-stu-id="44b0d-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="44b0d-113">•   Kliknij przycisk **Otwórz**, następnie po pojawieniu się monitu kliknij przycisk **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="44b0d-114">Otwieranie i edytowanie istniejącej wersji roboczej struktury podziału pracy w kliencie programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="44b0d-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="44b0d-115">Jeżeli projekt w Dynamics 365 Finance ma już utworzoną strukturę podziału pracy, można ją otworzyć w aplikacji Microsoft Project Client, o ile tylko struktura jest wersją roboczą.</span><span class="sxs-lookup"><span data-stu-id="44b0d-115">If a project in Dynamics 365 Finance already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="44b0d-116">Aby otworzyć strukturę ze strony **Projekt**, na karcie **Plan** kliknij łącze **Otwórz w programie Microsoft Project**. Tę stronę można również otworzyć z poziomu aplikacji klienckiej Microsoft Project, klikając przycisk **Otwórz** na karcie **Microsoft Dynamics 365**. Wybierz opcję **Firma**, a następnie na liście pozycję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="44b0d-117">Jeśli używasz przeglądarki Internet Explorer, trzeba będzie kliknąć przycisk **Zapisz** i ręcznie otworzyć plik z lokalizacji, do której zostanie pobrany.</span><span class="sxs-lookup"><span data-stu-id="44b0d-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="44b0d-118">Można też kliknąć opcję **Zapisz i otwórz** i otworzyć plik w kliencie programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="44b0d-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="44b0d-119">Podczas zapisywania nie zmieniaj nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="44b0d-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="44b0d-120">Przed wprowadzeniem jakichkolwiek zmian w pliku przy użyciu programu Microsoft Project Client należy go wyewidencjonować. Kliknij przycisk **Wyewidencjonuj** na karcie **Microsoft Dynamics 365**. Uniemożliwi to innym użytkownikom edytowanie struktury podziału pracy w tym samym czasie z poziomu programu Finance.</span><span class="sxs-lookup"><span data-stu-id="44b0d-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance at the same time.</span></span> <span data-ttu-id="44b0d-121">Aby opublikować strukturę podziału pracy po wprowadzeniu wszelkich zmian, na karcie **Microsoft Dynamics 365** kliknij przycisk **Zaewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="44b0d-122">Jeśli zespół projektu został już dodany do projektu w programie Finance, na liście zasobów zostaną wstawieni członkowie zespołu.</span><span class="sxs-lookup"><span data-stu-id="44b0d-122">If a project team has already been added to the project in Finance, the resource list will be populated with the team members.</span></span> <span data-ttu-id="44b0d-123">Jeśli zespół projektu nie został jeszcze dodany do projektu, można wybrać zasoby i zbudować zespół w kliencie programu Microsoft Project, klikając przycisk **Zasoby** znajdujący się na karcie **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="44b0d-124">Następujące dane zostaną zsynchronizowane z powrotem z programem Finance w ramach procesu ewidencjonowania:</span><span class="sxs-lookup"><span data-stu-id="44b0d-124">The following data will be synced back to Finance as part of the check-in process:</span></span>

<span data-ttu-id="44b0d-125">•   Nazwa zadania</span><span class="sxs-lookup"><span data-stu-id="44b0d-125">•   Task name</span></span>

<span data-ttu-id="44b0d-126">•   Data rozpoczęcia</span><span class="sxs-lookup"><span data-stu-id="44b0d-126">•   Start date</span></span>

<span data-ttu-id="44b0d-127">•   Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="44b0d-127">•   Finish date</span></span>

<span data-ttu-id="44b0d-128">•   Zdarzenia poprzedzające</span><span class="sxs-lookup"><span data-stu-id="44b0d-128">•   Predecessors</span></span>

<span data-ttu-id="44b0d-129">•   Nazwy zasobów</span><span class="sxs-lookup"><span data-stu-id="44b0d-129">•   Resource names</span></span>

<span data-ttu-id="44b0d-130">•   Kategoria</span><span class="sxs-lookup"><span data-stu-id="44b0d-130">•   Category</span></span>

<span data-ttu-id="44b0d-131">•   Kategoria zasobów</span><span class="sxs-lookup"><span data-stu-id="44b0d-131">•   Resource category</span></span>

<span data-ttu-id="44b0d-132">•   Godziny pracy</span><span class="sxs-lookup"><span data-stu-id="44b0d-132">•   Work hours</span></span>

<span data-ttu-id="44b0d-133">•   Notatki</span><span class="sxs-lookup"><span data-stu-id="44b0d-133">•   Notes</span></span>

<span data-ttu-id="44b0d-134">•   Priorytet</span><span class="sxs-lookup"><span data-stu-id="44b0d-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="44b0d-135">Jeśli do pliku klienta programu Microsoft Project zostaną dodane jakiekolwiek inne kolumny, nie zostaną one zapisane w pliku i nie pojawią się po ponownym otwarciu pliku.</span><span class="sxs-lookup"><span data-stu-id="44b0d-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="44b0d-136">Tworzenie struktury podziału pracy dla istniejącego projektu przy użyciu klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="44b0d-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="44b0d-137">Aby utworzyć nową strukturę podziału pracy przy użyciu klienta programu Microsoft Project, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="44b0d-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="44b0d-138">Otwórz klienta programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="44b0d-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="44b0d-139">Na karcie **Microsoft Dynamics 365** kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="44b0d-140">Wybierz dla projektu wartość w polu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="44b0d-141">Wybierz opcję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="44b0d-142">Kliknij **Wyewidencjonuj** na karcie **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="44b0d-143">Gotowy masz wszystko przygotowane do publikowania w programie Finance, na karcie **Microsoft Dynamics 365** kliknij przycisk **Zaewidencjonuj**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-143">When ready to publish to Finance, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="44b0d-144">Zastępowanie istniejącej struktury podziału pracy dla istniejącego projektu przy użyciu klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="44b0d-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="44b0d-145">Aby utworzyć nową strukturę podziału pracy za pomocą klienta programu Microsoft Project i zastąpić nią istniejącą strukturę podziału pracy dla istniejącego projektu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="44b0d-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="44b0d-146">Otwórz klienta programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="44b0d-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="44b0d-147">Utwórz harmonogram w kliencie programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="44b0d-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="44b0d-148">Na karcie **Microsoft Dynamics 365** kliknij kolejno opcje **Zapisz zmiany** > **Zastąp istniejący projekt**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="44b0d-149">Wybierz dla projektu wartość w polu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="44b0d-150">Wybierz opcję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="44b0d-151">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="44b0d-152">Tworzenie nowego projektu z klienta programu Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="44b0d-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="44b0d-153">Otwórz klienta programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="44b0d-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="44b0d-154">Utwórz harmonogram w kliencie programu Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="44b0d-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="44b0d-155">Na karcie **Microsoft Dynamics 365** kliknij kolejno opcje **Zapisz zmiany** > **Zapisz do nowego projektu**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="44b0d-156">Wybierz dla projektu wartość w polu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="44b0d-157">W razie potrzeby wypełnij pole **Identyfikatora projektu**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="44b0d-158">Wypełnij pole **Nazwa projektu**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="44b0d-159">Wybierz wartości w polach **Typ projektu**, **Grupa projektów** i **Identyfikator umowy dotyczącej projektu**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="44b0d-160">Alternatywnie można utworzyć nową umowę na projekt, klikając przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="44b0d-161">Wybierz wartość w polu **Kalendarz** na potrzeby pozyskiwania zasobów.</span><span class="sxs-lookup"><span data-stu-id="44b0d-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="44b0d-162">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-162">Click **OK**.</span></span>

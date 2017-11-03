---
title: "Łączenie z systemem Pomocy"
description: "W tym temacie opisano składniki systemu Pomocy w programie Microsoft Dynamics 365 for Finance and Operations, sposoby ich podłączania oraz podstawowe zasady tworzenia pomocy niestandardowej."
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c0942b66859da3659be49b19986bfd146ac43130
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="connect-the-help-system"></a><span data-ttu-id="c209a-103">Łączenie z systemem Pomocy</span><span class="sxs-lookup"><span data-stu-id="c209a-103">Connect the Help system</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c209a-104">W tym temacie opisano składniki systemu Pomocy w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c209a-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="c209a-105">Omówiono sposoby podłączania tych składników oraz podstawowe zasady tworzenia pomocy niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="c209a-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span> 

## <a name="help-architecture"></a><span data-ttu-id="c209a-106">Architektura modułu Pomoc</span><span class="sxs-lookup"><span data-stu-id="c209a-106">Help architecture</span></span>
<span data-ttu-id="c209a-107">Poniższa ilustracja pokazuje części systemu Pomocy w programie Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c209a-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="c209a-108">Wewnętrzny system Pomocy ściąga artykuły z witryny programu Dynamics 365 for Finance and Operations pod adresem https://docs.microsoft.com oraz przewodniki po zadaniach przechowywane w narzędziu do modelowania procesów biznesowych w usłudze Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c209a-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span> 
> [!NOTE]
> <span data-ttu-id="c209a-109">Funkcje oznaczone w diagramie gwiazdką (\*) są planowane, ale jeszcze niedostępne.</span><span class="sxs-lookup"><span data-stu-id="c209a-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span> <span data-ttu-id="c209a-110">[![Architektura modułu Pomoc](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="c209a-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>


## <a name="connecting-the-help-system"></a><span data-ttu-id="c209a-111">Łączenie z systemem Pomocy</span><span class="sxs-lookup"><span data-stu-id="c209a-111">Connecting the Help system</span></span>
> [!NOTE]
> <span data-ttu-id="c209a-112">Karta **Przewodniki po zadaniach** jest obecnie niedostępna w programach Microsoft Dynamics 365 for Talent i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="c209a-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="c209a-113">Obecnie pracujemy nad włączeniem tej funkcjonalności w przyszłym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="c209a-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="c209a-114">Przewodniki po zadaniach w sekcji Rozpoczęcie pracy w module Talent pozostają dostępne i oferują podstawowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="c209a-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="c209a-115">Ponadto jest dostępna pomoc dla procedur w witrynie docs.microsoft.com ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) dla aplikacji Retail i Talent.</span><span class="sxs-lookup"><span data-stu-id="c209a-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) for both Retail and Talent.</span></span>
 

<span data-ttu-id="c209a-116">Za pomocą strony **Parametry systemowe** administratorzy łączą elementy systemu Pomocy i je implementują.</span><span class="sxs-lookup"><span data-stu-id="c209a-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span> <span data-ttu-id="c209a-117">[![Formularz Parametry systemowe z ustawieniami Pomocy](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na stronie **Parametry systemowe** wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="c209a-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c209a-118">Podczas pierwszego otwierania karty **Pomoc** należy utworzyć połączenie z usługą Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="c209a-118">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="c209a-119">Kliknij łącze na środku formularza, poczekaj na nawiązanie połączenia, zamknij okno dialogowe i kliknij przycisk **OK**, co spowoduje przejście do strony **Parametry systemu**.[![Łączenie z usługą LCS](./media/connect-to-lcs-crop-1024x365.png "Łączenie z usługą LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="c209a-119">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1.  <span data-ttu-id="c209a-120">Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.</span><span class="sxs-lookup"><span data-stu-id="c209a-120">Select the Lifecycle Services project to connect to.</span></span>
2.  <span data-ttu-id="c209a-121">Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.</span><span class="sxs-lookup"><span data-stu-id="c209a-121">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
    - <span data-ttu-id="c209a-122">Pakiety zawartości Microsoft dla programu Finance and Operations znajdują się w najnowszej ujednoliconej bibliotece APQC dla programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c209a-122">For Finance and Operations, for Microsoft content, select the most recent APQC Unified Library for Finance and Operations.</span></span> 
    - <span data-ttu-id="c209a-123">Dla programu Retail opublikujemy bibliotekę w najbliższej przyszłości.</span><span class="sxs-lookup"><span data-stu-id="c209a-123">For Retail, we will be releasing a library in the near future.</span></span> 
    - <span data-ttu-id="c209a-124">Nie trzeba wybierać biblioteki dla programu Talent — połączenie z właściwą biblioteką jest tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="c209a-124">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span> 

3.  <span data-ttu-id="c209a-125">Ustaw kolejność wyświetlania bibliotek BPM.</span><span class="sxs-lookup"><span data-stu-id="c209a-125">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="c209a-126">Określa kolejność wyświetlania nagrań z bibliotek w okienku **pomocy**.</span><span class="sxs-lookup"><span data-stu-id="c209a-126">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="c209a-127">Po wykonaniu tych kroków można utworzyć okienko **Pomoc** i kliknąć kartę **Przewodniki zadań**. Zobaczysz przewodniki zadań mające zastosowanie do strony aktualnie wyświetlonej w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c209a-127">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you’re currently on in Finance and Operations.</span></span> <span data-ttu-id="c209a-128">Jeśli nie zostaną znalezione żadne przewodniki po zadaniach, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c209a-128">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="c209a-129">Wyświetlanie przetłumaczonych przewodników po zadaniach</span><span class="sxs-lookup"><span data-stu-id="c209a-129">Showing translated task guides</span></span>

<span data-ttu-id="c209a-130">Przetłumaczone przewodniki po zadaniach po raz pierwszy umieszczono w ujednoliconej bibliotece APQC w wydaniu z maja 2016 r. oraz w bibliotece ułatwiającej rozpoczęcie pracy.</span><span class="sxs-lookup"><span data-stu-id="c209a-130">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="c209a-131">Aby wyświetlić przetłumaczone przewodniki po zadaniach w pomocy w programie Finance and Operations, upewnij się, że masz połączenie z biblioteką z maja.</span><span class="sxs-lookup"><span data-stu-id="c209a-131">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="c209a-132">Język wyświetlania przetłumaczonego przewodnika po zadaniu jest kontrolowany przez każdego użytkownika w ustawieniach języka w oknie **Opcje** &gt; **Preferencje**.</span><span class="sxs-lookup"><span data-stu-id="c209a-132">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c209a-133">Mimo że przetłumaczono wiele przewodników po zadaniach, obecnie klient programu Finance and Operations nie pokazuje nazw przetłumaczonych przewodników.</span><span class="sxs-lookup"><span data-stu-id="c209a-133">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="c209a-134">Ponadto w majowej bibliotece są dostępne tłumaczenia tylko przewodników po zadaniach opublikowanych w lutym 2016 r.</span><span class="sxs-lookup"><span data-stu-id="c209a-134">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="c209a-135">Opublikujemy zaktualizowaną bibliotekę z dodatkowymi tłumaczeniami.</span><span class="sxs-lookup"><span data-stu-id="c209a-135">We will release an updated library with additional translations.</span></span>
> -   <span data-ttu-id="c209a-136">Jeśli przewodnik po zadaniu został przetłumaczony, po otwarciu przewodnika jego cały tekst będzie wyświetlany w wybranym języku.</span><span class="sxs-lookup"><span data-stu-id="c209a-136">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> -   <span data-ttu-id="c209a-137">Jeśli przewodnik po zadaniu nie został jeszcze przetłumaczony, po otwarciu przewodnika tylko część tekstu (formanty) będzie wyświetlana w wybranym języku.</span><span class="sxs-lookup"><span data-stu-id="c209a-137">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="c209a-138">Tworzenie pomocy niestandardowej</span><span class="sxs-lookup"><span data-stu-id="c209a-138">Creating custom help</span></span>
<span data-ttu-id="c209a-139">W programie Finance and Operations i aplikacji Retail można utworzyć pomoc niestandardową poprzez utworzenie nagrań zadań odpowiadających konkretnemu wdrożeniu i zapisanie ich w bibliotece procesów biznesowych LCS.</span><span class="sxs-lookup"><span data-stu-id="c209a-139">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="c209a-140">Nie można tworzyć niestandardowych przewodników po zadaniach dla modułu Talent.</span><span class="sxs-lookup"><span data-stu-id="c209a-140">You cannot create custom task guides for Talent.</span></span> 

<span data-ttu-id="c209a-141">W przypadku partnerów: jeśli zostanie podniesiony poziom biblioteki do firmowej i zostanie ona uwzględniona w rozwiązaniu, będzie dostępna dla klientów.</span><span class="sxs-lookup"><span data-stu-id="c209a-141">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="c209a-142">Można również utworzyć kopię ujednoliconej globalnej biblioteki APQC, a następnie otworzyć tę kopię, otwierać z niej nagrania zadań, modyfikować je i zapisywać nagrania z wprowadzonymi zmianami.</span><span class="sxs-lookup"><span data-stu-id="c209a-142">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="c209a-143">Aby uzyskać więcej informacji, zobacz [Jak utworzyć nagrania zadań do użycia w dokumentacji lub na szkoleniach](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="c209a-143">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

<a name="see-also"></a><span data-ttu-id="c209a-144">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="c209a-144">See also</span></span>
--------

[<span data-ttu-id="c209a-145">Omówienie Pomocy</span><span class="sxs-lookup"><span data-stu-id="c209a-145">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="c209a-146">Omówienie rejestratora zadań</span><span class="sxs-lookup"><span data-stu-id="c209a-146">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="c209a-147">Jak utworzyć nagrania zadań do użycia w dokumentacji lub na szkoleniach</span><span class="sxs-lookup"><span data-stu-id="c209a-147">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)






---
title: Konfigurowanie środowiska pomocy dla aplikacji Finance and Operations
description: Ten temat zawiera informacje dotyczące składników systemu pomocy dla niektórych aplikacji Microsoft Dynamics 365. Omówiono również sposób łączenia tych aplikacji oraz przedstawiono podsumowanie procesu tworzenia pomocy niestandardowej.
author: margoc
manager: AnnBe
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0495bbc008ed1760b98c2c1ace63fc4a8b1ab5cc
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694428"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a><span data-ttu-id="63f79-104">Konfigurowanie środowiska pomocy dla aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="63f79-104">Configure the Help experience for Finance and Operations apps</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63f79-105">W tym temacie znajduje się omówienie składników systemu pomocy dla aplikacji Finance and Operations, takich jak Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="63f79-105">In this topic, you will find an overview of the components of the Help system for Finance and Operations apps, such as Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources.</span></span> <span data-ttu-id="63f79-106">W tym temacie omówiono również sposób łączenia tych składników oraz przedstawiono podsumowanie procesu tworzenia pomocy niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="63f79-106">The topic also explains how to connect these components and provides a summary of the process for creating custom Help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="63f79-107">Architektura modułu Pomoc</span><span class="sxs-lookup"><span data-stu-id="63f79-107">Help architecture</span></span>

<span data-ttu-id="63f79-108">Aplikacje Finance and Operations oferują omówienia koncepcyjne i inne tematy opublikowane w witrynie [https://docs.microsoft.com/dynamics365](/dynamics365/).</span><span class="sxs-lookup"><span data-stu-id="63f79-108">Finance and Operations apps include conceptual overviews and other topics that are published to the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span> <span data-ttu-id="63f79-109">Następnie można uzyskać dostęp do tej zawartości za pomocą okienka **Pomoc** w danym produkcie.</span><span class="sxs-lookup"><span data-stu-id="63f79-109">This content can then be accessed from the in-product **Help** pane.</span></span> <span data-ttu-id="63f79-110">Poniższa ilustracja pokazuje części Pomocy systemu.</span><span class="sxs-lookup"><span data-stu-id="63f79-110">The following illustration shows the parts of the Help system.</span></span>

<span data-ttu-id="63f79-111">[![Architektura modułu Pomoc](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="63f79-111">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

<span data-ttu-id="63f79-112">System pomocy w danym produkcie pobiera artykuły z witryny docs.microsoft.com i innych połączonych witryn internetowych.</span><span class="sxs-lookup"><span data-stu-id="63f79-112">The in-product Help system pulls articles from docs.microsoft.com and other connected websites.</span></span> <span data-ttu-id="63f79-113">Pobierane są również przewodniki zadań przechowywane w Narzędziu do modelowania procesów biznesowych (BPM) w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="63f79-113">It also pulls in task guides that are stored in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="adding-task-guides"></a><span data-ttu-id="63f79-114">Dodawanie przewodników zadań</span><span class="sxs-lookup"><span data-stu-id="63f79-114">Adding task guides</span></span>

> [!NOTE]
> <span data-ttu-id="63f79-115">Karta **Przewodniki zadań** nie jest obecnie dostępna w aplikacjach Human Resources i Commerce.</span><span class="sxs-lookup"><span data-stu-id="63f79-115">The **Task guides** tab isn't currently available in Human Resources or Commerce.</span></span> <!--We are currently working to enable this functionality in a future release.--> <span data-ttu-id="63f79-116">Natomiast przewodniki po zadaniach w sekcji Rozpoczęcie pracy w module Human Resources pozostają dostępne i oferują podstawowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="63f79-116">However, the task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="63f79-117">Pomoc dotycząca procedur aplikacji Human Resources oraz Commerce jest dostępna w witrynie [https://docs.microsoft.com/dynamics365](/dynamics365/).</span><span class="sxs-lookup"><span data-stu-id="63f79-117">For both Human Resources and Commerce, procedural Help is available on the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span>

<span data-ttu-id="63f79-118">Na stronie **Parametry systemowe** administratorzy systemu mogą konfigurować dostęp do odpowiednich bibliotek przewodników zadań na potrzeby implementacji.</span><span class="sxs-lookup"><span data-stu-id="63f79-118">On the **System parameters** page, system admins can configure access to the relevant task guide libraries for an implementation.</span></span>

> [!NOTE]
> - <span data-ttu-id="63f79-119">Aby skonfigurować pomoc, musisz się zalogować przy użyciu konta w tej samej dzierżawie, w której jest wdrożona aplikacja.</span><span class="sxs-lookup"><span data-stu-id="63f79-119">To configure Help, you must sign in by using an account in the same tenant as the tenant where the app is deployed.</span></span>
> - <span data-ttu-id="63f79-120">Nie można połączyć się z biblioteką LCS z wystąpienia aplikacji działającej na lokalnym wirtualnym dysku twardym (VHD).</span><span class="sxs-lookup"><span data-stu-id="63f79-120">An LCS library can't be connected from an instance of the app that is running on a local virtual hard drive (VHD).</span></span>

<span data-ttu-id="63f79-121">[![Formularz Parametry systemu z ustawieniami Pomocy](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="63f79-121">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="63f79-122">Aby skonfigurować przewodniki zadań dla rozwiązania, wykonaj poniższe kroki na stronie **Parametry systemowe**.</span><span class="sxs-lookup"><span data-stu-id="63f79-122">To configure task guides for a solution, follow these steps on the **System parameters** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63f79-123">Podczas pierwszego otwierania karty **Pomoc** należy utworzyć połączenie z usługą Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="63f79-123">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="63f79-124">Wybierz link w środku formularza, poczekaj na nawiązanie połączenia, zamknij okno dialogowe i wybierz przycisk **OK**, co spowoduje przejście do formularza **Parametry systemowe**.</span><span class="sxs-lookup"><span data-stu-id="63f79-124">Be sure to select the link in the middle of the form, wait for the connection, close the dialog box, and then select **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="63f79-125">[![Nawiązywanie połączenia z usługą LCS](./media/connect-to-lcs-crop-1024x365.png "Nawiązywanie połączenia z usługą LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="63f79-125">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="63f79-126">Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.</span><span class="sxs-lookup"><span data-stu-id="63f79-126">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="63f79-127">Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.</span><span class="sxs-lookup"><span data-stu-id="63f79-127">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="63f79-128">Ustaw kolejność wyświetlania bibliotek BPM.</span><span class="sxs-lookup"><span data-stu-id="63f79-128">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="63f79-129">Kolejność wyświetlania to porządek, w jakim nagrania zadań z bibliotek będą pojawiać się w okienku **Pomoc**.</span><span class="sxs-lookup"><span data-stu-id="63f79-129">The display order defines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="63f79-130">Po wykonaniu tych kroków można utworzyć okienko **Pomoc** i wybrać kartę **Przewodniki zadań**. Zobaczysz przewodniki zadań mające zastosowanie do strony aktualnie wyświetlonej w aplikacjach Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="63f79-130">After you complete these steps, you can open the **Help** pane and select the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="63f79-131">Jeśli nie zostaną znalezione żadne przewodniki po zadaniach, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="63f79-131">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="63f79-132">Wyświetlanie przetłumaczonych przewodników po zadaniach</span><span class="sxs-lookup"><span data-stu-id="63f79-132">Showing translated task guides</span></span>

<span data-ttu-id="63f79-133">Przetłumaczone przewodniki po zadaniach po raz pierwszy opublikowano w ujednoliconej bibliotece APQC w wydaniu z maja 2016 r. oraz w bibliotece ułatwiającej rozpoczęcie pracy.</span><span class="sxs-lookup"><span data-stu-id="63f79-133">Translated task guides were first released in the May 2016 APQC Unified Library and in the Getting Started library.</span></span> <span data-ttu-id="63f79-134">Aby wyświetlić pomoc przetłumaczonego przewodnika zadania, upewnij się, że rozwiązanie Dynamics 365 zostało połączone z biblioteką z maja 2016 r.</span><span class="sxs-lookup"><span data-stu-id="63f79-134">To view localized task guide Help, make sure that your Dynamics 365 solution is connected to the May 2016 library.</span></span> <span data-ttu-id="63f79-135">Użytkownicy mogą zmienić język wyświetlonego przewodnika zadania, zmieniając ustawienia języka w obszarze **Opcje** &gt; **Preferencje**.</span><span class="sxs-lookup"><span data-stu-id="63f79-135">Users can change the language that a task guide appears in by changing the language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="63f79-136">Mimo że przetłumaczono wiele przewodników zadań, klient obecnie nie pokazuje nazw przetłumaczonych przewodników zadań.</span><span class="sxs-lookup"><span data-stu-id="63f79-136">Although many task guides have been translated, the client doesn't currently show the translated task guide names.</span></span> <span data-ttu-id="63f79-137">Dodatkowo w bibliotece z maja 2016 r. są dostępne tylko tłumaczenia przewodników zadań opublikowanych w lutym 2016 r.</span><span class="sxs-lookup"><span data-stu-id="63f79-137">Additionally, in the May 2016 library, translations are available only for the task guides that were released in February 2016.</span></span> <span data-ttu-id="63f79-138">Microsoft opublikuje zaktualizowaną bibliotekę zawierającą dodatkowe tłumaczenia.</span><span class="sxs-lookup"><span data-stu-id="63f79-138">Microsoft will release an updated library that includes additional translations.</span></span>
>
> - <span data-ttu-id="63f79-139">Jeśli przewodnik po zadaniu został przetłumaczony, po otwarciu przewodnika jego cały tekst będzie wyświetlany w wybranym języku.</span><span class="sxs-lookup"><span data-stu-id="63f79-139">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="63f79-140">Jeśli przewodnik po zadaniu nie został jeszcze przetłumaczony, po otwarciu przewodnika tylko część tekstu (formanty) będzie wyświetlana w wybranym języku.</span><span class="sxs-lookup"><span data-stu-id="63f79-140">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="adding-custom-help"></a><span data-ttu-id="63f79-141">Dodawanie pomocy niestandardowej</span><span class="sxs-lookup"><span data-stu-id="63f79-141">Adding custom Help</span></span>

<span data-ttu-id="63f79-142">Przewodników zadań można używać do tworzenia pomocy niestandardowej. Można również połączyć witrynę internetową z okienkiem **Pomoc**.</span><span class="sxs-lookup"><span data-stu-id="63f79-142">You can use task guides to create custom Help, or you can connect a custom Help website to the **Help** pane.</span></span>

### <a name="create-custom-help-by-using-task-guides"></a><span data-ttu-id="63f79-143">Tworzenie przewodników zadań pomocy niestandardowej</span><span class="sxs-lookup"><span data-stu-id="63f79-143">Create custom Help by using task guides</span></span>

<span data-ttu-id="63f79-144">Pomoc niestandardową dla obsługiwanych aplikacji można utworzyć, tworząc nagrania zadań odpowiadające implementacji i zapisując je w bibliotece procesów biznesowych w usługach LCS.</span><span class="sxs-lookup"><span data-stu-id="63f79-144">You can create custom Help for the supported apps by creating task recordings that reflect your implementation and then saving them to a Business process library in LCS.</span></span> <span data-ttu-id="63f79-145">Nie można tworzyć niestandardowych przewodników po zadaniach dla aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="63f79-145">You can't create custom task guides for Human Resources.</span></span>

<span data-ttu-id="63f79-146">Jeśli jesteś partnerem i podwyższasz status biblioteki do biblioteki firmowej oraz dołączasz ją do rozwiązania, będzie ona dostępna dla Twoich klientów.</span><span class="sxs-lookup"><span data-stu-id="63f79-146">If you're a partner, and you promote a library to a corporate library and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="63f79-147">Można również utworzyć kopię ujednoliconej biblioteki APQC, a następnie otworzyć nagrania zadań w kopii, edytować je i zapisywać zmiany.</span><span class="sxs-lookup"><span data-stu-id="63f79-147">You can also make a copy of the APQC Unified Library, and then open the task recordings in the copy, edit them, and save your changes.</span></span> <span data-ttu-id="63f79-148">Więcej informacji można znaleźć w see [Zasoby Rejestratora zadań](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="63f79-148">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-help-site"></a><span data-ttu-id="63f79-149">Łączenie z niestandardową witryną pomocy</span><span class="sxs-lookup"><span data-stu-id="63f79-149">Connect a custom Help site</span></span>

<span data-ttu-id="63f79-150">Aplikacje Finance and Operations są rzadko używane w gotowej postaci.</span><span class="sxs-lookup"><span data-stu-id="63f79-150">Finance and Operations apps are rarely used in their out-of-box form.</span></span> <span data-ttu-id="63f79-151">Zamiast tego rozwiązanie jest dostosowywane i rozszerzane w celu dopasowania do potrzeb organizacji.</span><span class="sxs-lookup"><span data-stu-id="63f79-151">Instead, the solution is customized and extended to fit the organization's needs.</span></span> <span data-ttu-id="63f79-152">Można również dostosowywać i rozszerzać środowisko pomocy.</span><span class="sxs-lookup"><span data-stu-id="63f79-152">You can also customize and extend the Help experience.</span></span> <span data-ttu-id="63f79-153">Można na przykład dodać niestandardową pomoc do okienka **Pomoc** w produkcie.</span><span class="sxs-lookup"><span data-stu-id="63f79-153">For example, you can add custom Help to the in-product **Help** pane.</span></span>

<span data-ttu-id="63f79-154">Firma Microsoft udostępniła zestaw narzędzi ułatwiających wdrażanie i łączenie pomocy niestandardowej z okienkiem **Pomoc**.</span><span class="sxs-lookup"><span data-stu-id="63f79-154">Microsoft has provided a toolkit to help you deploy and connect custom Help to the **Help** pane.</span></span> <span data-ttu-id="63f79-155">Aby uzyskać informacje o tym, jak można skonfigurować niestandardowe rozwiązanie pomocy połączone z okienkiem **Pomoc**, zapoznaj się z [omówieniem pomocy niestandardowej](../../dev-itpro/help/custom-help-overview.md).</span><span class="sxs-lookup"><span data-stu-id="63f79-155">For information about how you can set up a custom Help solution that is connected to the **Help** pane, see [Custom Help overview](../../dev-itpro/help/custom-help-overview.md).</span></span>

<span data-ttu-id="63f79-156">Aby współpracować z firmą Microsoft w zakresie tworzenia do narzędzi i procesów ułatwiających dostosowywanie pomocy, wypełnij formularz pod adresem [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span><span class="sxs-lookup"><span data-stu-id="63f79-156">If you want to collaborate with Microsoft on tools and processes for customizing Help, fill in the form at [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span></span>

## <a name="see-also"></a><span data-ttu-id="63f79-157">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="63f79-157">See also</span></span>

[<span data-ttu-id="63f79-158">System Pomocy</span><span class="sxs-lookup"><span data-stu-id="63f79-158">Help system</span></span>](help-overview.md)  
[<span data-ttu-id="63f79-159">Omówienie pomocy niestandardowej</span><span class="sxs-lookup"><span data-stu-id="63f79-159">Custom Help overview</span></span>](../../dev-itpro/help/custom-help-overview.md)  
[<span data-ttu-id="63f79-160">Zasoby rejestratora zadań</span><span class="sxs-lookup"><span data-stu-id="63f79-160">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)  
[<span data-ttu-id="63f79-161">Tworzenie dokumentacji lub szkolenia za pomocą Rejestratora zadań</span><span class="sxs-lookup"><span data-stu-id="63f79-161">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[<span data-ttu-id="63f79-162">Repozytorium GitHub pomocy niestandardowej</span><span class="sxs-lookup"><span data-stu-id="63f79-162">Custom Help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)  

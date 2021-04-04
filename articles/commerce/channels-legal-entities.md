---
title: Utwórz firmy
description: W tym temacie opisano sposób tworzenia firm w Microsoft Dynamics 365 Commerce, która musi zostać utworzona i skonfigurowana przed utworzeniem kanałów.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 016b67631a53139d12d65dfaf594f49b030326b1
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478219"
---
# <a name="create-legal-entities"></a><span data-ttu-id="5017b-103">Utwórz firmy</span><span class="sxs-lookup"><span data-stu-id="5017b-103">Create legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5017b-104">W tym temacie opisano sposób tworzenia firm w Microsoft Dynamics 365 Commerce, która musi zostać utworzona i skonfigurowana przed utworzeniem kanałów.</span><span class="sxs-lookup"><span data-stu-id="5017b-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

<span data-ttu-id="5017b-105">Firma to organizacja, która ma zarejestrowaną lub uchwaloną strukturę prawną.</span><span class="sxs-lookup"><span data-stu-id="5017b-105">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="5017b-106">Firmy mogą zawierać zgodne z prawem umowy i wymaga się od nich przygotowywania zestawień na temat ich wydajności.</span><span class="sxs-lookup"><span data-stu-id="5017b-106">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="5017b-107">Firma jest typem podmiotu prawnego.</span><span class="sxs-lookup"><span data-stu-id="5017b-107">A company is a type of legal entity.</span></span> <span data-ttu-id="5017b-108">Obecnie firmy to jedyny rodzaj podmiotu prawnego, który można tworzyć, a każdy podmiot prawny jest skojarzony z identyfikatorem firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-108">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="5017b-109">To skojarzenie istnieje, ponieważ niektóre obszary funkcjonalne w programie wykorzystują identyfikator lub *DataAreaId* firmy w ich modelach danych.</span><span class="sxs-lookup"><span data-stu-id="5017b-109">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="5017b-110">W tych obszarach funkcjonalnych firmy są używane jako granica zabezpieczeń danych.</span><span class="sxs-lookup"><span data-stu-id="5017b-110">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="5017b-111">Użytkownicy mogą uzyskiwać dostęp do danych tylko dla firmy, do której są aktualnie zalogowani.</span><span class="sxs-lookup"><span data-stu-id="5017b-111">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="5017b-112">Podczas tworzenia kanału należy określić, do której firmy należy dany kanał.</span><span class="sxs-lookup"><span data-stu-id="5017b-112">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="5017b-113">Utwórz nową firmę</span><span class="sxs-lookup"><span data-stu-id="5017b-113">Create a new legal entity</span></span>

<span data-ttu-id="5017b-114">Aby utworzyć nową firmę w usłudze Dynamics 365 Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5017b-114">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="5017b-115">W okienku nawigacji przejdź do **Moduły \> Ustawienia Headquarters \> Firmy**.</span><span class="sxs-lookup"><span data-stu-id="5017b-115">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="5017b-116">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5017b-116">On the action pane, select **New**.</span></span> <span data-ttu-id="5017b-117">Po prawej stronie pojawi się okienko **Nowa firma**.</span><span class="sxs-lookup"><span data-stu-id="5017b-117">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="5017b-118">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="5017b-118">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="5017b-119">Wprowadź wartość w polu **Firma**.</span><span class="sxs-lookup"><span data-stu-id="5017b-119">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="5017b-120">W polu **Kraj/region** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5017b-120">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="5017b-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5017b-121">Select **OK**.</span></span> 

   ![Tworzenie firmy](media/legal-entities.png)

1. <span data-ttu-id="5017b-123">W sekcji **Ogólne** udostępniane są następujące ogólne informacje o firmie:</span><span class="sxs-lookup"><span data-stu-id="5017b-123">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="5017b-124">Wprowadź alias, jeśli alias jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="5017b-124">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="5017b-125">Alias jest alternatywną nazwą, która może być używana do wyszukiwania danej firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-125">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="5017b-126">Zaznacz, czy ta firma jest używana jako skonsolidowana.</span><span class="sxs-lookup"><span data-stu-id="5017b-126">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="5017b-127">Zaznacz, czy ta firma jest używana jako firma z wpisami eliminacji.</span><span class="sxs-lookup"><span data-stu-id="5017b-127">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="5017b-128">Wybierz **język domyślny** dla firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-128">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="5017b-129">Wybierz **strefę czasową** dla firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-129">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="5017b-130">W sekcji **Adresy** wybierz **Edytuj**, żeby wprowadzić takie informacje adresowe, jak nazwa ulicy i numer budynku, kod pocztowy oraz miasto.</span><span class="sxs-lookup"><span data-stu-id="5017b-130">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="5017b-131">W sekcji **Informacje kontaktowe** wprowadź informacje dotyczące metod komunikacji, takie jak adresy e-mail, adresy URL i numery telefonów.</span><span class="sxs-lookup"><span data-stu-id="5017b-131">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="5017b-132">W sekcji **Raportowanie ustawowe** wprowadź numery rejestrowe używane do raportowania statutowego.</span><span class="sxs-lookup"><span data-stu-id="5017b-132">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="5017b-133">W sekcji **Numery rejestracji** wprowadź wszelkie informacje wymagane przez firmę.</span><span class="sxs-lookup"><span data-stu-id="5017b-133">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="5017b-134">W sekcji **Informacje o koncie bankowym** wprowadź numery kont bankowych i kody banku rachunków używanych przez firmę.</span><span class="sxs-lookup"><span data-stu-id="5017b-134">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="5017b-135">W sekcji **Handel zagraniczny i logistyka** wprowadź informacje wysyłkowe firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-135">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="5017b-136">W sekcji **Sekwencje identyfikatorów** można wyświetlić sekwencje numeracji skojarzone z firmą.</span><span class="sxs-lookup"><span data-stu-id="5017b-136">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="5017b-137">Ta opcja będzie pusta na początku.</span><span class="sxs-lookup"><span data-stu-id="5017b-137">This will be empty to start with.</span></span>
1. <span data-ttu-id="5017b-138">W sekcji **Obraz na pulpit nawigacyjny** można wyświetlić i zmienić obraz logo i pulpitu nawigacyjnego skojarzony z firmą.</span><span class="sxs-lookup"><span data-stu-id="5017b-138">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="5017b-139">W sekcji **Rejestracja podatkowa** wprowadź numery rejestrowe używane w zeznaniach dla urzędów skarbowych.</span><span class="sxs-lookup"><span data-stu-id="5017b-139">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="5017b-140">W sekcji **Podatek 1099** wprowadź dane formularza 1099 dla firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-140">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="5017b-141">W sekcji **Informacja podatkowa** wprowadź dane podatkowe dla firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-141">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="5017b-142">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5017b-142">Select **Save**.</span></span>

<span data-ttu-id="5017b-143">Poniższy obraz przedstawia przykład szczegółów firmy.</span><span class="sxs-lookup"><span data-stu-id="5017b-143">The following image shows details of an example legal entity.</span></span>

![Sekcja ogólna firmy](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="5017b-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5017b-145">Additional resources</span></span>

[<span data-ttu-id="5017b-146">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="5017b-146">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="5017b-147">Planowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="5017b-147">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="5017b-148">Hierarchie organizacyjne</span><span class="sxs-lookup"><span data-stu-id="5017b-148">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="5017b-149">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="5017b-149">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="5017b-150">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="5017b-150">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

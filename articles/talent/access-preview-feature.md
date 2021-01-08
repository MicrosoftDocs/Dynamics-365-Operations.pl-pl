---
title: Zarządzanie funkcjami
description: W tym temacie opisano, jak administrator może włączyć funkcje w wersji zapoznawczej w aplikacji Microsoft Dynamics 365 Talent, oraz podano listę funkcji dostępnych obecnie w wersji zapoznawczej.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.1.0, Talent
ms.openlocfilehash: d818e9e04ce88e5ab285ef8176334809447fb477
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462284"
---
# <a name="manage-features"></a><span data-ttu-id="bb08c-103">Zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="bb08c-103">Manage features</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bb08c-104">W ramach ciągłego wdrażania nowych funkcji zarządzania kapitałem ludzkim (HCM) w aplikacji Microsoft Dynamics 365 Human Resources chcemy stworzyć klientom możliwość jak najszybszego zetknięcia się z nimi.</span><span class="sxs-lookup"><span data-stu-id="bb08c-104">As part of our continuous rollout of human capital management (HCM) capabilities for Microsoft Dynamics 365 Human Resources, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="bb08c-105">Administratorzy mogą przeglądać i używać funkcji zapoznawczych w swoich środowiskach.</span><span class="sxs-lookup"><span data-stu-id="bb08c-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="bb08c-106">Te funkcje są prawie gotowe do ogólnego udostępnienia i przeszły wszechstronne testy.</span><span class="sxs-lookup"><span data-stu-id="bb08c-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="bb08c-107">Jednak zanim je upublicznimy powszechnie, chcemy jeszcze poznać finalne opinie klientów i przeprowadzić ostatnią weryfikację.</span><span class="sxs-lookup"><span data-stu-id="bb08c-107">We're just looking for a final round of customer feedback and validation before we release them for general availability.</span></span>

<span data-ttu-id="bb08c-108">W tym temacie opisano, jak włączyć funkcje w wersji zapoznawczej, oraz podano listę funkcji dostępnych obecnie w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="bb08c-108">This topic describes how you can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="bb08c-109">Lista będzie aktualizowana wraz z przekazywaniem kolejnych funkcji ogółowi użytkowników i udostępnianiem wersji zapoznawczych.</span><span class="sxs-lookup"><span data-stu-id="bb08c-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="bb08c-110">Dodawanie nowych funkcji zapoznawczych nie będzie w żaden sposób anonsowane.</span><span class="sxs-lookup"><span data-stu-id="bb08c-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="bb08c-111">Użytkownicy po prostu zaczną je widzieć.</span><span class="sxs-lookup"><span data-stu-id="bb08c-111">Users will just start to see the features.</span></span> <span data-ttu-id="bb08c-112">Aby uzyskać więcej informacji o nowych funkcjach w aplikacji Talent, zobacz [Nowości i zmiany w aplikacji Dynamics 365 Talent](./whats-new.md) oraz [Informacje o wersji Dynamics 365 i Power Platform](https://docs.microsoft.com/business-applications-release-notes).</span><span class="sxs-lookup"><span data-stu-id="bb08c-112">For more information about new features in Talent, see [What's new or changed in Dynamics 365 Talent](./whats-new.md) and [Dynamics 365 and Power Platform Release Notes](https://docs.microsoft.com/business-applications-release-notes).</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="bb08c-113">Włączanie i wyłączanie funkcji zapoznawczych</span><span class="sxs-lookup"><span data-stu-id="bb08c-113">Enable or disable preview features</span></span>

<span data-ttu-id="bb08c-114">Aby uzyskać dostęp do funkcji w wersji zapoznawczej, należy je najpierw włączyć w środowisku.</span><span class="sxs-lookup"><span data-stu-id="bb08c-114">To access preview features, you must first enable them in your environment.</span></span> <span data-ttu-id="bb08c-115">Włączanie lub wyłączanie funkcji zapoznawczych jest specyficzne dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="bb08c-115">Enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb08c-116">Włączenie ustawienia **Funkcje w wersji zapoznawczej** skutkuje włączeniem funkcji w wersji zapoznawczej wszystkim użytkownikom w organizacji pracującym w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="bb08c-116">When you turn on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="bb08c-117">Wyłączenie ustawienia powoduje wyłączenie funkcji w wersji zapoznawczej i zablokowanie użytkownikom dostępu do nich.</span><span class="sxs-lookup"><span data-stu-id="bb08c-117">When you turn off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="bb08c-118">Funkcje zapoznawcze są obsługiwane w ograniczonym zakresie w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="bb08c-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="bb08c-119">Mogą korzystać ze słabszych narzędzi ochrony prywatności i bezpieczeństwa oraz nie są objęte umową dotyczącą poziomu usług (SLA) zawieraną dla aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="bb08c-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement (SLA).</span></span> <span data-ttu-id="bb08c-120">Nie należy używać funkcji zapoznawczych do przetwarzania danych osobowych (tzn. wszelkich informacji, które mogą jednoznacznie identyfikować użytkownika) ani innych danych, które podlegają prawnym lub ustawowym wymogom dotyczącym zgodności.</span><span class="sxs-lookup"><span data-stu-id="bb08c-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="attract"></a><span data-ttu-id="bb08c-121">Attract</span><span class="sxs-lookup"><span data-stu-id="bb08c-121">Attract</span></span>

1. <span data-ttu-id="bb08c-122">Zaloguj się do programu Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="bb08c-122">Sign in to Microsoft Dynamics 365 Talent: Attract.</span></span>
2. <span data-ttu-id="bb08c-123">W menu **Ustawienia** (symbol koła zębatego) w prawym górnym rogu wybierz opcję **Centrum administracyjne**.</span><span class="sxs-lookup"><span data-stu-id="bb08c-123">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin center**.</span></span>
3. <span data-ttu-id="bb08c-124">Na karcie **Zarządzanie funkcjami** zaznacz opcję **Funkcje w wersji zapoznawczej**, tak aby zmieniła kolor na niebieski i treść na **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="bb08c-124">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue and says **On**.</span></span>

    ![Włączanie funkcji w wersji zapoznawczej w aplikacji Attract](./media/attract-enable-preview-features.png)

4. <span data-ttu-id="bb08c-126">Wybierz lub anuluj wybór poszczególnych funkcji w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="bb08c-126">Select or cancel the selection of individual preview features.</span></span> <span data-ttu-id="bb08c-127">W przeciwnym razie zostaną włączone wszystkie dostępne funkcje w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="bb08c-127">If you do nothing, all available preview features are enabled.</span></span>
5. <span data-ttu-id="bb08c-128">Odśwież przeglądarkę, a zaczniesz widzieć nowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="bb08c-128">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="bb08c-129">Wszyscy użytkownicy, którzy są już zalogowani, zobaczą funkcje po następnym zalogowaniu, lub też mogą odświeżyć przeglądarki, a zobaczą je natychmiast.</span><span class="sxs-lookup"><span data-stu-id="bb08c-129">Any users who are already signed in will see the features the next time they sign in, or they can refresh their browser to see the features immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="bb08c-130">Niektóre funkcje w wersji zapoznawczej mogą wymagać dodatkowej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="bb08c-130">Some preview features might require additional configuration.</span></span> <span data-ttu-id="bb08c-131">Obok funkcji w wersji zapoznawczej znajdują się łącza umożliwiające dokończenie ich konfigurowania.</span><span class="sxs-lookup"><span data-stu-id="bb08c-131">Follow the links next to the preview feature to complete the setup for it.</span></span>

## <a name="feedback"></a><span data-ttu-id="bb08c-132">Opinii</span><span class="sxs-lookup"><span data-stu-id="bb08c-132">Feedback</span></span>

<span data-ttu-id="bb08c-133">Chcemy się dowiedzieć, co sądzisz, na podstawie swojego doświadczenia, o tych funkcjach w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="bb08c-133">We want to hear from you about your experience with any of these preview features.</span></span> <span data-ttu-id="bb08c-134">Zachęcamy do regularnego zamieszczania opinii w podanych witrynach podczas korzystania z tych i innych funkcji:</span><span class="sxs-lookup"><span data-stu-id="bb08c-134">We encourage you to regularly post your feedback on the following sites as you use these or any other features:</span></span>

- <span data-ttu-id="bb08c-135">[Społeczność](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) — Ta witryna to doskonała platforma, na której użytkownicy mogą omawiać scenariusze zastosowania, zadawać pytania i otrzymywać osób od podobnych im osób.</span><span class="sxs-lookup"><span data-stu-id="bb08c-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="bb08c-136">Opowiedz nam o funkcjach, które Twoim zdaniem powinny się znaleźć w produkcie, a także o wszelkich zmianach, które Twoim zdaniem należy wprowadzić w istniejących funkcjach.</span><span class="sxs-lookup"><span data-stu-id="bb08c-136">Let us know about features that you want to see in the product, or let us know about any changes you think we should make to existing features.</span></span> <span data-ttu-id="bb08c-137">Pomysły na ulepszenie produktu można zgłaszać w następujących witrynach:</span><span class="sxs-lookup"><span data-stu-id="bb08c-137">Suggest product ideas on the following sites:</span></span>

    - [<span data-ttu-id="bb08c-138">Pomysły dotyczące aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="bb08c-138">Attract ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="bb08c-139">Pomysły dotyczące aplikacji Onboard</span><span class="sxs-lookup"><span data-stu-id="bb08c-139">Onboard ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

<span data-ttu-id="bb08c-140">W przesyłanych opiniach i recenzjach produktu nie podawaj żadnych danych osobowych (tzn. informacji, które mogłyby umożliwić identyfikację Ciebie).</span><span class="sxs-lookup"><span data-stu-id="bb08c-140">Make sure that you don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="bb08c-141">Zebrane informacje mogą być dalej analizowane, ale ze względu na obowiązujące przepisy o ochronie danych osobowych nie będą wykorzystywane do udzielania odpowiedzi na pytania.</span><span class="sxs-lookup"><span data-stu-id="bb08c-141">Collected information might be analyzed further and isn't used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="bb08c-142">Dane osobowe, które na mocy tych programów są zbierane osobno, podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="bb08c-142">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="bb08c-143">Dodaj tej temat do zakładek i zaglądaj tu regularnie, aby być na bieżąco z nowo publikowanymi funkcjami w wersjach zapoznawczych.</span><span class="sxs-lookup"><span data-stu-id="bb08c-143">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb08c-144">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="bb08c-144">See also</span></span>

- [<span data-ttu-id="bb08c-145">Wypróbuj lub kup aplikacje Talent</span><span class="sxs-lookup"><span data-stu-id="bb08c-145">Try or buy Talent apps</span></span>](https://dynamics.microsoft.com/talent/overview/)
- [<span data-ttu-id="bb08c-146">Nowości i zmiany w Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="bb08c-146">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="bb08c-147">Plany wydań</span><span class="sxs-lookup"><span data-stu-id="bb08c-147">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="bb08c-148">Uzyskiwanie pomocy technicznej dotyczącej rozwiązania Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="bb08c-148">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)

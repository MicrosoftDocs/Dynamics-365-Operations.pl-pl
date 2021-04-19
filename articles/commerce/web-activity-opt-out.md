---
title: Rezygnacja ze zbierania zdarzeń aktywności internetowej
description: W tym temacie wyjaśniono, jak można pozwolić osobom odwiedzającym witrynę internetową na zbieranie zdarzeń aktywności internetowej w aplikacji Microsoft Dynamics 365 Commerce.
author: aamiral
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86f475cc0b78c620309301516b6c3b525b640637
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791564"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="b8a09-103">Rezygnacja ze zbierania zdarzeń działania sieci Web</span><span class="sxs-lookup"><span data-stu-id="b8a09-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="b8a09-104">W tym temacie wyjaśniono, jak można pozwolić klientom zrezygnować ze zbierania zdarzeń aktywności internetowej w aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b8a09-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b8a09-105">Aplikacja Dynamics 365 Commerce umożliwia administratorzy witryn analizować aktywność internetową użytkowników swoich witryn handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="b8a09-105">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="b8a09-106">Dzięki temu mogą oni lepiej zrozumieć, w jaki sposób są używane ich witryny, a także zoptymalizować witryny, aby zwiększyć komfort pracy użytkownika i osiągnąć cele biznesowe.</span><span class="sxs-lookup"><span data-stu-id="b8a09-106">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="b8a09-107">Sposoby zaimplementowania rezygnacji z usługi przez administratorów</span><span class="sxs-lookup"><span data-stu-id="b8a09-107">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="b8a09-108">Administratorom udostępniono trzy sposoby zaimplementowania rezygnacji z usługi.</span><span class="sxs-lookup"><span data-stu-id="b8a09-108">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="b8a09-109">Rezygnacja w imieniu użytkowników</span><span class="sxs-lookup"><span data-stu-id="b8a09-109">Opt out on behalf of users</span></span>

<span data-ttu-id="b8a09-110">W przypadku zarządzania kontami w module Commerce Headquarters administratorzy mogą zrezygnować w imieniu użytkowników.</span><span class="sxs-lookup"><span data-stu-id="b8a09-110">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="b8a09-111">W kliencie HQ na stronie **Wszyscy odbiorcy** wyszukaj i wybierz odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="b8a09-111">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="b8a09-112">Na stronie szczegółów odbiorcy na skróconej karcie **Retail** sekcji **Prywatność** ustaw opcję **Nie śledź aktywności internetowej** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b8a09-112">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Ustawienia prywatności](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="b8a09-114">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b8a09-114">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="b8a09-115">Oparta na module usługa rezygnacji</span><span class="sxs-lookup"><span data-stu-id="b8a09-115">Module-based opt-out experience</span></span>

<span data-ttu-id="b8a09-116">Administratorzy mogą zezwolić uwierzytelnionym użytkownikom na samodzielną rezygnację z zbierania zdarzeń aktywności internetowej.</span><span class="sxs-lookup"><span data-stu-id="b8a09-116">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="b8a09-117">Aby określić to działanie, należy dodać moduł rezygnacji przez użytkownika do stron profilu konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b8a09-117">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="b8a09-118">Rozszerzenia niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b8a09-118">Custom extensions</span></span>

<span data-ttu-id="b8a09-119">Administratorzy mogą tworzyć własne rozszerzenia służące do zarządzania niektórymi usługami rezygnacji użytkowników.</span><span class="sxs-lookup"><span data-stu-id="b8a09-119">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="b8a09-120">Aby uzyskać więcej informacji, zobacz [Wywoływanie interfejsów API w usłudze Retail Server](e-commerce-extensibility/call-retail-server-apis.md) i [rozszerzalność kanału online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="b8a09-120">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

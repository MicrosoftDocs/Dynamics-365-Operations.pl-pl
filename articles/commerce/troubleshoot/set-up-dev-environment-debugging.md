---
title: Skonfiguruj środowisko programowe dla usług e-commerce do debugowania względem maszyny wirtualnej warstwy 1 Retail Server
description: W tym temacie wyjaśniono, jak skonfigurować środowisko programistyczne handlu elektronicznego w celu debugowania na maszynie wirtualnej (VM) serwera Tier 1 Retail Server.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5ef286aa28ff459befb72b0178f308e5fb85ec44
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801490"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a><span data-ttu-id="a6495-103">Skonfiguruj środowisko programowe dla usług e-commerce do debugowania względem maszyny wirtualnej warstwy 1 Retail Server</span><span class="sxs-lookup"><span data-stu-id="a6495-103">Set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a6495-104">W tym temacie wyjaśniono, jak skonfigurować środowisko programistyczne handlu elektronicznego w celu debugowania na maszynie wirtualnej (VM) serwera Tier 1 Retail Server.</span><span class="sxs-lookup"><span data-stu-id="a6495-104">This topic explains how to set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine (VM).</span></span>

## <a name="description"></a><span data-ttu-id="a6495-105">opis</span><span class="sxs-lookup"><span data-stu-id="a6495-105">Description</span></span>

<span data-ttu-id="a6495-106">Microsoft Dynamics 365 Commerce Środowiska warstwy 1 są zwykle wdrażane w środowiskach uruchomieniowych Commerce Runtime (CRT) i w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="a6495-106">Microsoft Dynamics 365 Commerce Tier 1 environments are typically deployed for Commerce runtime (CRT) and point of sale (POS) extension development.</span></span> <span data-ttu-id="a6495-107">Są to środowiska autonomiczne.</span><span class="sxs-lookup"><span data-stu-id="a6495-107">They are standalone environments.</span></span> <span data-ttu-id="a6495-108">Ze względu na charakter oprogramowania jako usługi (Rodzaju usług) architektura nie obejmuje składników systemu e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a6495-108">Because of the software as a service (SaaS) nature of the architecture, they don't include e-commerce components.</span></span>

<span data-ttu-id="a6495-109">W niektórych scenariuszach można przetestować wywołania rozszerzeń w środowisku warstwy 1, aby było możliwe debugowanie rozszerzeń z składników usługi e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a6495-109">In some scenarios, you might want to test calls to extensions in a Tier 1 environment, so that you can debug extensions from e-commerce components.</span></span> <span data-ttu-id="a6495-110">Aby przeczytać ogólne instrukcje, zobacz [Debugowanie względem środowiska projektowego Commerce w warstwie 1 Commerce](../e-commerce-extensibility/debug-tier-1.md).</span><span class="sxs-lookup"><span data-stu-id="a6495-110">For general instructions, see [Debug against a Tier 1 Commerce development environment](../e-commerce-extensibility/debug-tier-1.md).</span></span>

<span data-ttu-id="a6495-111">Podczas debugowania względem środowiska warstwy 1, ponieważ witryna wywołuje teraz inny serwer detaliczny, wywołania między serwerami mogą powodować różne błędy związane z zasadami zabezpieczeń zawartości.</span><span class="sxs-lookup"><span data-stu-id="a6495-111">When you debug against a Tier 1 environment, because the site is now calling a different Retail Server, cross-server calls might cause various errors that are related to the content security policy.</span></span>

<span data-ttu-id="a6495-112">Na poniższej ilustracji pokazano przykład błędu, który może wystąpić, gdy wariant został wybrany na stronie szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="a6495-112">The following illustration shows an example of an error that might occur when a variant is selected on a product details page.</span></span>

![Błąd podczas wyboru wariantu na stronie szczegółów produktu](media/unhandled-rejection-error.jpg)

<span data-ttu-id="a6495-114">Na poniższej ilustracji pokazano przykład podobnego błędu w narzędziach debugera przeglądarki (F12 Developer Tools).</span><span class="sxs-lookup"><span data-stu-id="a6495-114">The following illustration shows an example of a similar error in a browser's debugger tools (F12 Developer Tools).</span></span> <span data-ttu-id="a6495-115">W komunikacie o błędzie wymieniono naruszenie dyrektywy zasad zabezpieczeń zawartości.</span><span class="sxs-lookup"><span data-stu-id="a6495-115">The error message mentions violation of the content security policy directive.</span></span>

![Błąd narzędzi debugera](media/debugger-tools-error.JPG)

## <a name="resolution"></a><span data-ttu-id="a6495-117">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="a6495-117">Resolution</span></span>

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a><span data-ttu-id="a6495-118">Wyłączanie zasad zabezpieczeń zawartości dla witryny w Konstruktorze witryn portalu Commerce</span><span class="sxs-lookup"><span data-stu-id="a6495-118">Disable the content security policy for the site in Commerce site builder</span></span>

1. <span data-ttu-id="a6495-119">Wybierz witrynę, nad która pracujesz.</span><span class="sxs-lookup"><span data-stu-id="a6495-119">Select the site that you're working on.</span></span>
1. <span data-ttu-id="a6495-120">Wybierz **Ustawienia**, a następnie wybierz **Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="a6495-120">Select **Settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="a6495-121">Na karcie **Zasady zabezpieczeń** zawartość wybierz pozycję **Wyłącz zasady zabezpieczeń zawartości**.</span><span class="sxs-lookup"><span data-stu-id="a6495-121">On the **Content security policy** tab, select **Disable content security policy**.</span></span>
1. <span data-ttu-id="a6495-122">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="a6495-122">Select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="a6495-123">Rejestracja b2C (Business-to-consumer) nie działa w lokalnym środowisku programisty.</span><span class="sxs-lookup"><span data-stu-id="a6495-123">Business-to-consumer (B2C) sign-in won't work in a local development environment.</span></span> <span data-ttu-id="a6495-124">Można jednak w razie potrzeby użyć funkcji realizacji transakcji gościa lub utworzyć model strony.</span><span class="sxs-lookup"><span data-stu-id="a6495-124">However, you can use guest checkouts or build page mocks to simulate a user sign-in as required.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a6495-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a6495-125">Additional resources</span></span>

[<span data-ttu-id="a6495-126">Rozpoczynanie wdrażania rozszerzania handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="a6495-126">Get started with e-commerce online extensibility development</span></span>](../e-commerce-extensibility/sdk-getting-started.md)

[<span data-ttu-id="a6495-127">Zarządzanie zasadami zabezpieczeń zawartości w witrynie handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="a6495-127">Manage content security policy (CSP) on e-commerce site</span></span>](../manage-csp.md)

---
title: Wybór motywu witryny
description: W tym temacie opisano sposób ustawiania lub zmieniania motywu witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c54a3e9471fdeb56f27fe7c567c7cd7f0b7fd218
ms.sourcegitcommit: 2ef23dcd4e42362186b9951e675010d97d55c6bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4556436"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="9d8ed-103">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="9d8ed-103">Select a site theme</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9d8ed-104">W tym temacie opisano sposób ustawiania lub zmieniania motywu witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9d8ed-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="9d8ed-105">Overview</span></span>

<span data-ttu-id="9d8ed-106">Układ i styl witryny (np. czcionki, rozmiary i kolory) są definiowane przez wybrany motyw i mają zastosowanie w odniesieniu do witryny.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-106">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="9d8ed-107">Motyw jest tworzony i wdrażany przez programistę w firmie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-107">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="9d8ed-108">Aby zapoznać się z omówieniem motywów, zajrzyj do [Omówienie funkcji motywowania](e-commerce-extensibility/theming.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ed-108">For an overview of themes, see [Theming overview](e-commerce-extensibility/theming.md).</span></span> <span data-ttu-id="9d8ed-109">Aby uzyskać więcej informacji dotyczących sposobu tworzenia i wdrażania motywów, zobacz [Tworzenie nowego motywu](e-commerce-extensibility/create-theme.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ed-109">For more information about how to create and deploy themes, see [Create a new theme](e-commerce-extensibility/create-theme.md).</span></span>

<span data-ttu-id="9d8ed-110">Domyślnie podczas tworzenia oddziałów jest używany motyw o nazwie **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-110">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="9d8ed-111">Ten motyw domyślny jest dostarczany jako część biblioteki modułu handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-111">This default theme is provided as part of the Commerce module library.</span></span> <span data-ttu-id="9d8ed-112">Po wdrożeniu dodatkowych motywów dla witryny można skonfigurować witrynę tak, aby korzystała z jednego z nich.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-112">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="9d8ed-113">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="9d8ed-113">Select the site theme</span></span>

<span data-ttu-id="9d8ed-114">Aby wybrać motyw zastosowany w odniesieniu do witryny, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-114">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="9d8ed-115">W środowisku tworzenia witryn przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-115">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="9d8ed-116">Przejdź do **Zarządzanie witryną** \> **Możliwości rozszerzania**.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-116">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="9d8ed-117">W obszarze **Motyw** wybierz motyw w menu rozwijanym.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-117">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="9d8ed-118">Aby zastosować wybraną kompozycję do witryny, wybierz opcję **Zapisz i Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-118">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="9d8ed-119">Wybrany motyw jest publikowany w witrynie po wybraniu opcji **Zapisz i Publikuj** na stronie **Możliwości rozszerzania**.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-119">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="9d8ed-120">Aby wyświetlić podgląd motywu w witrynie przed zastosowaniem go, można użyć swojego środowiska programistycznego lub piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="9d8ed-120">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d8ed-121">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9d8ed-121">Additional resources</span></span>

[<span data-ttu-id="9d8ed-122">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="9d8ed-122">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="9d8ed-123">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="9d8ed-123">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="9d8ed-124">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="9d8ed-124">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="9d8ed-125">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="9d8ed-125">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="9d8ed-126">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="9d8ed-126">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="9d8ed-127">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="9d8ed-127">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="9d8ed-128">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="9d8ed-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="9d8ed-129">Omówienie funkcji motywowania</span><span class="sxs-lookup"><span data-stu-id="9d8ed-129">Theming overview</span></span>](e-commerce-extensibility/theming.md)

[<span data-ttu-id="9d8ed-130">Tworzenie nowego motywu</span><span class="sxs-lookup"><span data-stu-id="9d8ed-130">Create a new theme</span></span>](e-commerce-extensibility/create-theme.md)


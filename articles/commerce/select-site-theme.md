---
title: Wybór motywu witryny
description: W tym temacie opisano sposób ustawiania lub zmieniania motywu witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e11e2ffafa29dfe4ad7a4a8e4d14e9d7c74c31f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794074"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="80e18-103">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="80e18-103">Select a site theme</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="80e18-104">W tym temacie opisano sposób ustawiania lub zmieniania motywu witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="80e18-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="80e18-105">Układ i styl witryny (np. czcionki, rozmiary i kolory) są definiowane przez wybrany motyw i mają zastosowanie w odniesieniu do witryny.</span><span class="sxs-lookup"><span data-stu-id="80e18-105">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="80e18-106">Motyw jest tworzony i wdrażany przez programistę w firmie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="80e18-106">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="80e18-107">Aby zapoznać się z omówieniem motywów, zajrzyj do [Omówienie funkcji motywowania](e-commerce-extensibility/theming.md).</span><span class="sxs-lookup"><span data-stu-id="80e18-107">For an overview of themes, see [Theming overview](e-commerce-extensibility/theming.md).</span></span> <span data-ttu-id="80e18-108">Aby uzyskać więcej informacji dotyczących sposobu tworzenia i wdrażania motywów, zobacz [Tworzenie nowego motywu](e-commerce-extensibility/create-theme.md).</span><span class="sxs-lookup"><span data-stu-id="80e18-108">For more information about how to create and deploy themes, see [Create a new theme](e-commerce-extensibility/create-theme.md).</span></span>

<span data-ttu-id="80e18-109">Domyślnie podczas tworzenia oddziałów jest używany motyw o nazwie **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="80e18-109">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="80e18-110">Ten motyw domyślny jest dostarczany jako część biblioteki modułu handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="80e18-110">This default theme is provided as part of the Commerce module library.</span></span> <span data-ttu-id="80e18-111">Po wdrożeniu dodatkowych motywów dla witryny można skonfigurować witrynę tak, aby korzystała z jednego z nich.</span><span class="sxs-lookup"><span data-stu-id="80e18-111">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="80e18-112">Wybór motywu witryny</span><span class="sxs-lookup"><span data-stu-id="80e18-112">Select the site theme</span></span>

<span data-ttu-id="80e18-113">Aby wybrać motyw zastosowany w odniesieniu do witryny, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="80e18-113">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="80e18-114">W środowisku tworzenia witryn przejdź do swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="80e18-114">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="80e18-115">Przejdź do **Zarządzanie witryną** \> **Możliwości rozszerzania**.</span><span class="sxs-lookup"><span data-stu-id="80e18-115">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="80e18-116">W obszarze **Motyw** wybierz motyw w menu rozwijanym.</span><span class="sxs-lookup"><span data-stu-id="80e18-116">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="80e18-117">Aby zastosować wybraną kompozycję do witryny, wybierz opcję **Zapisz i Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="80e18-117">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="80e18-118">Wybrany motyw jest publikowany w witrynie po wybraniu opcji **Zapisz i Publikuj** na stronie **Możliwości rozszerzania**.</span><span class="sxs-lookup"><span data-stu-id="80e18-118">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="80e18-119">Aby wyświetlić podgląd motywu w witrynie przed zastosowaniem go, można użyć swojego środowiska programistycznego lub piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="80e18-119">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80e18-120">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="80e18-120">Additional resources</span></span>

[<span data-ttu-id="80e18-121">Dodawanie logo</span><span class="sxs-lookup"><span data-stu-id="80e18-121">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="80e18-122">Praca z plikami zastępowania CSS</span><span class="sxs-lookup"><span data-stu-id="80e18-122">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="80e18-123">Dodawanie ikony favicon</span><span class="sxs-lookup"><span data-stu-id="80e18-123">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="80e18-124">Dodawanie wiadomości powitalnej</span><span class="sxs-lookup"><span data-stu-id="80e18-124">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="80e18-125">Dodawanie powiadomienia o prawach autorskich</span><span class="sxs-lookup"><span data-stu-id="80e18-125">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="80e18-126">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="80e18-126">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="80e18-127">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="80e18-127">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="80e18-128">Omówienie funkcji motywowania</span><span class="sxs-lookup"><span data-stu-id="80e18-128">Theming overview</span></span>](e-commerce-extensibility/theming.md)

[<span data-ttu-id="80e18-129">Tworzenie nowego motywu</span><span class="sxs-lookup"><span data-stu-id="80e18-129">Create a new theme</span></span>](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

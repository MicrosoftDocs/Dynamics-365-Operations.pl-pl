---
title: Sposoby dodawania zawartości
description: Ten temat zawiera omówienie i umożliwia wybranie łączy do określania, gdzie i jak zacząć zarządzanie zawartością za pomocą zbioru narzędzi konstruktora witryn Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 916e28c2628613332246d19af0fae81f258404b0
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025742"
---
# <a name="ways-to-add-content"></a><span data-ttu-id="54ed7-103">Sposoby dodawania zawartości</span><span class="sxs-lookup"><span data-stu-id="54ed7-103">Ways to add content</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="54ed7-104">Ten temat zawiera omówienie i łącza do dokumentacji na temat zarządzania zawartością za pomocą zbioru narzędzi konstruktora witryn Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="54ed7-104">This topic provides an overview and links to documentation about how to manage content using the Microsoft Dynamics 365 Commerce site builder web authoring toolset.</span></span>

## <a name="overview"></a><span data-ttu-id="54ed7-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="54ed7-105">Overview</span></span>

<span data-ttu-id="54ed7-106">Istnieje wiele sposobów zmiany wyglądu, działania i zawartości witryny.</span><span class="sxs-lookup"><span data-stu-id="54ed7-106">There are many ways to change the look, feel, and content of your site.</span></span> <span data-ttu-id="54ed7-107">W zależności od wymaganego poziomu dostosowania wiele z tych zmian mogą implementować osoby inne niż deweloperzy w ramach konstruktora witryn, który jest zestawem narzędzi do tworzenia treści w sieci Web Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="54ed7-107">Depending on the required level of customization, many of these changes can be implemented by non-developers within site builder, the web authoring toolset included with Dynamics 365 Commerce.</span></span> <span data-ttu-id="54ed7-108">Konstruktor witryn umożliwia tworzenie szablonów, wybieranie motywów oraz wybieranie i konfigurowanie modułów bez konieczności pisania kodu.</span><span class="sxs-lookup"><span data-stu-id="54ed7-108">Site builder enables you to build templates, select themes, and select and configure modules without writing any code.</span></span> <span data-ttu-id="54ed7-109">Z kolei umiejętności programistyczne są wymagane w celu utworzenia nowego motywu lub modułu, ponieważ musi być używany pakiet e-Commerce Software Development Kit (SDK) i wdrażanie przepływu pracy Microsoft Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="54ed7-109">By contrast, development skills are required to create a new theme or module, because the e-Commerce software development kit (SDK) and the Microsoft Dynamics Lifecycle Services (LCS) deployment workflow must be used.</span></span>

<span data-ttu-id="54ed7-110">Poniższe tematy są dobrym punktem początkowym zrozumienia sposobu dodawania zawartości witryny i zarządzania nią.</span><span class="sxs-lookup"><span data-stu-id="54ed7-110">The following topics are good jumping off points to start understanding how to add and manage site content.</span></span> <span data-ttu-id="54ed7-111">Większość wypisanych tematów koncentruje się na obszarach witryny, które nie wymagają dewelopera.</span><span class="sxs-lookup"><span data-stu-id="54ed7-111">Most of the topics listed focus on areas of your site that don't require a developer.</span></span> <span data-ttu-id="54ed7-112">Niektóre podstawowe elementy edytowania zawartości adresu, a inni skupiają się na zadaniach administratora witryny.</span><span class="sxs-lookup"><span data-stu-id="54ed7-112">Some address basic content editing, while others focus on site administrator tasks.</span></span> <span data-ttu-id="54ed7-113">W przypadku każdego z tych tematów oznacza to, że określone zadania mogą wymagać użycia zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="54ed7-113">Each of these topics will denote specific tasks might require SDK work.</span></span> <span data-ttu-id="54ed7-114">W każdym temacie założono, że zainicjowano już witrynę i przyznano mu dostęp do przybornika konstruktora witryn dla tej witryny.</span><span class="sxs-lookup"><span data-stu-id="54ed7-114">Each topic assumes that you have already provisioned a site and been granted access to the site builder toolset for your site.</span></span>

<span data-ttu-id="54ed7-115">Aby rozpocząć, wybierz jeden z poniższych tematów.</span><span class="sxs-lookup"><span data-stu-id="54ed7-115">Select one of the following topics to get started.</span></span>

- <span data-ttu-id="54ed7-116">Aby zaznajomić się z terminologią dotyczącą zarządzania zawartością używaną w module Konstruktor witryn i wtej dokumentacji, należy zapoznać się z tematem [Słownik terminów dotyczących modelu strony](page-elements-overview.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-116">To familiarize yourself with the content management terminology used in site builder and within this documentation, see [Page model glossary](page-elements-overview.md).</span></span>
- <span data-ttu-id="54ed7-117">Aby zrozumieć, jak moduły działają w przepływach pracy zarządzania zawartością, należyzapoznać się z tematem [Praca z modułami](work-with-modules.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-117">To understand how modules work within content management workflows, see [Work with modules](work-with-modules.md).</span></span>
- <span data-ttu-id="54ed7-118">Aby zmienić tekst, obrazy lub wideo na istniejącej stronie witryny, należy zapoznać się z [Praca z modułami](work-with-modules.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-118">To change the text, images, or video on an existing site page, see [Work with modules](work-with-modules.md).</span></span>
- <span data-ttu-id="54ed7-119">Aby zobaczyć, jak fragmenty mogą zwiększyć efektywność i elastyczność zarządzania zawartością, zajrzyj do tematu [Praca z fragmentami](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-119">To see how fragments can make content management more efficient and flexible, see [Work with fragments](work-with-fragments.md).</span></span>
- <span data-ttu-id="54ed7-120">Aby zapewnić prawidłowe korzystanie z funkcji tworzenia marki dla autorów zawartości sieci Web, należy zapoznać się z [Omówienie szablonów i układów](templates-layouts-overview.md) i [Praca z szablonami](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-120">To help ensure a successful on-brand authoring experience for web content authors, see [Templates and layouts overview](templates-layouts-overview.md) and [Work with templates](work-with-templates.md).</span></span>
- <span data-ttu-id="54ed7-121">Aby zmienić rozmieszczenie sekcji na stronie witryny, należy zapoznać się z [Praca z układami](work-with-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-121">To rearrange sections on a site page, see [Work with layouts](work-with-layouts.md).</span></span>
- <span data-ttu-id="54ed7-122">Aby zmienić czcionki, kolory i ogólny wygląd stron witryny, zobacz temat [Wybór motywu witryny](select-site-theme.md) lub [Praca z plikami zastępowania CSS](css-override-files.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-122">To change the fonts, colors, and general look of site pages, see [Select a site theme](select-site-theme.md) or [Work with CSS over-ride files](css-override-files.md).</span></span>
- <span data-ttu-id="54ed7-123">Aby zmienić kolejność lub dodać nowe opcje nawigacji, należy zapoznać się ztematem [Dostosowywanie nawigacji w witrynie](customize-site-navigation.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-123">To rearrange or add new navigation options, see [Customize site navigation](customize-site-navigation.md).</span></span>
- <span data-ttu-id="54ed7-124">Aby dowiedzieć się, jak przemieszczać, wyświetlać i publikować szeroki zbiór współbieżnych zmian zawartości sieci Web, zobacz [Praca z grupami publikowania.](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="54ed7-124">To learn how to stage, preview, and publish a broad set of concurrent web content changes, see [Work with publish groups](publish-groups.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="54ed7-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="54ed7-125">Additional resources</span></span>

[<span data-ttu-id="54ed7-126">Omówienie strony tworzenia</span><span class="sxs-lookup"><span data-stu-id="54ed7-126">Authoring page overview</span></span>](authoring-home-overview.md)

[<span data-ttu-id="54ed7-127">Dokumentowanie stanów i cyklów życia</span><span class="sxs-lookup"><span data-stu-id="54ed7-127">Document states and lifecycle</span></span>](document-states-overview.md)

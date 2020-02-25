---
title: Dokumentowanie stanów i cyklów życia
description: Ten temat dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
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
ms.openlocfilehash: b4f1c462f734b2d58843308f0f877fe18a4d9af7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002988"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="e7349-103">Dokumentowanie stanów i cyklów życia</span><span class="sxs-lookup"><span data-stu-id="e7349-103">Document states and lifecycle</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e7349-104">Ten temat dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7349-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="e7349-105">Opis opisu stanu</span><span class="sxs-lookup"><span data-stu-id="e7349-105">Document state descriptions</span></span>

<span data-ttu-id="e7349-106">Temat [Elementy stony](page-elements-overview.md) zawiera listę różnych typów dokumentów w systemie zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="e7349-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="e7349-107">Te typy dokumentów mogą mieć kilka stanów w narzędziu do tworzenia treści.</span><span class="sxs-lookup"><span data-stu-id="e7349-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="e7349-108">Dokument ułatwia zapobieganie konfliktom danych i egzekwowanie kontroli wersji.</span><span class="sxs-lookup"><span data-stu-id="e7349-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="e7349-109">Określają one, kto może zmieniać dokumenty, kiedy dokumenty mogą być zmieniane i kiedy zmiany mogą być przeglądane przez inne osoby.</span><span class="sxs-lookup"><span data-stu-id="e7349-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="e7349-110">W poniższej tabeli przedstawiono stany dokumentów elementów strony w Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7349-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="e7349-111">Stan dokumentu</span><span class="sxs-lookup"><span data-stu-id="e7349-111">Document state</span></span> | <span data-ttu-id="e7349-112">Opis</span><span class="sxs-lookup"><span data-stu-id="e7349-112">Description</span></span> |
|---|---|
| <span data-ttu-id="e7349-113">Wyewidencjonowano</span><span class="sxs-lookup"><span data-stu-id="e7349-113">Checked out</span></span> | <span data-ttu-id="e7349-114">Gdy element CMS jest wyewidencjonowany dla danego użytkownika, nie może być edytowany przez żadnego innego uwierzytelnionego użytkownika systemu.</span><span class="sxs-lookup"><span data-stu-id="e7349-114">When a CMS item is checked out to you, it can't be edited by any other authenticated system users.</span></span> <span data-ttu-id="e7349-115">Wszelkie zmiany wprowadzone w elemencie są widoczne tylko dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="e7349-115">Any changes that you make to the item are visible only to you.</span></span> |
| <span data-ttu-id="e7349-116">Zaewidencjonowano</span><span class="sxs-lookup"><span data-stu-id="e7349-116">Checked in</span></span> | <span data-ttu-id="e7349-117">Gdy element CMS jest zaewidencjonowany, wszystkie zmiany są widoczne dla innych uwierzytelnionych użytkowników systemu, a użytkownicy mogą następnie wyewidencjonować ten element i edytować go.</span><span class="sxs-lookup"><span data-stu-id="e7349-117">When a CMS item is checked in, all changes are visible to other authenticated system users, and those users can then check out the item and edit it.</span></span> <span data-ttu-id="e7349-118">Każde ewidencjonowanie utworzy rekord wersji dokumentu w historii pozycji.</span><span class="sxs-lookup"><span data-stu-id="e7349-118">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="e7349-119">Opublikowane</span><span class="sxs-lookup"><span data-stu-id="e7349-119">Published</span></span> | <span data-ttu-id="e7349-120">Po opublikowaniu element CMS jest przesunięty do witryny na żywo i staje się wykrywalny w Internecie przez nieuwierzytelnionych użytkowników zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="e7349-120">When a CMS item is published, it's pushed to your live site and becomes discoverable on the internet by non-authenticated external users.</span></span> <span data-ttu-id="e7349-121">Towary mogą być publikowane tylko wtedy, gdy zostały zaewidencjonowane.</span><span class="sxs-lookup"><span data-stu-id="e7349-121">Items can be published only if they have been checked in.</span></span> |
| <span data-ttu-id="e7349-122">Zapisano</span><span class="sxs-lookup"><span data-stu-id="e7349-122">Saved</span></span> | <span data-ttu-id="e7349-123">Zmiany wprowadzone w wyewidencjonowanym elemencie CMS można zapisać w CMS przed zapisaniem lub opublikowaniem elementu.</span><span class="sxs-lookup"><span data-stu-id="e7349-123">Changes that have been made to a checked-out CMS item can be saved to the CMS before the item is checked in or published.</span></span> <span data-ttu-id="e7349-124">Te zapisane zmiany nie są widoczne dla innych uwierzytelnionych użytkowników systemu, dopóki element nie zostanie zaewidencjonowany.</span><span class="sxs-lookup"><span data-stu-id="e7349-124">These saved changes aren't visible to other authenticated system users until the item is checked in.</span></span> <span data-ttu-id="e7349-125">Nie są one widoczne dla użytkowników zewnętrznych do momentu opublikowania elementu.</span><span class="sxs-lookup"><span data-stu-id="e7349-125">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="e7349-126">Odrzucone wyewidencjonowanie</span><span class="sxs-lookup"><span data-stu-id="e7349-126">Discarded check out</span></span> | <span data-ttu-id="e7349-127">Gdy wyewidencjonowany element CMS zostanie odrzucony, wszystkie zapisane zmiany zostaną usunięte, a pozycja zostanie przywrócona do wersji, która była ostatnio zaewidencjonowana.</span><span class="sxs-lookup"><span data-stu-id="e7349-127">When a checked-out CMS item is discarded, all saved changes are deleted, and the item reverts to the version that was most recently checked in.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="e7349-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e7349-128">Additional resources</span></span>

[<span data-ttu-id="e7349-129">Sposoby dodawania zawartości</span><span class="sxs-lookup"><span data-stu-id="e7349-129">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="e7349-130">Słownik terminów dotyczących modelu strony</span><span class="sxs-lookup"><span data-stu-id="e7349-130">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="e7349-131">Praca z grupami publikowania</span><span class="sxs-lookup"><span data-stu-id="e7349-131">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="e7349-132">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="e7349-132">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="e7349-133">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="e7349-133">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="e7349-134">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="e7349-134">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="e7349-135">Dostosowywanie nawigacji w witrynie</span><span class="sxs-lookup"><span data-stu-id="e7349-135">Customize site navigation</span></span>](customize-site-navigation.md)

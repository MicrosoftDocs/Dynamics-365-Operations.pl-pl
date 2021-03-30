---
title: Dokumentowanie stanów i cyklów życia
description: Ten temat dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 457b1ac7afb8cad57399572acf429d208db917af
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230541"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="198c8-103">Dokumentowanie stanów i cyklów życia</span><span class="sxs-lookup"><span data-stu-id="198c8-103">Document states and lifecycle</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="198c8-104">Ten temat dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="198c8-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="198c8-105">Opis opisu stanu</span><span class="sxs-lookup"><span data-stu-id="198c8-105">Document state descriptions</span></span>

<span data-ttu-id="198c8-106">Temat [Elementy stony](page-elements-overview.md) zawiera listę różnych typów dokumentów w systemie zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="198c8-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="198c8-107">Te typy dokumentów mogą mieć kilka stanów w narzędziu do tworzenia treści.</span><span class="sxs-lookup"><span data-stu-id="198c8-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="198c8-108">Dokument ułatwia zapobieganie konfliktom danych i egzekwowanie kontroli wersji.</span><span class="sxs-lookup"><span data-stu-id="198c8-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="198c8-109">Określają one, kto może zmieniać dokumenty, kiedy dokumenty mogą być zmieniane i kiedy zmiany mogą być przeglądane przez inne osoby.</span><span class="sxs-lookup"><span data-stu-id="198c8-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="198c8-110">W poniższej tabeli przedstawiono stany dokumentów elementów strony w Commerce.</span><span class="sxs-lookup"><span data-stu-id="198c8-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="198c8-111">Stan dokumentu</span><span class="sxs-lookup"><span data-stu-id="198c8-111">Document state</span></span>      | <span data-ttu-id="198c8-112">Akcja konstruktora witryn</span><span class="sxs-lookup"><span data-stu-id="198c8-112">Site builder action</span></span>        | <span data-ttu-id="198c8-113">opis</span><span class="sxs-lookup"><span data-stu-id="198c8-113">Description</span></span>                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="198c8-114">Wyewidencjonowano</span><span class="sxs-lookup"><span data-stu-id="198c8-114">Checked out</span></span>         | <span data-ttu-id="198c8-115">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="198c8-115">Select **Edit**.</span></span>           | <span data-ttu-id="198c8-116">Właściwy dokument został wyewidencjonowany dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="198c8-116">The applicable document is checked out to you.</span></span> <span data-ttu-id="198c8-117">Dokument jest w tym stanie, ale nie może być zmieniany przez innych uwierzytelnionych użytkowników systemu, a wszelkie zmiany wprowadzone w dokumencie są widoczne tylko dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="198c8-117">While a document is in this state, it can't be changed by other authenticated system users, and any changes that you make to the document are visible only to you.</span></span> |
| <span data-ttu-id="198c8-118">Zapisano</span><span class="sxs-lookup"><span data-stu-id="198c8-118">Saved</span></span>               | <span data-ttu-id="198c8-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="198c8-119">Select **Save**.</span></span>           | <span data-ttu-id="198c8-120">Zmiany wprowadzone w wyewidencjonowanym dokumencie są zapisywane w bazie danych, ale dokument nie został jeszcze zaewidencjonowany ani opublikowany.</span><span class="sxs-lookup"><span data-stu-id="198c8-120">Changes that have been made to a checked-out document are saved to the database, but the document isn't yet checked in or published.</span></span> <span data-ttu-id="198c8-121">Te zapisane zmiany nie są widoczne dla innych uwierzytelnionych użytkowników systemu, dopóki autor nie wybierze **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="198c8-121">The saved changes aren't visible to other authenticated system users until the author selects **Finish editing**.</span></span> <span data-ttu-id="198c8-122">Nie są one widoczne dla użytkowników zewnętrznych do momentu opublikowania elementu.</span><span class="sxs-lookup"><span data-stu-id="198c8-122">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="198c8-123">Odrzucone wyewidencjonowanie</span><span class="sxs-lookup"><span data-stu-id="198c8-123">Discarded check out</span></span> | <span data-ttu-id="198c8-124">Wybierz opcję **Odrzuć edycje**.</span><span class="sxs-lookup"><span data-stu-id="198c8-124">Select **Discard edits**.</span></span>  | <span data-ttu-id="198c8-125">Wszystkie zmiany wprowadzone w wyewidencjonowanym dokumencie zostaną odrzucone, a towar zostanie przywrócony do ostatniej wersji, która została zaewidencjonowana.</span><span class="sxs-lookup"><span data-stu-id="198c8-125">All changes to the checked-out document are discarded, and the item reverts to the last version that was checked in.</span></span> |
| <span data-ttu-id="198c8-126">Zaewidencjonowano</span><span class="sxs-lookup"><span data-stu-id="198c8-126">Checked in</span></span>          | <span data-ttu-id="198c8-127">Wybierz opcję **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="198c8-127">Select **Finish editing**.</span></span> | <span data-ttu-id="198c8-128">Edytowany dokument jest zaewidencjonowany.</span><span class="sxs-lookup"><span data-stu-id="198c8-128">The edited document is checked in.</span></span> <span data-ttu-id="198c8-129">Wszystkie zmiany są widoczne dla innych uwierzytelnionych użytkowników systemu, a następnie użytkownicy mogą edytować ten dokument.</span><span class="sxs-lookup"><span data-stu-id="198c8-129">All changes are visible to other authenticated system users, and those users can then edit the document.</span></span> <span data-ttu-id="198c8-130">Każde ewidencjonowanie utworzy rekord wersji dokumentu w historii pozycji.</span><span class="sxs-lookup"><span data-stu-id="198c8-130">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="198c8-131">Opublikowany</span><span class="sxs-lookup"><span data-stu-id="198c8-131">Published</span></span>           | <span data-ttu-id="198c8-132">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="198c8-132">Select **Publish**.</span></span>        | <span data-ttu-id="198c8-133">Dokument jest opublikowany, a zmiany są przekazywane do witryny na żywo i stają się wykrywalne przez użytkowników zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="198c8-133">The document is published, and the changes are pushed to your live site and become discoverable by external users.</span></span> <span data-ttu-id="198c8-134">Towary mogą być publikowane tylko wtedy, gdy zostały najpierw zaewidencjonowane przez kliknięcie przycisku **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="198c8-134">Items can be published only if they have first been checked in by selecting **Finish editing**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="198c8-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="198c8-135">Additional resources</span></span>

[<span data-ttu-id="198c8-136">Sposoby dodawania zawartości</span><span class="sxs-lookup"><span data-stu-id="198c8-136">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="198c8-137">Słownik terminów dotyczących modelu strony</span><span class="sxs-lookup"><span data-stu-id="198c8-137">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="198c8-138">Praca z grupami publikowania</span><span class="sxs-lookup"><span data-stu-id="198c8-138">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="198c8-139">Włączanie i używanie udostępniania między kanałami</span><span class="sxs-lookup"><span data-stu-id="198c8-139">Enable and use cross-channel sharing</span></span>](cross-channel-sharing.md)

[<span data-ttu-id="198c8-140">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="198c8-140">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="198c8-141">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="198c8-141">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="198c8-142">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="198c8-142">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="198c8-143">Dostosowywanie nawigacji w witrynie</span><span class="sxs-lookup"><span data-stu-id="198c8-143">Customize site navigation</span></span>](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
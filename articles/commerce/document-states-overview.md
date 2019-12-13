---
title: Dokumentowanie stanów i cyklów życia
description: Ten temat dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: a34d10edbf84ac1814afdc7107727aea68a303e0
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770442"
---
# <a name="document-states-and-lifecycle"></a>Dokumentowanie stanów i cyklów życia

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ten temat dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Opis opisu stanu

Temat [Elementy stony](page-elements-overview.md) zawiera listę różnych typów dokumentów w systemie zarządzania zawartością (CMS). Te typy dokumentów mogą mieć kilka stanów w narzędziu do tworzenia treści. Dokument ułatwia zapobieganie konfliktom danych i egzekwowanie kontroli wersji. Określają one, kto może zmieniać dokumenty, kiedy dokumenty mogą być zmieniane i kiedy zmiany mogą być przeglądane przez inne osoby.

W poniższej tabeli przedstawiono stany dokumentów elementów strony w Commerce.

| Stan dokumentu | Opis |
|---|---|
| Wyewidencjonowano | Gdy element CMS jest wyewidencjonowany dla danego użytkownika, nie może być edytowany przez żadnego innego uwierzytelnionego użytkownika systemu. Wszelkie zmiany wprowadzone w elemencie są widoczne tylko dla Ciebie. |
| Zaewidencjonowano | Gdy element CMS jest zaewidencjonowany, wszystkie zmiany są widoczne dla innych uwierzytelnionych użytkowników systemu, a użytkownicy mogą następnie wyewidencjonować ten element i edytować go. Każde ewidencjonowanie utworzy rekord wersji dokumentu w historii pozycji. |
| Opublikowane | Po opublikowaniu element CMS jest przesunięty do witryny na żywo i staje się wykrywalny w Internecie przez nieuwierzytelnionych użytkowników zewnętrznych. Towary mogą być publikowane tylko wtedy, gdy zostały zaewidencjonowane. |
| Zapisano | Zmiany wprowadzone w wyewidencjonowanym elemencie CMS można zapisać w CMS przed zapisaniem lub opublikowaniem elementu. Te zapisane zmiany nie są widoczne dla innych uwierzytelnionych użytkowników systemu, dopóki element nie zostanie zaewidencjonowany. Nie są one widoczne dla użytkowników zewnętrznych do momentu opublikowania elementu. |
| Odrzucone wyewidencjonowanie | Gdy wyewidencjonowany element CMS zostanie odrzucony, wszystkie zapisane zmiany zostaną usunięte, a pozycja zostanie przywrócona do wersji, która była ostatnio zaewidencjonowana. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Sposoby dodawania zawartości](add-manage-content.md)

[Słownik terminów dotyczących modelu strony](page-elements-overview.md)

[Praca z modułami](work-with-modules.md)

[Praca z fragmentami](work-with-fragments.md)

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Dostosowywanie nawigacji w witrynie](customize-site-navigation.md)

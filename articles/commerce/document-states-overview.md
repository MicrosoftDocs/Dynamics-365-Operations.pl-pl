---
title: Dokumentowanie stanów i cyklów życia
description: Ten artykuł dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: intro-internal
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 350b3236eec6ad6520025bf44b22f12366f1e266
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269924"
---
# <a name="document-states-and-lifecycle"></a>Dokumentowanie stanów i cyklów życia

[!include [banner](includes/banner.md)]

Ten artykuł dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Opis opisu stanu

Artykuł [Elementy stony](page-elements-overview.md) zawiera listę różnych typów dokumentów w systemie zarządzania zawartością (CMS). Te typy dokumentów mogą mieć kilka stanów w narzędziu do tworzenia treści. Dokument ułatwia zapobieganie konfliktom danych i egzekwowanie kontroli wersji. Określają one, kto może zmieniać dokumenty, kiedy dokumenty mogą być zmieniane i kiedy zmiany mogą być przeglądane przez inne osoby.

W poniższej tabeli przedstawiono stany dokumentów elementów strony w Commerce.

| Stan dokumentu      | Akcja konstruktora witryn        | opis                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Wyewidencjonowano         | Wybierz opcję **Edycja**.           | Właściwy dokument został wyewidencjonowany dla Ciebie. Dokument jest w tym stanie, ale nie może być zmieniany przez innych uwierzytelnionych użytkowników systemu, a wszelkie zmiany wprowadzone w dokumencie są widoczne tylko dla użytkownika. |
| Zapisano               | Wybierz opcję **Zapisz**.           | Zmiany wprowadzone w wyewidencjonowanym dokumencie są zapisywane w bazie danych, ale dokument nie został jeszcze zaewidencjonowany ani opublikowany. Te zapisane zmiany nie są widoczne dla innych uwierzytelnionych użytkowników systemu, dopóki autor nie wybierze **Zakończ edycję**. Nie są one widoczne dla użytkowników zewnętrznych do momentu opublikowania elementu. |
| Odrzucone wyewidencjonowanie | Wybierz opcję **Odrzuć edycje**.  | Wszystkie zmiany wprowadzone w wyewidencjonowanym dokumencie zostaną odrzucone, a towar zostanie przywrócony do ostatniej wersji, która została zaewidencjonowana. |
| Zaewidencjonowano          | Wybierz opcję **Zakończ edycję**. | Edytowany dokument jest zaewidencjonowany. Wszystkie zmiany są widoczne dla innych uwierzytelnionych użytkowników systemu, a następnie użytkownicy mogą edytować ten dokument. Każde ewidencjonowanie utworzy rekord wersji dokumentu w historii pozycji. |
| Opublikowany           | Wybierz opcję **Publikuj**.        | Dokument jest opublikowany, a zmiany są przekazywane do witryny na żywo i stają się wykrywalne przez użytkowników zewnętrznych. Towary mogą być publikowane tylko wtedy, gdy zostały najpierw zaewidencjonowane przez kliknięcie przycisku **Zakończ edycję**. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Sposoby dodawania zawartości](add-manage-content.md)

[Słownik terminów dotyczących modelu strony](page-elements-overview.md)

[Praca z grupami publikowania](publish-groups.md)

[Włączanie i używanie udostępniania między kanałami](cross-channel-sharing.md)

[Praca z modułami](work-with-modules.md)

[Praca z fragmentami](work-with-fragments.md)

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Dostosowywanie nawigacji w witrynie](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

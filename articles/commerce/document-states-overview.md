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
# <a name="document-states-and-lifecycle"></a>Dokumentowanie stanów i cyklów życia

[!include [banner](includes/banner.md)]

Ten temat dotyczy różnych stanów dokumentów elementów strony w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Opis opisu stanu

Temat [Elementy stony](page-elements-overview.md) zawiera listę różnych typów dokumentów w systemie zarządzania zawartością (CMS). Te typy dokumentów mogą mieć kilka stanów w narzędziu do tworzenia treści. Dokument ułatwia zapobieganie konfliktom danych i egzekwowanie kontroli wersji. Określają one, kto może zmieniać dokumenty, kiedy dokumenty mogą być zmieniane i kiedy zmiany mogą być przeglądane przez inne osoby.

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
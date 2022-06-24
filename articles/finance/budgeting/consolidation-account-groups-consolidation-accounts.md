---
title: Grupy kont konsolidacyjnych i dodatkowe konta konsolidacyjne
description: Ten artykuł zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane.
author: panolte
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9e66190fe0bab24545bf19eba59facded63ee197
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882028"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Grupy kont konsolidacyjnych i dodatkowe konta konsolidacyjne

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane.

## <a name="consolidation-account-groups"></a>Grupy kont konsolidacji

Grupy kont konsolidacji pozwalają tworzyć grupy kont, które mają użyć do konsolidowania danych. Zazwyczaj grupa kont konsolidacyjnych reprezentuje rządowy plan kont. Grupa kont konsolidacyjnych może również mapować konta na grupę zdefiniowaną w centrali firmy. Grupy kont konsolidacji są podane w module **Konsolidacje** w obszarze **Ustawienia**. Podczas dodawania nowej grupy wprowadzasz unikatowy identyfikator oraz nazwę grupy kont.

## <a name="additional-consolidation-accounts"></a>Dodatkowe konta konsolidacji
Funkcja dodatkowych kont konsolidacji umożliwia przypisanie konta z istniejącego planu kont do grupy kont konsolidacji. Następnie można określić wartość i nazwę konta konsolidacji. 

Dodatkowe konta konsolidacji są podane w module **Konsolidacje** w obszarze **Ustawienia**. Podczas tworzenia nowego konta konsolidacji należy określić następujące informacje:

-   **Konto główne** — To pole jest odnośnikiem, który pokazuje wszystkie konta główne oparte na plan kont wybranym na stronie. Po wybraniu konta nazwa jest automatycznie wprowadzana w polu **Nazwa konta głównego**.
-   **Grupa kont konsolidacji** — To pole służy określaniu grupy, do której ma zostać przypisane konto. Jeśli konsolidujesz na dwa różne sposoby, należy dodać to samo konto do wszystkich czterech grup kont konsolidacji.
-   **Konto konsolidacji** — Wprowadź wartość konta konsolidacji. Ta wartość nie musi określać konta z planu kont. To może być dowolne inne konto.
-   **Nazwa konta konsolidacji** — Wprowadź nazwę konta w postaci, w jakiej ma być wyświetlana w zapytaniach i raportach.
-   **Poziom SAT** — To pole służy do zgłaszania wyciągów z kont meksykańskiemu urzędowi skarbowemu. 

Po zakończeniu tworzenia grup kont konsolidacji i dodatkowych kont konsolidacji można wybrać grupę w procesie konsolidacji online.


Aby uzyskać więcej informacji, zobacz [Tworzenie grup konsolidacji i dodatkowych kont konsolidacyjnych](../general-ledger/tasks/create-consolidation-groups.md). 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

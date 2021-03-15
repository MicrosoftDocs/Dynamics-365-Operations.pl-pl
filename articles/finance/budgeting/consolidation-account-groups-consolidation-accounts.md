---
title: Grupy kont konsolidacji i dodatkowe konta konsolidacji
description: Ten temat zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane w Microsoft Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5a4e3b4d7bb1d5feefd843cdc347b4a08f94a85a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982195"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Grupy kont konsolidacji i dodatkowe konta konsolidacji

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane w Microsoft Dynamics 365 Finance.

<a name="consolidation-account-groups"></a>Grupy kont konsolidacji
----------------------------

Grupy kont konsolidacji pozwalają tworzyć grupy kont, które mają użyć do konsolidowania danych. W większości przypadków grupa kont konsolidacji reprezentuje urzędowy plan kont lub mapuje konta na grupę zdefiniowaną przez centralę firmy. Grupy kont konsolidacji są podane w module **Konsolidacje** w obszarze **Ustawienia**. Podczas dodawania nowej grupy wprowadzasz unikatowy identyfikator i nazwę grupy kont.

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
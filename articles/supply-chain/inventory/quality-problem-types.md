---
title: Typy problemów w niezgodnościach
description: W tym artykule opisano sposób tworzenia i używania typów problemów w niezgodnościach.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a73e692257c2a27085d60e75e028445811ee778a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857758"
---
# <a name="problem-types-for-nonconformances"></a>Typy problemów w niezgodnościach

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób tworzenia i używania typów problemów w niezgodnościach.

Strona **Typ problemu** służy do definiowania klasyfikacji problemów z jakością, które mogą występować w różnych typach niezgodności. Dla każdego tworzonego problemu należy określić typy niezgodności, z którymi będzie on używany. Możliwe jest skonfigurowanie następujących typów niezgodności:

- **Wewnętrzne** — niezgodności tego typu są związane z dostępnymi zapasami (na przykład zleceniami kontroli jakości lub zleceniami kwarantanny).
- **Odbiorca** — niezgodności tego typu są związane z zamówieniami sprzedaży.
- **Dostawca** — niezgodności tego typu są związane z zamówieniami zakupu.
- **Zlecenie usługi** — niezgodności tego typu są związane ze zleceniami serwisowymi.
- **Produkcja** — Niezgodności tego typu są związane z zamówieniami partii lub zleceniami produkcyjnymi.
- **Wytwarzanie produktu towarzyszącego** — Niezgodności tego typu są związane z zamówieniami partii na produkty towarzyszące.

Podczas tworzenia nowego typu problemu w okienku akcji wybierz opcję **Typy niezgodności**, aby utworzyć listę co najmniej jednego typu niezgodności autoryzowanych dla tego typu problemu. Dzięki temu typ problemu, który jest związany z wadliwym kodem, może być stosowany do wszystkich typów niezgodności. Jednak typ problemu związany ze skargami klientów może dotyczyć tylko typów niezgodności **Odbiorca** i **Zlecenie usługi**.

## <a name="examples-of-problem-types"></a>Przykłady typów problemu

Oto kilka przykładów scenariuszy typów problemów, których można używać z różnymi typami niezgodności:

- **Odbiorca:** złożenie reklamacji przez odbiorcę, wykonanie zwrotu przez odbiorcę lub niespełnienie specyfikacji jakościowych.
- **Dostawca:** produkt został uszkodzony, specyfikacje jakości nie zostały spełnione lub odebrano niewłaściwy produkt.
- **Zlecenie usługi:** niespełnienie specyfikacji jakościowych, złożenie reklamacji przez odbiorcę lub wymagana konserwacja maszyny.
- **Produkcja:** specyfikacje jakości nie zostały spełnione, konserwacja maszyny jest wymagana lub produkt został uszkodzony.
- **Wytwarzanie produktu towarzyszącego:** specyfikacje jakości nie zostały spełnione, konserwacja maszyny jest wymagana lub produkt został uszkodzony.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>Tworzenie typu problemu i przypisywanie go do typów niezgodności

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Typy problemów**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Typ problemu** — służy do wprowadzania unikatowego identyfikatora lub nazwy typu problemu.
    - **Opis** – wprowadź szczegółowy opis typu problemu.

1. Gdy nowy wiersz jest nadal zaznaczony, wybierz opcję **Typy niezgodności** w okienku akcji.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie dla nowego wiersza ustaw w polu **Typ niezgodności** typ niezgodności, który ma być dozwolony dla tego typu problemu.
1. Powtórz poprzedni krok dla każdego dodatkowego typu niezgodności, który chcesz autoryzować dla tego typu problemu.
1. Zamknij strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzanie jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Pracownicy odpowiedzialni za zatwierdzanie niezgodności](quality-responsible-workers.md)
- [Strefy kwarantanny niezgodności](quality-quarantine-zones.md)
- [Typy diagnostyki niezgodności](quality-diagnostic-types.md)
- [Opłaty związane z kontrolą jakości dla niezgodności](quality-charges.md)
- [Operacje dotyczące niezgodności](quality-operations.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

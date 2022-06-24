---
title: Operacje dotyczące niezgodności
description: W tym artykule opisano sposób tworzenia i używania operacji dotyczących niezgodności.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2e63156dd2b230da7f1ea89e2c2006c1b4f3eeb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847999"
---
# <a name="operations-for-nonconformances"></a>Operacje dotyczące niezgodności

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób tworzenia i używania operacji dotyczących niezgodności.

Za pomocą strony **Operacje** można zdefiniować klasyfikacje pracy, którą można wykonać dla zatwierdzonej niezgodności. Przypisując operację pokrewną do niezgodności, można również zdefiniować szczegóły, jak powiązany materiał, godziny robocizny i opłaty wymagane do wykonania operacji. Ta informacja służy systemowi do obliczania szacowanego kosztu operacji. Informacje szczegółowe i szacowane koszty mają charakter odnośnikowy. Operacje pokrewne dla jakości różnią się od operacji, które można zdefiniować dla marszruty produkcji.

> [!NOTE]
> Chociaż można śledzić koszty, czas i towary używane w operacji związanej z niezgodnością, wprowadzone dane mają wyłącznie informacyjny charakter. Nie są automatycznie integrowane z księgą główną, księgą podrzędną zapasów lub modułem **Czas i frekwencja**.

## <a name="examples-of-operations"></a>Przykłady operacji

Pracujesz dla firmy produkcyjnej. Utworzono i zatwierdzono niezgodność dla towarów, które nie przeszły testu jakości. Utworzono korektę wskazującą, że problem był związany z wadliwym łożyskiem w maszynie. Wymiana łożyska wymaga wykonania kilku czynności, a odpowiedzialność za każdą operację jest śledzona. Mogą być na przykład wymagane następujące kroki:

1. Zatrzymanie linii produkcyjnej i przeprowadzenie procedury czyszczenia.
1. Wymiana łożyska przez serwis.
1. Inspekcja maszyny przez personel zapewnienia jakości przed włączeniem z powrotem maszyny.

W tym przykładzie można utworzyć następujące operacje reprezentujące pracę, która musi zostać wykonana:

- Zatrzymaj linię produkcyjną.
- Oczyść linię produkcyjną.
- Wykonaj konserwację maszyny.
- Skontroluj maszynę.

## <a name="create-an-operation"></a>Tworzenie operacji

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Operacje**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Operacja** — umożliwia wprowadzenie unikatowego identyfikatora lub nazwy operacji.
    - **Opis** – wprowadź szczegółowy opis operacji.
    - **Typ** — jeśli operacja może być używana tylko z niezgodnościami związanymi z określonym typem zamówienia, należy wybrać typ zamówienia (*Zamówienie zakupu* lub *Zamówienie sprzedaży)*.

1. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzanie jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Tworzenie i przetwarzanie niezgodności](tasks/create-process-non-conformance.md)
- [Pracownicy odpowiedzialni za zatwierdzanie niezgodności](quality-responsible-workers.md)
- [Strefy kwarantanny niezgodności](quality-quarantine-zones.md)
- [Typy diagnostyki niezgodności](quality-diagnostic-types.md)
- [Opłaty związane z kontrolą jakości dla niezgodności](quality-charges.md)
- [Typy problemów w niezgodnościach](quality-operations.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

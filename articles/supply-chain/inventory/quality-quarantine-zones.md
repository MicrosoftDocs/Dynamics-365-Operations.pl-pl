---
title: Strefy kwarantanny niezgodności
description: W tym temacie opisano sposób tworzenia i używania stref kwarantanny w niezgodnościach.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 207950a2ff4057853488f75d0e302a049d228b76
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578471"
---
# <a name="quarantine-zones-for-nonconformances"></a>Strefy kwarantanny niezgodności

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia i używania stref kwarantanny w niezgodnościach.

Strona **Strefy kwarantanny** służy do definiowania stref, które można przypisać do niezgodności. Podczas tworzenia niezgodności można ustawić pola **Strefa kwarantanny** i **Typ kwarantanny** na karcie **Ogólne** na stronie **Niezgodności**. Pole **Strefa kwarantanny** zazwyczaj wskazuje obszar lub lokalizację, w której znajduje się towar. Pole **Typ kwarantanny** definiuje towar jako *Ograniczone użycie* lub *Nienadający się do użytku*.

Podczas drukowania raportu o niezgodności lub korektach dla niezgodności można wyświetlić strefę kwarantanny, w której znajduje się towar.

Dla niezgodności można również wydrukować znacznik niezgodności. W tym raporcie jest pokazana przypisana strefa kwarantanny wraz ze wskazówkami postępowania z wadliwymi materiałami. Strefy kwarantanny mogą odpowiadać lokalizacjom magazynowym lub zasobom operacyjnym.

## <a name="examples-of-quarantine-zones"></a>Przykładowe strefy kwarantanny

### <a name="example-1"></a>Przykład 1

Pracujesz w firmie, która produkuje i rozprowadza telewizory, głośniki i odtwarzacze multimedialne. W takim przypadku można skonfigurować strefy kwarantanny reprezentujące poszczególne typy produktu.

### <a name="example-2"></a>Przykład 2

Trzy pojemniki i dwa regały służą do przechowywania towarów, które wykazują niezgodności. W takim przypadku można skonfigurować pięć stref kwarantanny, po jednej dla każdego pojemnika i każdego regału.

## <a name="create-a-quarantine-zone"></a>Tworzenie strefy kwarantanny

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Strefy kwarantanny**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Strefa kwarantanny** — służy do wprowadzania unikatowego identyfikatora lub nazwy strefy kwarantanny.
    - **Opis** – wprowadź szczegółowy opis strefy kwarantanny.

1. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzanie jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Pracownicy odpowiedzialni za zatwierdzanie niezgodności](quality-responsible-workers.md)
- [Typy problemów w niezgodnościach](quality-quarantine-zones.md)
- [Typy diagnostyki niezgodności](quality-diagnostic-types.md)
- [Opłaty związane z kontrolą jakości dla niezgodności](quality-charges.md)
- [Operacje dotyczące niezgodności](quality-operations.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

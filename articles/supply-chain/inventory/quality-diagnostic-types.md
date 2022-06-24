---
title: Typy diagnostyki niezgodności
description: W tym artykule opisano sposób tworzenia i używania typów diagnostyki, które mogą być używane z niezgodnościami.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87b7a051f807c9faab3169d2672d47f663892225
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852455"
---
# <a name="diagnostic-types-for-nonconformances"></a>Typy diagnostyki niezgodności

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób tworzenia i używania typów diagnostyki, które mogą być używane z niezgodnościami.

Strona **Typy diagnostyki** służy do definiowania klasyfikacji akcji diagnostycznych. Następnie podczas tworzenia korekty niezgodności należy wybrać diagnostykę. Korekta określa jakiego rodzaju działania diagnostyczne należy podjąć w przypadku zatwierdzonej niezgodności, a także osobę, która ma to działanie wykonać. Określa również żądaną datę ukończenia żądania planowaną datę ukończenia.

## <a name="examples-of-diagnostic-types"></a>Przykłady typów diagnostyki

Pracujesz w firmie produkcyjnej i masz towary, które nie przeszły testów kontroli jakości. Towary te są przenoszone do obszaru kwarantanny i oznaczane jako produkty niezgodności. Rekord niezgodności jest tworzony w systemie Microsoft Dynamics 365 Supply Chain Management w celu śledzenia szczegółów do rozwiązania problemu.

W tym przypadku problemy z jakością są spowodowane zatarciem i przegrzaniem łożysk w maszynie pakującej towary. Korekta tego problemu polega na wymianie części w maszynie.

Podczas konfigurowania typów diagnostyki można utworzyć wiele rekordów, z których każdy reprezentuje inny typ problemu, jaki może wystąpić w maszynie. Można również utworzyć jeden ogólny typ diagnostyki, który reprezentuje naprawę maszyny.

## <a name="create-a-diagnostic-type"></a>Tworzenie typu diagnostyki

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Typy diagnostyki**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Diagnostyka** — służy do wprowadzania unikatowego identyfikatora lub nazwy typu diagnostyki.
    - **Opis** – wprowadź szczegółowy opis typu diagnostyki.

1. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzanie jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Pracownicy odpowiedzialni za zatwierdzanie niezgodności](quality-responsible-workers.md)
- [Strefy kwarantanny niezgodności](quality-quarantine-zones.md)
- [Typy problemów w niezgodnościach](quality-problem-types.md)
- [Opłaty związane z kontrolą jakości dla niezgodności](quality-charges.md)
- [Operacje dotyczące niezgodności](quality-operations.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

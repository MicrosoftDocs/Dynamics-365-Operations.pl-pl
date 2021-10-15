---
title: Opłaty za operacje dotyczące niezgodności
description: W tym temacie opisano sposób tworzenia opłat związanych z kontrolą jakości, które mogą być naliczane za operacje dotyczące niezgodności.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac3306f3f9215ab03f408b8026f335dcf496515a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580967"
---
# <a name="charges-for-nonconformance-operations"></a>Opłaty za operacje dotyczące niezgodności

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia opłat związanych z kontrolą jakości, które mogą być naliczane za operacje dotyczące niezgodności.

Strona **Opłaty związane z kontrolą jakości** służy do definiowania typów opłat, które można dodawać do operacji dotyczących niezgodności. Opłaty umożliwiają śledzenie szczegółów dotyczących obciążeń lub opłat, które są należne odbiorcy za niezgodne produkty lub należne od dostawcy za otrzymane niezgodne produkty. Opłat można również użyć do śledzenia kosztów, które są wymagane dla zewnętrznych dostawców lub usług w celu wykonania operacji.

## <a name="examples-of-quality-charges"></a>Przykłady opłat związanych z kontrolą jakości

Pracujesz dla firmy produkcyjnej. Twoja firma ma kontrakty z kilkoma dostawcami. W tych umowach są określone standardy wysyłki na czas, uszkodzeń i jakości produktów dla towarów. Analogicznie, masz zawarte z kilkoma odbiorcami umowy dotyczące zwrotów, uszkodzeń i jakości produktów.

Struktura opłat jest definiowana dla każdej okoliczności i określona w umowie. Opłaty związane z kontrolą jakości można konfigurować jako kontur różnych typów opłat, takich jak *Uszkodzenia*, *Opóźnienie wysyłki* czy *Jakość*. Następnie podczas tworzenia niezgodności dodajesz jedną lub więcej operacji. Dla każdej operacji należy wybrać opcję **Opłaty**, aby zdefiniować szczegóły dotyczące opłat.

## <a name="create-a-quality-charge"></a>Tworzenie opłaty związanej z kontrolą jakości

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zarządzanie jakością \> Opłaty związane z kontrolą jakości**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Kod opłaty** — służy do wprowadzania unikatowego identyfikatora lub nazwy opłaty związanej z kontrolą jakości.
    - **Opis** – wprowadź szczegółowy opis opłaty związanej z kontrolą jakości.

1. Zamknij stronę.

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>Dodawanie opłaty związanej z kontrolą jakości do operacji dotyczącej niezgodności

Aby uzyskać szczegółowe informacje dotyczące dodawania operacji do niezgodności i stosowania za nią opłat, zobacz temat [Operacje dotyczące niezgodności](quality-operations.md).

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

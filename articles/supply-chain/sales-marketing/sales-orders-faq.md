---
title: Często zadawane pytania dotyczące zamówień sprzedaży
description: Na tej stronie znajdują się odpowiedzi na często zadawane pytania dotyczące pracy z zamówieniami sprzedaży w programie Dynamics 365 Supply Chain Management.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d75022dcc476052040b16c9033cf5ff2a697ae6c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477299"
---
# <a name="sales-order-faqs"></a>Zamówienie sprzedaży — często zadawane pytania

Na tej stronie znajdują się odpowiedzi na często zadawane pytania dotyczące pracy z zamówieniami sprzedaży w programie Dynamics 365 Supply Chain Management.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Czy można połączyć zamówienie zakupu z zamówieniem sprzedaży, aby zrealizować zapotrzebowanie?

Można utworzyć zamówienia zakupu na podstawie zamówienia sprzedaży. Aby uzyskać więcej informacji, zobacz [Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order).

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>Czy można anulować lub usunąć zamówienie sprzedaży lub zamówienie zwrotu?

Można anulować tylko zamówienia sprzedaży i zamówienia zwrotu, które są w stanie *Utworzone*. Aby uzyskać więcej informacji, zobacz [Anulowanie zamówienia zwrotu](/dynamics365/supply-chain/service-management/cancel-return-order).

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Czy można przywrócić zafakturowane zamówienie sprzedaży, które zostało usunięte?

Jeśli zafakturowane zamówienie sprzedaży zostało usunięte przez pomyłkę, można przywrócić je lub wyświetlić jego szczegóły.

Przejdź do strony **Konto odbiorcy \> Transakcje \> Oryginalny dokument \> Wyświetl szczegóły**. Znajdź szukaną fakturę i wybierz ją, aby wyświetlić jej szczegóły. Szczegóły zawierają odwołanie do zamówienia sprzedaży. Należy również uzyskać dostęp do szczegółów zamówienia sprzedaży z tej strony.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>Jak usunąć oddzielone rekordy zamówienia sprzedaży?

Aby oczyścić rekordy oddzielonych rekordów zamówienia sprzedaży, należy uruchomić zadanie okresowe *Usuwanie zamówień sprzedaży*, przechodząc do jednej z następujących lokalizacji:

- Sprzedaż i marketing \> Zadania okresowe \> Oczyszczanie \> Usuwanie zamówień zakupu
- Handel detaliczny i inny \> Retail i Commerce — składniki IT \> Wyczyść \> Usuwanie zamówień zakupu

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Czy istnieje sposób obliczania prowizji dla faktur, które zostały już zaksięgowane?

Supply Chain Management nie obsługuje obecnie obliczania prowizji za zaksięgowane faktury.

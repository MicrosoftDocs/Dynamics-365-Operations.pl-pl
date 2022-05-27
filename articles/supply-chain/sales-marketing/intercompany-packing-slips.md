---
title: Międzyfirmowe dokumenty dostawy
description: W tym temacie opisano sposób generowania i drukowania dokumentów dostawy dla transakcji międzyfirmowych
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ca569ca7eb2a3ced36904442212bde565f499f94
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678639"
---
# <a name="intercompany-packing-slips"></a>Międzyfirmowe dokumenty dostawy

## <a name="generate-intercompany-packing-slips"></a>Generuj międzyfirmowe dokumenty dostawy

[!include [banner](../../includes/banner.md)]

Jeśli pracujesz z dostawą bezpośrednią, dokument dostawy jest zawsze generowany automatycznie zarówno na międzyfirmowym zamówieniu zakupu, jak i na oryginalnym zamówieniu sprzedaży podczas generowania dokumentu dostawy na międzyfirmowym zamówieniu sprzedaży. Faktura międzyfirmowego zamówienia zakupu jest oparta na wcześniej wygenerowanym dokumencie dostawy międzyfirmowego zamówienia zakupu.

Jeśli wprowadzisz jakiekolwiek aktualizacje dokumentu dostawy w międzyfirmowym zamówieniu sprzedaży, te aktualizacje zostaną odzwierciedlone zarówno w międzyfirmowym zamówieniu zakupu, jak i w oryginalnym zamówieniu sprzedaży.

Jeśli nie pracujesz z dostawą bezpośrednią, musisz ręcznie wygenerować dokument dostawy na międzyfirmowym zamówieniu sprzedaży, międzyfirmowym zamówieniu zakupu i oryginalnym zamówieniu sprzedaży.

## <a name="print-intercompany-packing-slips"></a>Wydrukuj międzyfirmowe dokumenty przewozowe

[!include [banner](../../includes/banner.md)]

W przypadku pracy z dostawą bezpośrednią dokument dostawy może być wydrukowany automatycznie dla międzyfirmowego zamówienia zakupu i oryginalnego zamówienia sprzedaży podczas księgowania dokumentu dostawy w międzyfirmowym zamówieniu sprzedaży.

Aby automatycznie drukować dokumenty dostawy, na stronie **Międzyfirmowe** dla zamówień zakupu zaznacz oba pola automatycznie **drukuj dokument dostawy**.

Jeśli zaktualizujesz dokument dostawy w międzyfirmowym zamówieniu sprzedaży, zmiany są automatycznie odzwierciedlane w międzyfirmowym zamówieniu zakupu i oryginalnym zamówieniu sprzedaży.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

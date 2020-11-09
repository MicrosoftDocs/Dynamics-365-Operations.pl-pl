---
title: Dostępność zapasów w podwójnym zapisie
description: Ten temat zawiera informacje o sposobie sprawdzania dostępności zapasów w trybie podwójnego zapisu.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997899"
---
# <a name="inventory-availability-in-dual-write"></a>Dostępność zapasów w podwójnym zapisie

[!include [banner](../../includes/banner.md)]

Korzystając z dostępności zapasów, można sprawdzić stan zapasów przed dodaniem produktu do stron **Oferty** , **Zamówienia** lub **Faktury** w Microsoft Dynamics 365 Sales. Na przykład sprawdzenie zapasów i określenie daty realizacji jest jednym z kluczowych zadań w procesie [od prospektu do gotówki](dual-write-prospect-to-cash.md).

Jeśli nie ma wystarczającej ilości zapasów, można oszacować datę dostawy na podstawie przewidywanych przyjęć i problemów z zapasami. Można również sprawdzić informacje o dostępności zapasów (ATP), w której można znaleźć ilość ATP w wstępnie zdefiniowanym horyzoncie czasowym.

## <a name="on-hand-inventory"></a>Dostępne zapasy

W Dynamics 365 Sales jest dodany nowy przycisk **Dostępne zapasy** do nagłówka stron **Oferty** , **Zamówienia** i **Faktury**. Wybranie tego przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę i produkt, dla którego mają zostać sprawdzone dostępne zapasy. W tym oknie dialogowym są wyświetlane takie same informacje jak [Dostępne zapasy](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

W oknie dialogowym są zwracane informacje o zapasach z Dynamics 365 Supply Chain Management. Informacje te obejmują następujące ilości:

- Ilość dostępnych zapasów
- Zarezerowowana dostępna ilość
- Dostępna ilość na stanie
- Ilość zamówiona
- Ilość na zamówienie
- Zarezerwowana zamówiona ilość
- Łączna dostępna ilość

## <a name="atp-information"></a>Informacje ATP

W Sales nowy przyscisk **Informacje ATP** został dodany do wiersza pozycji na stronach **Oferty** , **Zamówienia** i **Faktury**. Wybranie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę, produkt, oddział zapasów, magazyn zapasów i ilośc zamówienia. To okno dialogowe ma takie same ustawienia, które są opisane w obszarze [Zobowiązanie do zamówienia](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

Okno dialogowe zwraca informacje o ATP z Supply Chain Management. Informacje te obejmują następujące ilości:

- Ilość ATP
- Ilość przychodu
- Ilość rozchodu
- Ilość dostępnych zapasów

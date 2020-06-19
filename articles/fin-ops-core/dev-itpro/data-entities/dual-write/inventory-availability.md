---
title: Dostępność zapasów w podwójnym zapisie
description: Ten temat zawiera informacje o sprawdzaniu dostępności zapasów w trybie podwójnego zapisu.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426989"
---
# <a name="inventory-availability"></a>Dostępność zapasów

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Korzystając z dostępności zapasów, można sprawdzić stan zapasów przed dodaniem produktu doformularzy **Oferty**, **Zamówienia** lub **Faktury** w aplikacjach opartych na modelu w Dynamics 365. Na przykład sprawdzenie zapasów i określenie daty realizacji jest kluczowym zadaniem w procesie [od prospektu do gotówki](dual-write-prospect-to-cash.md). Jeśli nie ma wystarczającej ilości zapasów, można oszacować datę dostawy na podstawie przewidywanych przyjęć i problemów z zapasami. Można również sprawdzić informacje o dostępności zapasów (ATP), w której można znaleźć ilość ATP w wstępnie zdefiniowanym horyzoncie czasowym.

## <a name="on-hand-inventory"></a>Dostępne zapasy 

W nagłówku formularzy **Oferty**, **Zamówienia** lub **Faktury** w Dynamics 365 Sales jest dodawany nowy przycisk **Dostępne zapasy**. Kliknięcie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę i produkt, dla którego mają zostać sprawdzone dostępne zapasy. Usługa zwraca informacje o zapasach z Dynamics 365 Supply Chain Management i pokazuje te same informacje, co [Dostępne zapasy](../../../../supply-chain/inventory/tasks/check-availability-stock.md). Informacje te obejmują następujące ilości:

- **Ilość dostępna**
- **Zarezerowowana ilość dostępna**
- **Dostępna ilość dostępna**
- **Ilość zamówiona**
- **Ilość na zamówienie**
- **Zarezerwowana zamówiona ilość**
- **Łączna dostępna ilość**

## <a name="atp-information"></a>Informacje ATP

W wierszu pozycji formularzy **Oferty**, **Zamówienia** lub **Faktury** w Dynamics 365 Sales jest dodawany nowy przycisk **Informacja ATP**. Kliknięcie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę, produkt, oddział zapasów, magazyn zapasów i ilośc zamówienia. Zwraca **Informacje ATP** z Supply Chain Management i pokazuje ustawienia opisane w [Zobowiązanie do zamówienia](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations). Informacje obejmują **Ilość ATP**, **Ilość przyjęta**, **Ilość wydana** oraz **Ilość dostępnych zapasów**.

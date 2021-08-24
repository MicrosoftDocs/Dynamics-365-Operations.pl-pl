---
title: Dostępność zapasów w podwójnym zapisie
description: Ten temat zawiera informacje o sposobie sprawdzania dostępności zapasów w trybie podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: f967f832fc716938c544aad266d2c14a9ea19dd0ca8ee11fe228ce47145f3e78
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762433"
---
# <a name="inventory-availability-in-dual-write"></a>Dostępność zapasów w podwójnym zapisie

[!include [banner](../../includes/banner.md)]

Korzystając z dostępności zapasów, można sprawdzić stan zapasów przed dodaniem produktu do stron **Oferty**, **Zamówienia** lub **Faktury** w Microsoft Dynamics 365 Sales. Na przykład sprawdzenie zapasów i określenie daty realizacji jest jednym z kluczowych zadań w procesie [od prospektu do gotówki](dual-write-prospect-to-cash.md).

Jeśli nie ma wystarczającej ilości zapasów, można oszacować datę dostawy na podstawie przewidywanych przyjęć i problemów z zapasami. Można również sprawdzić informacje o dostępności zapasów (ATP), w której można znaleźć ilość ATP w wstępnie zdefiniowanym horyzoncie czasowym.

## <a name="on-hand-inventory"></a>Dostępne zapasy

W Dynamics 365 Sales jest dodany nowy przycisk **Dostępne zapasy** do nagłówka stron **Oferty**, **Zamówienia** i **Faktury**. Wybranie tego przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę i produkt, dla którego mają zostać sprawdzone dostępne zapasy. W tym oknie dialogowym są wyświetlane takie same informacje jak [Dostępne zapasy](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

W oknie dialogowym są zwracane informacje o zapasach z Dynamics 365 Supply Chain Management. Informacje te obejmują następujące ilości:

- Ilość dostępnych zapasów
- Zarezerowowana dostępna ilość
- Dostępna ilość na stanie
- Ilość zamówiona
- Ilość na zamówienie
- Zarezerwowana zamówiona ilość
- Łączna dostępna ilość

## <a name="atp-information"></a>Informacje ATP

W Sales nowy przyscisk **Informacje ATP** został dodany do wiersza pozycji na stronach **Oferty**, **Zamówienia** i **Faktury**. Wybranie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę, produkt, oddział zapasów, magazyn zapasów i ilośc zamówienia. To okno dialogowe ma takie same ustawienia, które są opisane w obszarze [Zobowiązanie do zamówienia](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

Okno dialogowe zwraca informacje o ATP z Supply Chain Management. Informacje te obejmują następujące ilości:

- Ilość ATP
- Ilość przychodu
- Ilość rozchodu
- Ilość dostępnych zapasów

## <a name="how-it-works"></a>Jak działa

Po wybraniu przycisku **Dostępne zapasy** na stronie **Oferty**, **Zamówienia** lub **Faktury** zostanie wykonane na żywo wywołanie podwójnego zapisu dla interfejsu API **dostępnych zapasów**. Interfejs API oblicza stan dostępnych zapasów danego produktu. Wynik jest przechowywany w tabelach **InventCDSInventoryOnHandRequestEntity** i **InventCDSInventoryOnHandEntryEntity**, a następnie zapisywany w tabeli w trybie podwójnego zapisu usługi Dataverse. Aby korzystać z tej funkcji, należy uruchomić następujące mapy podwójnego zapisu. Pomiń wstępną synchronizację podczas uruchamiania map.

- Wpisy dostępnych zapasów CDS (msdyn_inventoryonhandentries)
- Żądania dostępnych zapasów CDS (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Szablony

Dla danych dotyczących dostępnych zapasów są dostępne następujące szablony.

Aplikacje Finance and Operations | Aplikacje Customer Engagement     | opis
---|---|---
[Dostępne wpisy zapasów CDS](mapping-reference.md#145) | msdyn_inventoryonhandentries |
[Żądania dostępnych zapasów CDS](mapping-reference.md#147) | msdyn_inventoryonhandrequests |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

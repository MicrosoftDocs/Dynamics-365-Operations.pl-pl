---
title: Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu
description: W tym temacie wyjaśniono sposób konfigurowania wymiany w przypadku zwrotu w rozwiązaniu Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 45b628376a483d3d639e5c018dd93570ed8ce7af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "302735"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu

[!include [banner](includes/banner.md)]

W poprzednich wersjach rozwiązania Microsoft Dynamics 365 for Retail zwroty dotyczące zamówień klientów były przetwarzane przy użyciu dokumentu zamówienia zwrotu w module Retail headquarters. Jednak dokumenty zamówienia zwrotu mogą być używane tylko do przetwarzania produktów zwracanych. Zwracane produkty są oznaczone ilością ujemną w wierszach zamówień zwrotu. Z drugiej strony sprzedaż jest wskazywana przez ilość dodatnią. Dokument zamówienia zwrotu nie obsługuje jednak ilości dodatnich. Ze względu na to ograniczenie w poprzednich wersjach aplikacji Retail nie była obsługiwane sytuacje, w których wymiana produktu była dokonywana przy użyciu dokumentu zamówienia zwrotu.

Dodano jednak funkcję w celu obsługi sytuacji, w których wymiana odbywa się z wykorzystaniem zamówień zwrotu. Aby przetwarzać tego typu transakcje w aplikacji Retail jest obecnie używany dokument zamówienia sprzedaży zamiast dokumentu zamówienia zwrotu.

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a>Konfigurowanie aplikacji Retail pod kątem obsługi wymiany w przypadku zamówień zwrotu

Aby skonfigurować system do obsługi wymiany w przypadku zamówień zwrotu, należy wykonać poniższe czynności.

1. Kliknij kolejno opcje **Handel detaliczny \> Ustawienia centrali \> Parametry \> Parametry sieci sprzedaży**. Na skróconej karcie **Zamówienia odbiorcy** ustaw wartość **Tak** opcji **Przetwarzanie zamówień zwrotu jako zamówień sprzedaży**.
2. Uruchom zadanie **Harmonogram dystrybucji konfiguracji globalnej** (**1110**).

## <a name="make-an-exchange"></a>Dokonywanie wymiany

Po skonfigurowaniu systemu w sposób opisany w poprzedniej sekcji użytkownik punktu sprzedaży (POS), aby przetworzyć zwrot, będzie w dalszym ciągu musiał wybrać zamówienie sprzedaży lub fakturę sprzedaży, podobnie jak w poprzednich wersjach aplikacji Retail. Jednak po dodaniu zwracanych towarów do koszyka, użytkownik będzie mógł dodawać nowe wiersze sprzedaży do koszyka.

Dla tych nowych wierszy sprzedaży użytkownik musi zdefiniować wszystkie atrybuty, które są wymagane w celu przetworzenia wiersza zamówienia odbiorcy. Do tych atrybutów należy metoda dostawy i lokalizacja realizacji. Płatność należna za transakcję będzie kwotą netto wierszy zamówienia zwrotu i wierszy zamówienia sprzedaży. Po przekazaniu płatności za transakcję zamówienie zwrotu zostanie zaksięgowane w module Centrala sieci sprzedaży jako dokument zamówienia sprzedaży, a w systemie zostanie natychmiast wystawiona faktura dotycząca wierszy zwrotu.

Aby zapewnić lepszą widoczność różnych kwot w koszyku, zostały w nim dodane trzy nowe pola kwoty. W celu udostępnienia tych nowych pól w interfejsie użytkownika (UI) punktu sprzedaży można użyć projektanta układu ekranu.

- **Zastosowana kaucja** — kwota kaucji, która jest stosowana do transakcji, gdy użytkownik pobiera zamówienie odbiorcy. Jeśli nie określono żadnych zastąpień kaucji oraz została skonfigurowana kaucja 10-procentowa, to kwota w tym polu stanowi 90 procent sumy zamówienia odbiorcy.
- **Kwota zrealizowana** — łączna kwota dla wierszy, w których ustawiono metodę dostawy **Wyniesienie**, gdy zamówienie klienta zostało utworzone lub zmodyfikowane albo podczas wymiany zamówienia odbiorcy. Kwota w tym polu obejmuje podatki i opłaty.
- **Kwota zwrotu** — suma dla wierszy, które zawierają ilości ujemne podczas wymiany zamówienia odbiorcy. Kwota w tym polu obejmuje podatki i opłaty.

---
title: Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu
description: W tym artykule wyjaśniono sposób konfigurowania wymiany w przypadku zwrotu w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 07/28/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f33c674e4110b4e45ac58e499a65da2509b00046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845800"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu

[!include [banner](includes/banner.md)]

W poprzednich wersjach rozwiązania Dynamics 365 Commerce zwroty dotyczące zamówień klientów były przetwarzane przy użyciu dokumentu zamówienia zwrotu w centrali. Jednak dokumenty zamówienia zwrotu mogą być używane tylko do przetwarzania produktów zwracanych. Zwracane produkty są oznaczone ilością ujemną w wierszach zamówień zwrotu. Z drugiej strony sprzedaż jest wskazywana przez ilość dodatnią. Dokument zamówienia zwrotu nie obsługuje jednak ilości dodatnich. Ze względu na to ograniczenie w poprzednich wersjach aplikacji nie były obsługiwane sytuacje, w których wymiana produktu była dokonywana przy użyciu dokumentu zamówienia zwrotu.

Dodano jednak funkcję w celu obsługi sytuacji, w których wymiana odbywa się z wykorzystaniem zamówień zwrotu. Aby przetwarzać tego typu transakcje, w aplikacji Commerce jest obecnie używany dokument zamówienia sprzedaży zamiast dokumentu zamówienia zwrotu.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>Konfigurowanie aplikacji Commerce pod kątem obsługi wymian w przypadku zamówień zwrotu

> [!NOTE]
> W rozwiązaniu Commerce w wersji 10.0.20 i nowszej dostępna jest nowa funkcja o nazwie „Doświadczenie w przetwarzaniu zwrotów zunifikowanych w punkcie sprzedaży”. Jeśli ta funkcja zostanie włączona, poniższe kroki konfiguracji nie są wymagane. Opcja **Przetwarzaj zwroty jako zamówienia sprzedaży** staje się ustawieniem skonfigurowanym na stałe i nie będzie można go zmienić.

Wykonaj następujące kroki, aby skonfigurować system do obsługi wymian w zamówieniach zwrotu (jeśli opcja **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w punkcie sprzedaży** nie jest włączona).

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry rozwiązania Commerce**. Na skróconej karcie **Zamówienia odbiorcy** ustaw wartość **Tak** opcji **Przetwarzanie zamówień zwrotu jako zamówień sprzedaży**.
2. Uruchom zadanie **Harmonogram dystrybucji konfiguracji globalnej** (**1110**).

## <a name="make-an-exchange"></a>Dokonywanie wymiany

Po skonfigurowaniu systemu w sposób opisany w poprzedniej sekcji użytkownik punktu sprzedaży (POS), aby przetworzyć zwrot, będzie w dalszym ciągu musiał wybrać zamówienie sprzedaży lub fakturę sprzedaży, podobnie jak w poprzednich wersjach aplikacji. Jednak po dodaniu zwracanych pozycji do koszyka, użytkownik będzie mógł dodawać nowe wiersze sprzedaży do koszyka.

Dla tych nowych wierszy sprzedaży użytkownik musi zdefiniować wszystkie atrybuty, które są wymagane w celu przetworzenia wiersza zamówienia odbiorcy. Do tych atrybutów należy metoda dostawy i lokalizacja realizacji. Płatność należna za transakcję będzie kwotą netto wierszy zamówienia zwrotu i wierszy zamówienia sprzedaży. Po przekazaniu płatności za transakcję zamówienie zwrotu zostanie zaksięgowane w centrali jako dokument zamówienia sprzedaży, a w systemie zostanie natychmiast wystawiona faktura dotycząca wierszy zwrotu.

Aby zapewnić lepszą widoczność różnych kwot w koszyku, zostały w nim dodane trzy nowe pola kwoty. W celu udostępnienia tych nowych pól w interfejsie użytkownika (UI) punktu sprzedaży można użyć projektanta układu ekranu.

- **Zastosowana kaucja** — kwota kaucji, która jest stosowana do transakcji, gdy użytkownik pobiera zamówienie odbiorcy. Jeśli nie określono żadnych zastąpień kaucji oraz została skonfigurowana kaucja 10-procentowa, to kwota w tym polu stanowi 90 procent sumy zamówienia odbiorcy.
- **Kwota zrealizowana** — łączna kwota dla wierszy, w których ustawiono metodę dostawy **Wyniesienie**, gdy zamówienie klienta zostało utworzone lub zmodyfikowane albo podczas wymiany zamówienia odbiorcy. Kwota w tym polu obejmuje podatki i opłaty.
- **Kwota zwrotu** — suma dla wierszy, które zawierają ilości ujemne podczas wymiany zamówienia odbiorcy. Kwota w tym polu obejmuje podatki i opłaty.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Opłaty podlegające zwrotowi są przeliczane nieprawidłowo na podstawie zwracanej ilości
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc kasjerom zobaczyć w programie punkt sprzedaży (POS) niepoprawne opłaty związane ze zwrotem ilości zwracanych towarów.
author: gvrmohanreddy
ms.date: 03/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 7a84207f587a826b9acdfd818c64220c5327bde1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890250"
---
# <a name="refundable-charges-are-miscalculated-based-on-the-quantity-returned"></a>Opłaty podlegające zwrotowi są przeliczane nieprawidłowo na podstawie zwracanej ilości

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc kasjerom zobaczyć w programie punkt sprzedaży (POS) niepoprawne opłaty związane ze zwrotem ilości zwracanych towarów.

## <a name="description"></a>Opis

Odbiorca zwraca częściową ilość towarów, które zakupiono dla zamówienia sprzedaży, które ma opłaty zwrotne na poziomie wiersza. Jednak zamiast pokazywać częściowy zwrot pieniędzy, POS pokazuje wszystkie opłaty jako podlegające zwrotowi.

Na przykład odbiorca nabywa po pięć sztuk towaru po określonej $5 towaru, o łącznej wartości $25. Klient zwraca trzy z pięciu pozycji. Jednak kasjerowi wyświetla się opłata zwrotna w wysokości 25 USD w punkcie sprzedaży, zamiast oczekiwanej opłaty zwrotnej w wysokości 15 USD za trzy zwrócone produkty.

## <a name="resolution"></a>Rozwiązanie

### <a name="turn-on-the-enable-refunding-charges-based-on-the-refunded-quantity-feature"></a>Włącz opcję Włącz zwrot kosztów na podstawie zwróconej ilości

Począwszy od Microsoft Dynamics 365 Commerce w wersji 10.0.26, funkcja **Włącz zwrot kosztów na podstawie zwróconej ilości** umożliwia obliczanie opłat podlegających zwrotowi na poziomie wiersza na podstawie ilości zwracanych towarów.

Aby włączyć funkcję **Włącz zwrot opłat na podstawie funkcji zwracanej** ilości w programie Commerce Headquarters, wykonaj następujące czynności.

1. Otwórz obszar roboczy **Zarządzanie funkcjami** (**Administrator systemu \> obszary robocze\> Zarządzanie funkcjami**).
1. Z listy dostępnych funkcji wyszukaj i wybierz funkcję **Włącz zwrot opłat na podstawie funkcji zwracanej ilości**.
1. W okienku po prawej stronie włącz pozycję **Włącz teraz**.

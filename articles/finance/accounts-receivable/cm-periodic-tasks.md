---
title: Zadania okresowe zarządzania kredytami
description: W tym temacie opisano zadania okresowe, które są niezbędne w procesie zarządzania limitami kredytowymi dla odbiorców.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: b41b87cd3e2e80b87318c5c771d45a4d0e5d4b85
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971710"
---
# <a name="periodic-credit-management-tasks"></a>Okresowe zadania zarządzania kredytami

[!include [banner](../includes/banner.md)]

W tym temacie opisano zadania okresowe, które są niezbędne w procesie zarządzania limitami kredytowymi dla odbiorców.

## <a name="update-risk-scores"></a>Aktualizuj oceny ryzyka

W miarę zmieniających się przedsiębiorstw i zmian okoliczności ryzyko kredytowe danego odbiorcy może również ulec zmianie. Aby ułatwić obsługę odpowiednich limitów kredytowych dla odbiorców, należy okresowo sprawdzać kryteria dla każdego wyniku ryzyka i aktualizować wyniki dla każdego odbiorcy. Poniższe wyniki można zaktualizować, korzystając ze strony **Aktualizowanie wyników ryzyka** (**Kredyty i Windykacja \> Zadania okresowe \> Zarządzanie kredytem \> Aktualizowanie wyników ryzyka**). Przetwarzane są również wszystkie zdefiniowane przez użytkownika obliczenia.

- **Średnia liczba dni płatności** — ten punkt jest średnią liczbą dni, przez jaką odbiorca może zapłacić faktury.
- **Odbiorca od** — wartość tego pola to liczba lat, przez które odbiorca jest odbiorcą danej organizacji.
- **Działalność od** — jest to liczba lat, przez które odbiorca jest w trakcie działalności. Używana jest wartość pola **Rozpoczęcie działalności** na stronie **Odbiorcy**.
- **Wskaźnik rotacji należności w dniach** — ten wynik jest oparty na saldzie rozrachunków z odbiorcami, przychodach sprzedaży i liczbie dni w poprzednim okresie 12-miesięcznym.
- **Saldo średnie** — ten wynik jest oparty na saldzie rozrachunków z odbiorcami dla poprzedniego okresu 12-miesięcznego.
- **Grupa zarządzania kredytami**, **Stan konta** i **Kraj** — te wyniki wykorzystują informacje od odbiorcy.

## <a name="update-customer-balance-statistics"></a>Aktualizuj statystyki salda odbiorcy

Istnieje możliwość uruchomienia procesu **Aktualizuj statystyki salda odbiorcy** w celu zaktualizowania obliczania statystyk salda wyświetlanego na stronie **Informacje o statystykach salda**. Te informacje służą do obliczania wyników ryzyka i wartości wyświetlanych w polach informacji statystycznych dotyczących odbiorcy na stronie **Odbiorca**.

Po uruchomieniu tego procesu system aktualizuje statystykę salda odbiorcy dla jednego odbiorcy. Aby skonfigurować zadanie przetwarzania wsadowego w celu uruchomienia procesu dla wielu odbiorców, można skorzystać ze strony **Oblicz statystykę salda** (**Zarządzanie kredytem \> Zadania okresowe \> Oblicz statystykę salda**).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
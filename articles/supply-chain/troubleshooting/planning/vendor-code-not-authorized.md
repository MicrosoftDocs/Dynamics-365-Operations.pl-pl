---
title: Kod dostawcy nie jest autoryzowany dla określonego produktu i daty
description: Podczas próby utworzenia planowanego zamówienia lub dodania wiersza do zamówienia zakupu pojawia się komunikat o błędzie, który stwierdza, że kod sprzedawcy nie jest autoryzowany dla produktu i daty.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294158"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a>Kod dostawcy nie jest autoryzowany dla określonego produktu i daty

Kod błędu: SYP4881415

## <a name="symptoms"></a>Objawy

Podczas próby wzmocnienia planowanego zamówienia lub dodania wiersza do zamówienia zakupu otrzymujemy następujący komunikat o błędzie:

> Kod dostawcy %1 nie jest uwierzytelniony dla %2 w dniu %3.

## <a name="cause"></a>Powód

Błąd występuje, ponieważ pole **Metoda sprawdzania zatwierdzonego sprzedawcy** jest ustawione na *Tylko ostrzeżenie* lub *Niedozwolone* dla określonego produktu, a sprzedawca nie jest obecnie uprawniony do dostarczania tego produktu.

## <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, należy albo wyłączyć sprawdzanie sprzedawcy dla danego produktu, albo zatwierdzić sprzedawcę.

Aby wyłączyć sprawdzanie sprzedawcy dla produktu, wykonaj poniższe kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Otwórz odpowiedni produkt.
1. Na skróconej karcie **Zakup** ustaw w polu **Metoda sprawdzania zatwierdzonych dostawców** wartość inną niż *Tylko ostrzeżenie* lub *Niedozwolone*.

Aby zatwierdzić sprzedawcę produktu, wykonaj poniższe kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Otwórz odpowiednią pozycję.
1. W Okienku akcji na karcie **Zakup** w grupie **Zatwierdzony dostawca** kliknij **Konfiguracja**.
1. Na stronie listy **Zatwierdzony sprzedawca** dodaj wiersz do siatki, aby ustawić następujące wartości:

    - **Dostawca** — umożliwia wybranie dostawcy, który ma być zatwierdzany dla bieżącego produktu.
    - **Data wejścia w życie** — umożliwia wybór pierwszej daty zatwierdzenia dostawcy.
    - **Data ważności** — umożliwia wybór ostatniej daty zatwierdzenia dostawcy.

Aby uzyskać więcej informacji, zobacz [Zatwierdzanie dostawców dla konkretnych produktów](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).

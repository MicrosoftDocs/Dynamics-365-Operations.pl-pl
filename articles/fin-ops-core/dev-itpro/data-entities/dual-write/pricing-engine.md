---
title: Synchronizacja na żądanie z aparatem kalkulacji cen rozwiązania Dynamics 365 Supply Chain Management
description: W tym temacie opisano sposób używania aparatu kalkulacji cen w Microsoft Dynamics 365 Supply Chain Management z Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 5ffc0358ff58b2a05aa84b4467a27d88b5e1ec42
ms.sourcegitcommit: 984604fd651d74aa49a2d7513f096faaf49f9f27
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2020
ms.locfileid: "3270343"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a>Synchronizacja na żądanie z aparatem kalkulacji cen rozwiązania Dynamics 365 Supply Chain Management

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Supply Chain Management udostępnia aparat kalkulacji cen, który obsługuje umowy handlowe, cenniki, programy lojalnościowe dla klientów, promocje i rabaty. Aparat cenowy używa złożonych reguł w celu określenia najlepszej ceny dla danej oferty lub zamówienia. W przypadku korzystania z funkcji podwójnego odpisu na stronach oferta i zamówienie w Dynamics 365 Sales można stosować zarówno cenę statyczną, jak i aparat cenowy z Dynamics 365 Supply Chain Management.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Użycie aparatu cenowego z Supply Chain Management w Sales

1. W Sales przejdź do **Sales \> Zamówienia**.
2. Wybierz **Nowy**, aby utworzyć nowe zamówienie lub wybierz istniejące zamówienie z listy **Moje zamówienia**.
3. Dodaj nowy wiersz zamówienia.
4. W przypadku tworzenia nowego zamówienia w okienku akcji wybierz opcję **Zamówienie cenowe**. Jeśli aktualizujesz istniejące zamówienie, wybierz **Ponownie oblicz** w okienku akcji.

    Następujące pola są automatycznie wypełniane:

    + Szczegółowa ilość
    + Procent rabatu
    + Dyskonto
    + Kwota przed frachtem
    + Kwota frachtu
    + Podatek całkowity
    + Łączna kwota
    
5. Aby upewnić się, że system traktuje umowy handlowe i sprzedaży w celu obliczenia ceny:
    1. Przejdź do środowiska Supply Chain Management.
    2. Przejdź do **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
    3. Wybierz kartę **Ceny** na bocznym pasku nawigacyjnym.
    4. Na karcie skróconej **Ocena umowy handlowej** usuń zaznaczenie opcji **Zapis ręczny**.

## <a name="how-it-works"></a>Jak działa

Po wybraniu **Zamówienia cenowego** w Sales funkcja **Sumy** na karcie **Zamówienie sprzedaży \> Widok** w Supply Chain Management jest wywoływana dla skojarzonego zamówienia sprzedaży. Wartości w sumie zamówienia w Sales są używane do wypełniania odpowiednich pól w Supply Chain Management.

Jeśli suma zamówienia sprzedaży jest obliczana w Supply Chain Management, obliczenie ocenia istniejące umowy handlowe i umowy sprzedaży dla odbiorcy oraz produkty wymienione w zamówieniu sprzedaży. Informacje te są używane do obliczania sum. W przypadku wybrania **Zamówienia cenowego** sprzedaż automatycznie odzwierciedla wszystkie ustawienia wykonane w Supply Chain Management.

## <a name="limitations"></a>Ograniczenia

Po wypełnieniu pól w Sales obowiązują następujące ograniczenia:

+ Konfigurowanie opłat i alokacji opłat w Supply Chain Management nie jest replikowane w Sales.
+ W przypadku cen nie są uwzględniane specjalne ceny detaliczne określone w polu **Kanał detaliczny** na stronie wiersz zamówienia sprzedaży w Supply Chain Management.
+ Nie są brane pod uwagę rabaty zdefiniowane w sekcji **Zarządzania przydziałem handlowym** w Supply Chain Management.

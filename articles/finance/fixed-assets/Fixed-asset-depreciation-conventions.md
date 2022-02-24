---
title: Konwencje amortyzacji środków trwałych
description: Ten temat opisuje konwencje amortyzacji środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd0153b5d735e1d565b67db6c66c854ff738509c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969210"
---
# <a name="fixed-asset-depreciation-conventions"></a>Konwencje amortyzacji środków trwałych

[!include [banner](../includes/banner.md)]

Ten temat opisuje konwencje amortyzacji środków trwałych. Konwencje amortyzacji są używane do określenia, kiedy i jak amortyzacja jest obliczana dla roku nabycia środka trwałego i roku likwidacji środka trwałego.

Konwencje amortyzacji można przypisać do konfiguracji księgi grupy środków trwałych. Aby wyświetlić lub przypisać konwencję amortyzacji, w obszarze konfiguracji środków trwałych, należy wybrać grupy **środka trwałego**. Wybierz przycisk **Księgi**. W takim przypadku przypisane konwencje amortyzacji są używane jako wartości domyślne podczas tworzenia księgi środków trwałych. Konwencje amortyzacji można również ustawiać dla poszczególnych ksiąg środków trwałych. Aby to zrobić, wybierz **Księgi** w obszarze konfiguracji środków trwałych, a następnie wybierz przycisk **grup środków trwałych**.

| Konwencja amortyzacji   | Opis |
|---------------------------|-------------|
| Brak                      | Środki trwałe zaczynają być amortyzowane w dniu <strong>Rozpoczęcie eksploatacji</strong>. |
| Pół roku                 | Odlicza się półroczną amortyzację zarówno za pierwszy, jak i za ostatni rok amortyzacji nieruchomości. Odejmuje się cały rok amortyzacji za każdy pozostały rok w okresie amortyzacji. |
| Pełny miesiąc                | Środki trwałe, które mają datę <strong>Rozpoczęcie eksploatacji</strong> przypadającą w dowolnym dniu w miesiącu, zaczynają się amortyzować w pierwszym dniu tego miesiąca. W przypadku celów amortyzacji środki trwałe są uważane za wycofane ostatniego dnia poprzedniego miesiąca. Nie uwzględniono konkretnego dnia miesiąca, w którym zostały wycofane. |
| Kwartał środkowy               | W celu obliczenia odpisu amortyzacyjnego za rok, w którym środek wprowadzono do eksploatacji, należy pomnożyć amortyzację za cały rok przez procent kwartału, w którym składnik majątku był w eksploatacji, jak pokazano w tabeli poniżej.<table><thead><tr><th>Kwartał</th><th>Wartość procentowa</th></tr></thead><tbody><tr><td>Pierwszy</td><td>87.5</td></tr><tr><td>Drugi</td><td>62.5</td></tr><tr><td>Trzeci</td><td>37.5</td></tr><tr><td>Czwarty</td><td>12.5</td></tr></tbody></table>Pół kwartału amortyzacji nalicza się w kwartale, w którym dokonano zbycia środka trwałego (lub w kwartale, w którym został on całkowicie zamortyzowany). |
| Miesiąc środkowy (1. dzień miesiąca)  | Środki trwałe, które mają datę <strong>Rozpoczęcie eksploatacji</strong> w pierwszej połowie miesiąca (dni od 1 do 15), zaczynają się amortyzować w pierwszym dniu miesiąca zawierającego datę <strong>Rozpoczęcie eksploatacji</strong>. Środki trwałe, które mają datę <strong>Rozpoczęcie eksploatacji</strong> w drugiej połowie miesiąca (dni od 16 do końca miesiąca), zaczynają się amortyzować w pierwszym dniu miesiąca po dacie <strong>Rozpoczęcie eksploatacji</strong>. Środki trwałe, które zostaną wycofane w pierwszej połowie miesiąca (dni od 1 do 15), są traktowane jako wycofane na potrzeby amortyzacji w ostatnim dniu poprzedniego miesiąca. Środki trwałe, które zostaną wycofane w drugiej połowie miesiąca (dni od 16 do końca miesiąca), są traktowane jako wycofane w ostatnim dniu miesiąca, w którym nastąpiło wycofanie na potrzeby amortyzacji. |
| Miesiąc środkowy (15. dzień miesiąca) | W celu obliczenia odpisu amortyzacyjnego za rok, w którym środek wprowadzono do eksploatacji, należy pomnożyć amortyzację całoroczną przez odpowiedni ułamek. Licznik (górna liczba) ułamka jest liczbą pełnych miesięcy w roku, gdy składnik majątku znajdował się w eksploatacji, powiększoną o 1/2 (0,5). Dzielnik (dolna liczba) wynosi 12. Jeśli zlikwidujesz składnik majątku przed końcem okresu amortyzacji, użyj tej samej metody do obliczenia odpisu amortyzacyjnego za rok likwidacji. |
| Pół roku (początek roku) | Środki trwałe, które mają datę <strong>Rozpoczęcie eksploatacji</strong> w pierwszej połowie roku, zaczynają się amortyzować w pierwszym dniu roku (cały rok). Środki trwałe, które mają datę <strong>Rozpoczęcie eksploatacji</strong> w drugiej połowie roku, zaczynają się amortyzować w połowie roku. |
| Pół roku (następny rok)     | Środki trwałe, które mają datę <strong>Rozpoczęcie eksploatacji</strong> w pierwszej połowie roku, zaczynają się amortyzować w pierwszym dniu roku (cały rok). Środki trwałe, które mają datę <strong>Rozpoczęcie eksploatacji</strong> w drugiej połowie roku, zaczynają się amortyzować w pierwszym dniu następnego roku. Środki trwałe, które zostaną wycofane w pierwszej połowie roku, są traktowane jako wycofane w ostatnim dniu poprzedniego roku na potrzeby amortyzacji. Każda amortyzacja zaksięgowana w bieżącym roku musi zostać wycofana (skorygowana). Środki trwałe, które zostaną wycofane w drugiej połowie roku, są traktowane jako wycofane na potrzeby amortyzacji w ostatnim dniu roku, w którym nastąpiło wycofanie. |

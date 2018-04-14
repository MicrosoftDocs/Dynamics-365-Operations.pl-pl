---
title: Planowanie operacji
description: "Ten temat zawiera informacje o planowaniu operacji. Funkcji planowania operacji można używać, aby przedstawić ogólne oszacowanie procesu produkcji w wybranym okresie."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 81dec9d988b22959df5421b7b84ef532a28e1228
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="operations-scheduling"></a>Planowanie operacji

[!INCLUDE [banner](../includes/banner.md)]

Ten temat zawiera informacje o planowaniu operacji. Funkcji planowania operacji można używać, aby przedstawić ogólne oszacowanie procesu produkcji w wybranym okresie.

Produkcję można planować na poziomie operacji i zadań. W przeciwieństwie do planowania zadań planowanie operacji nie powoduje rozłożenia operacji marszruty produkcji w zadania. Jeśli chcesz uwzględnić więcej szczegółów w planowaniu, takich jak informacje o aktualnych zdolnościach produkcyjnych, można uruchomić planowanie zadań po wykonaniu planowania operacji. Można również wykonać samo planowanie zadań. Planowanie zadań zazwyczaj służy do planowania poszczególnych zadań na produkcji w perspektywie czasowej bieżącej lub krótkoterminowej.

## <a name="components-of-operations-scheduling"></a>Składniki planowania operacji
Główne składniki planowania operacji to kierunek planowania, zdolności produkcyjne zasobów i optymalizacja materiałów. Korzystając z funkcji planowania operacji, można osiągnąć następujące cele:

-   Określanie metody planowania poprzez planowanie w przód lub wstecz od określonej daty.
-   Optymalizacja wykorzystania zasobów poprzez planowanie produkcji na podstawie zdolności produkcyjnych zasobów. Ta metoda ułatwia również ustalanie, kiedy należy użyć alternatywnych zasobów.
-   Optymalizacja wykorzystania materiałów poprzez planowanie produkcji na podstawie dostępności wymaganych materiałów.
-   Planowanie i synchronizowanie produkcji z odwołaniami. Daty produkcji z odwołaniami są korygowane po zmianie harmonogramu zlecenia produkcyjnego.

Planowanie operacji można rozpocząć dopiero po oszacowaniu kosztu zlecenia produkcyjnego. Jeśli nie dokonano szacowania, zostanie ono wykonane automatycznie przed rozpoczęciem planowania operacji. Harmonogram operacji określa następujące informacje:

-   Produkt planowany do produkcji
-   Konfiguracja produktu
-   Ilości związane z produkcją
-   Daty planowanego rozpoczęcia i zakończenia produkcji
-   Rezerwacje zdolności produkcyjnych dla zasobów wykonujących działania produkcji

Czasy przezbrajania, przetwarzania i procesu są ustawiane dla operacji w produkcji. Po wykonaniu planowania operacji stan zlecenia produkcyjnego zmienia się na **Zaplanowane**, a wszystkie operacje są zaplanowane w kolejności określonej w marszrucie produkcji. Jednak pod uwagę jest brany tylko czas trwania operacji. Godziny rozpoczęcia i zakończenia nie są planowane.

## <a name="scheduling-direction-and-date"></a>Kierunek planowania i data
Kierunek ma zasadnicze znaczenie w procesie planowania. Produkcję można planować w przód lub wstecz od dowolnej daty, zależnie od wymagań w zakresie synchronizacji i planowania.

-   **W przód od daty planowania** — Można zaplanować rozpoczęcie produkcji jak najszybciej. Produkcja może się rozpocząć dziś, jutro lub dowolnego dnia w przyszłości. Produkcja kończy się w najwcześniejszym możliwym terminie.
-   **Wstecz od daty planowania** — Można zaplanować rozpoczęcie produkcji jak najpóźniej. Planowanie wstecz bazuje na dacie, do kiedy należy skończyć produkcję. Harmonogram jest liczony wstecz od tej daty do możliwie najpóźniejszej daty, kiedy można rozpocząć produkcję i ją ukończyć na czas.

## <a name="resource-scheduling"></a>Planowanie zasobów
Podczas planowania operacji każda operacja w marszrucie produkcji jest planowana dla zasobu określonego dla tej operacji. Dodatkowo czas trwania każdej operacji jest określony w marszrucie produkcji. Jeśli dla operacji określono grupę zasobów, planowanie będzie rezerwować zdolności produkcyjne dla całej grupy. Jednak w przeciwieństwie do planowania zadań planowanie operacji nie powoduje wybrania konkretnych zasobów w grupie. Jeśli są ograniczone zdolności produkcyjne, harmonogram zależy od dostępności zasobów wymaganych do ukończenia produkcji. Podczas planowania operacji jest przestrzegana kolejność operacji ustawiona w marszrucie produkcji. Planowanie powoduje rezerwowanie zdolności produkcyjnych w grupie zasobów na podstawie czasów trwania operacji zdefiniowanych w marszrucie produkcji. Suma dostępnych zdolności produkcyjnych zaangażowanych zasobów decyduje o zdolnościach produkcyjnych grupy zasobów. Rezerwacje zdolności produkcyjnych, które już istnieją dla zasobów, są uznawane za niedostępne zdolności produkcyjne. Jeśli jest za mało zdolności produkcyjnych do produkcji, zlecenia produkcyjne mogą być opóźnione lub nawet wstrzymane. Można również określić wydajność, jakiej się oczekuje od zasobów zaangażowanych w produkcję. Wydajność podaje się w procentach zasobu. Procent wydajności koryguje produktywności zasobu. Ta korekta wpływa na czas zarezerwowany dla zasobu. Czasy realizacji dla operacji, które korzystają z zasobu, również są odpowiednio korygowane.

## <a name="operations-scheduling-and-master-planning"></a>Planowanie operacji a planowanie główne
Harmonogram operacji decyduje również o planowaniu głównym i obliczaniu zapotrzebowań materiałowych. W planowaniu operacji są brane pod uwagę następujące informacje:

-   **Produkcje zaległe** — produkty, które są zaplanowane, zwolnione lub rozpoczęte
-   **Dostępność materiałów** — zapasy, produkcje podrzędne i dostawcy
-   **Zdolności produkcyjne** — zasoby wymagane do produkcji

## <a name="cancellations"></a>Anulowania
Podczas planowania operacji można anulować określone części marszruty. Tymi częściami są czas oczekiwania, czas przezbrajania, czas przetwarzania, czas nakładania i czasy transportu.

## <a name="finite-materials"></a>Ograniczone materiały
Jeśli pracujesz z ograniczonymi materiałami, planowanie zależy również od dostępności materiałów wymaganych do produkcji. Jeśli jest za mało dostępnych składników produkcji, może dojść do opóźnienia produkcji. Planowanie można oprzeć na zużyciu materiałów poprzez określenie materiałów, które muszą być dostępne do produkcji. Gdy optymalizujesz względem zarówno zdolności produkcyjnych zasobów, jak i dostępności materiałów, produkcja jest obliczana zgodnie z tymi ograniczeniami. Rozpoczęcie zlecenia produkcyjnego można zaplanować dopiero na moment, gdy zdolności produkcyjne i materiały są dostępne w tym samym czasie i w wymaganych ilościach.

<a name="see-also"></a>Informacje dodatkowe
--------

[Opcje planowania operacji](operation-scheduling-options.md)





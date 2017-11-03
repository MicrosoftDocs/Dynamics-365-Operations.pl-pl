---
title: "Planowanie zadań"
description: "Ten artykuł zawiera informacje o planowaniu zadań, co jest bardziej szczegółową formą planowania niż planowanie operacji. Można używać planowania zadań do tworzenia harmonogramu pojedynczych zadań lub zamówień w sklepie i kontrolowania środowiska produkcyjnego."
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
ms.custom: 19431
ms.assetid: aef37341-91d8-4263-80eb-35d9584be156
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 53923db7cbd3b74c1d1db72f51076640815c7df4
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="job-scheduling"></a>Planowanie zadań

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o planowaniu zadań, co jest bardziej szczegółową formą planowania niż planowanie operacji. Można używać planowania zadań do tworzenia harmonogramu pojedynczych zadań lub zamówień w sklepie i kontrolowania środowiska produkcyjnego.

Można używać planowania zadań do tworzenia harmonogramu pojedynczych zadań lub zamówień w sklepie i kontrolowania środowiska produkcyjnego. Planowanie zadań umożliwia rozbicie każdej operacji na pojedyncze zadania. Zadania te są następnie przypisywane do zasobów operacyjnych, które będą je wykonywać. Planowanie zadań umożliwia również harmonizowanie wszystkich zadań, które odwołują się wybranego zadania. Można określić datę i godzinę rozpoczęcia lub zakończenia zadania, a następnie uruchomić planowanie. Określony czas może być godziną rozpoczęcia lub zakończenia, zależnie od wyboru kierunku planowania. Ta funkcja jest przydatna, jeśli na przykład zadanie może działać tylko na jednym komputerze jednocześnie lub gdy chcesz zoptymalizować zadanie uruchamiane dla każdego zasobu.

## <a name="tasks-in-the-job-scheduling-process"></a>Zadania w procesie planowania zadań
Proces planowania zadań obejmuje następujące zadania:

-   Dzielenie operacji na zadania.
-   Planowanie zadań na podstawie dat i godzin dla zasobów określonych dla operacji pokrewnej.
-   Obliczanie czasów rozpoczęcia i zakończenia dla każdego zadania. Aby upewnić się, że nie istnieją żadne nakładające się czasy, możesz użyć skończonej pojemności.
-   Określanie, które zasoby w grupie zasobów mają być używane do realizacji zadania. To zadanie wymaga wybrania dla operacji grupy zasobów. Proces planowania zadań wybiera zasoby lub grupy zasobów według najkrótszego realizacji i bierze pod uwagę wszystkie wcześniejsze rezerwacje zasobów.
-   Rozkładanie operacji na zadania w trakcie planowania zadań. Zadania są planowane według daty i godziny, w kolejności określanej przez marszrutę produkcji. Konfiguracja operacji określa zadania, które są rozkładane w procesie planowania. Grupa marszruty przypisana do operacji określa, czy zadania są generowane. Zadanie jest generowane tylko wtedy, gdy określono dla niego czas trwania. Na przykład zadanie czasu transportu jest generowane wtedy, gdy dla wybranej operacji określono czas transportu.

## <a name="scheduling-direction"></a>Kierunek planowania
Zadania można planować do przodu i wstecz.

-   **W przód** – pozwala planować zadania w przód, by jak najszybciej uruchomić produkcję. Ta metoda jest również nazywana „metodą popychania”, ponieważ produkcja jest „popychana w przód” przez cykl produkcyjny. Produkcja rozpoczyna się i kończy w najwcześniejszym możliwym terminie.
-   **Wstecz** – pozwala planować zadania wstecz, by uruchomić produkcję jak najpóźniej. Ta metoda jest również nazywana „metodą ciągnięcia”, bo opiera się na dacie planowanego ukończenia produkcji. Planowanie wstecz odlicza do tyłu do najpóźniejszej możliwej rozpoczęcia produkcji gwarantującej dotrzymanie uzgodnionego terminu.

## <a name="finite-capacity"></a>Ograniczone zdolności produkcyjne
Można planować zadania przy użyciu ograniczonych zdolności produkcyjnych. Jeśli używasz ograniczonych zdolności produkcyjnych, zaplanowane zdolności produkcyjne nie mogą być większe niż zdolności dostępne dla zasobu. Dostępny czas jest definiowany jako przedział czasu, w którym zasób jest dostępny i nie ma żadnych innych rezerwacji zdolności produkcyjnych. Planowanie oparte na ograniczonych zdolnościach produkcyjnych gwarantuje, że czasy rozpoczęcia i zakończenia operacji nie zachodzą na siebie. Brane są pod uwagę zdolności produkcyjne już zarezerwowane i ewentualne nakładanie się czasu rozpoczęcia i zakończenia. Ograniczone zdolności produkcyjne określają, jakie zdolności produkcyjne muszą być dostępne dla zasobu, tak aby zasób ten mógł zostać wykorzystany w sposób optymalny. Następnie następuje korekta tych wyliczeń według najkrótszego możliwego czasu realizacji między operacjami.

## <a name="finite-materials"></a>Ograniczone materiały
Planowanie zadań z uwzględnieniem ograniczonych materiałów gwarantuje, że wymagane materiały są dostępne w momencie rozpoczęcia operacji. Reguły zapotrzebowania dla towarów definiują te limity. Planowanie wykorzystuje rozkład wymagań do określenia, kiedy towary składowe są dostępne. W przypadku planowania bez ograniczonych materiałów system zakłada, że wszystkie towary składowe są dostępne, gdy są potrzebne.

## <a name="finite-properties"></a>Ograniczone właściwości
Planowanie zadań z uwzględnieniem ograniczonych właściwości wymaga, aby dla operacji marszruty produkcji były określone pewne właściwości. Warunki określone przez te właściwości muszą być spełnione, aby było możliwe zarezerwowanie zdolności produkcyjnych.

## <a name="references"></a>Odwołania
W ramach planowania zadań są planowane wszystkie produkcje powiązane z bieżącą produkcją. Jeśli produkcja ma jedną lub więcej produkcji podrzędnych, powinny one zostać zaplanowane w tym samym czasie co produkcja główna, ponieważ produkcja główna nie może się rozpocząć, dopóki nie zostaną zakończone jej produkcje podrzędne.

## <a name="schedule-resources"></a>Planowanie zasobów
Aparat planowania sprawdza kombinacje zasobów, by określić te kombinacje, które mogą spełnić wymagania. Można określić kryteria wyboru, wybierając jedną z następujących wartości w polu **Wybór zasobu głównego** na stronie **Parametry planowania**:

-   **Czas trwania** — aparat planowania wybiera zasoby, które mają najkrótszy czas realizacji. **Uwaga:** Planowanie według czasu trwania może powodować spadek wydajności, jeśli ta sama grupa zawiera wiele zasobów i są używane operacje podrzędne. Można zaplanować maksymalnie 32 zasoby dla każdej operacji. Po przekroczeniu tej ilości wyświetlany jest komunikat z dziennika informacyjnego, a planowanie zadań nie może znaleźć najlepsze alternatywnego gniazda produkcyjnego.
-   **Priorytet** — aparat planowania wybiera zasób, który ma najwyższy priorytet, jeżeli dwa lub więcej zasobów mają takie same możliwości i poziomy. Zasób, który ma najniższą wartość liczbową w tym polu, ma najwyższy priorytet.

Podczas planowania zadań system planuje zasoby na podstawie ograniczeń zdefiniowanych w parametrach zasobów. Można kontrolować zdolności produkcyjne zasobów za pomocą ustawień kalendarza. System oblicza ładunki dla zasobów w trakcie procesu planowania. **Uwaga:** W przypadku zastosowania funkcji planowania produkcji można uruchomić planowanie zadań po przeprowadzeniu planowania produkcji. Jeśli planowanie produkcji nie jest przeprowadzane, można uruchomić planowanie zadań jako samodzielny proces.

## <a name="maximum-capacities-for-resources-per-job-order"></a>Maksymalne zdolności produkcyjne zasobów na zlecenie zadania
Zasoby są przydzielane do zadań w wyniku planowania zadań. Istnieje możliwość ustalania maksymalnych zdolności produkcyjnych zasobów na zlecenie zadania. Można na przykład ustawić w systemie opcję planowania nie więcej niż 50 procent wszystkich zdolności produkcyjnych dla zlecenia produkcyjnego. Taka konfiguracja daje większą kontrolę nad planowaniem zasobów na poziomie planowania zadań. Pozwala więc łatwiej zapobiegać problemom, jeśli nie ma wystarczających zdolności produkcyjnych na wykonywanie produkcji jednoczesnej.

## <a name="resource-efficiency"></a>Wydajność zasobów
Planowanie zadań bierze pod uwagę procenty wydajności określone dla zasobów. Procenty wydajności skracają lub wydłużają czas rezerwowany dla zasobu. W konsekwencji czas realizacji jest również skracany lub wydłużany. Do obliczania używana jest następująca formuła: czas planowania = czas × 100 ÷ procent wydajności. W tej formule *czas* obejmuje zarówno czas procesu, jak czasu konfigurowania.





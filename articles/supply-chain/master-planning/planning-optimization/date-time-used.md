---
title: Parametry daty i godziny używane przez optymalizację planowania
description: Ten artykuł zawiera informacje dotyczące parametrów daty i godziny, które są używane podczas operacji optymalizacji planowania.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2ef78c73a1c7033735f9586229ff7ba21daaa5ef
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740912"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>Parametry daty i godziny używane przez optymalizację planowania

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące parametrów daty i godziny, które są używane podczas operacji optymalizacji planowania.

Podczas gdy przestarzały aparat planowania głównego używa dat transakcji we wszystkich obliczeniach, optymalizacja planowania działa na wartościach dat i godzin, które są konwertowane na daty. Taka różnica w zachowaniu może prowadzić do sytuacji, w której na przykład transakcje prognoz utworzone o północy w dniu uruchomienia planowania głównego nie są uwzględniane, ponieważ optymalizacja planowania uważa, że zostały utworzone przed bieżącą datą.

## <a name="parameters-for-issue-and-demand-transactions"></a>Parametry transakcji wydania i popytu

W poniższej tabeli wymieniono parametry optymalizacji planowania używane podczas przetwarzania transakcji wydania i popytu.

| Parametr | Nazwa parametru w funkcji optymalizacji planowania | Opis | Odpowiednik pola w aplikacji Microsoft Dynamics 365 Supply Chain Management (w tabeli ReqTrans) |
|---|---|---|---|
| Planowany czas wydania | `PlannedIssueTime` | Aktualna zaplanowana data wydania. | **Do dnia** (`FuturesDate`) i **Opóźnienie do godziny** (`FuturesTime`) |
| Żądany czas wydania | `RequestedIssueTime` | Data wydania żądana przez użytkownika i ustawiona w aplikacji Supply Chain Management. Ten parametr ma zastosowanie tylko do zwolnionych lub zatwierdzonych zamówień planowanych. W przypadku zamówień planowanych wartość domyślna jest pusta. | **Data wymagalności** (`ReqDateDlvOrig`) |
| Wymagany czas wydania | `RequiredIssueTime` | Wymagana data wydania skorygowana przez optymalizację planowania. Jeśli żądany czas wydania przypada w przeszłości po uruchomieniu optymalizacji planowania, wymagany czas wydania zostanie skorygowany do pierwszego otwartego dnia, który nie jest wcześniejszy niż dzisiejsza data. Jeśli żądany czas wydania jest oznaczony w kalendarzu jako zablokowany, wymagany czas wydania zostanie skorygowany do pierwszego otwartego dnia przed tym dniem. | **Data zapotrzebowania** (`ReqDate`) i **Godzina zapotrzebowania** (`ReqTime`) |
| Opóźnienie czasu wydania | `IssueTimeDelay` | Różnica czasu między planowanym czasem wydania a wymaganym czasem wydania dla zatwierdzonych i zwolnionych zamówień albo wymaganym czasem wydania. | **Opóźnienie (w dniach)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>Parametry transakcji przyjęcia i podaży

W poniższej tabeli wymieniono parametry optymalizacji planowania używane podczas przetwarzania transakcji przyjęcia i podaży.

| Parametr | Nazwa parametru w funkcji optymalizacji planowania | Opis | Odpowiednik pola w aplikacji Supply Chain Management (w tabeli ReqTrans lub ReqPO) |
|---|---|---|---|
| Planowany czas dostępności | `PlannedAvailabilityTime` | Data planowanej dostępności przyjęcia. | **Data zapotrzebowania** (`ReqDate`) i **Godzina zapotrzebowania** (`ReqTime`) |
| Planowany czas przyjęcia | `PlannedReceiptTime` | Data przyjęcia do lokalizacji. | **Data zakończenia** (`FuturesDate`), **Opóźnione do czasu** (`FuturesTime`) i **Data dostawy** (`ReqDateDlv`) lub **Żądana data** (`ReqDateDlvOrig`), jeśli zamówienie nie zostało jeszcze zwolnione. |
| Wymagany lanowany czas dostępności | `RequiredAvailabilityTime` | Wymagana data dostępności skorygowana przez optymalizację planowania. | **Data zapotrzebowania** (`ReqDate`) i **Godzina zapotrzebowania** (`ReqTime`) |
| Oczekiwany czas przyjęcia | `ExpectedReceiptTime` | Oczekiwana data przyjęcia dla zwolnionego przyjęcia. Ta wartość jest ustawiana przez użytkownika w aplikacji Supply Chain Management i nie jest korygowana przez optymalizację planowania. Ten parametr dotyczy tylko zwolnionych przyjęć. | **Data wymagalności** (`ReqDateDlvOrig`) |
| Żądana godzina przyjęcia | `RequiredReceiptTime` | Wymagana data przyjęcia skorygowana przez optymalizację planowania. | **Data zapotrzebowania** (`ReqDate`) i **Godzina zapotrzebowania** (`ReqTime`) |
| Planowany czas zamówienia | `PlannedOrderingTime` | Data złożenia zamówienia obliczana przez optymalizację planowania. | **Data zamówienia** (`ReqDateOrder`) i **Godzina zamówienia** (`ReqTimeOrder`) |
| Planowana godzina rozpoczęcia działania | `PlannedActivityStartTime` | Data rozpoczęcia działania dla danego przyjęcia. | **Start rozpoczęcia** (`SchedFromDate`) |
| Opóźnienie czasu przyjęcia | `ReceiptTimeDelay` | Różnica czasu między planowanym czasem przyjęcia a wymaganym czasem przyjęcia. | **Opóźnienie (dni)** (`FuturesDays`) i **Opóźnienie do czasu** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Przykłady parametru daty używanego przez optymalizację planowania

Plany na poniższych ilustracjach są na poziomie dnia, ale optymalizacja planowania jest uruchamiana na bardziej szczegółowym poziomie. Na przykład, ponieważ marże mogą być w godzinach, czasem zamówienia dla planowania może być 22 stycznia 2021, godzina 11:35 itd.

### <a name="example-1-simple-scenario"></a>Przykład 1. Prosty scenariusz

Jedno zamówienie sprzedaży o wymaganym czasie wydania w dniu 22 stycznia jest objęte jednym zamówieniem zakupu. Użyto następujących ustawień:

- Brak czasu realizacji
- Brak kalendarzy (wszystkie dni są otwarte.)
- Brak marży

Na poniższej ilustracji pokazano ten scenariusz. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Prosty scenariusz.](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>Przykład 2. Scenariusz z czasem realizacji

Jedno zamówienie sprzedaży o wymaganym czasie wydania w dniu 22 stycznia jest objęte jednym zamówieniem zakupu. Użyto następujących ustawień:

- Trzy dni czasu realizacji
- Brak kalendarzy (wszystkie dni są otwarte.)
- Brak marży

Na poniższej ilustracji pokazano ten scenariusz. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Scenariusz z czasem realizacji.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>Przykład 3. Scenariusz z marżą

Jedno zamówienie sprzedaży o wymaganym czasie wydania w dniu 22 stycznia jest objęte jednym zamówieniem zakupu. Użyto następujących ustawień:

- Trzy dni czasu realizacji
- Marża zamówienia wynosząca cztery dni
- Marża dostępności wynosząca pięć dni
- Brak kalendarzy (wszystkie dni są otwarte.)

Na poniższej ilustracji pokazano ten scenariusz. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Scenariusz z marżą.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>Przykład 4. Scenariusz z opóźnieniem

Jedno zamówienie sprzedaży o wymaganym czasie wydania w dniu 22 stycznia jest objęte jednym zamówieniem zakupu. W tym przykładzie użyto tych samych ustawień, co przykład 3, ale data planowania została przeniesiona na 15 stycznia. Planowanie wstecz (czerwone znaczniki) nie powiedzie się, ponieważ planowana godzina zamówienia musi być wcześniejsza niż dzisiejsza data. Dlatego planowanie główne musi planować w przód i występują opóźnienia.

Na poniższej ilustracji pokazano ten scenariusz. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Scenariusz z opóźnieniem.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>Przykład 5. Scenariusz z przeniesieniem

Jedno zamówienie sprzedaży z magazynu 1, dla których żądany czas wydania przypadał 22 stycznia, jest objęte jednym zamówieniem przeniesienia z magazynu 2, które jest objęte planowanym zamówieniem zakupu. Użyto następujących ustawień:

- Trzy dni czasu realizacji przeniesienia (magazyn 1)
- Dwa dni czasu realizacji zakupu (magazyn 2)
- Brak kalendarzy (wszystkie dni są otwarte.)

Na poniższej ilustracji pokazano ten scenariusz. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Scenariusz z przeniesieniem.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>Przykład 6. Scenariusz z czasem realizacji i kalendarzami

Jedno zamówienie sprzedaży o wymaganym czasie wydania w dniu 22 stycznia jest objęte jednym zamówieniem zakupu. Użyto następujących ustawień:

- Trzy dni czasu realizacji
- Kalendarz wydań (zamknięty w piątek)
- Kalendarz dostępności (zamknięty w czwartek i piątek)
- Kalendarz przyjęć (zamknięty we wtorek, środę i niedzielę)
- Kalendarz czasu realizacji (zamknięty w czwartek i piątek)
- Kalendarz zamówień (otwarty w poniedziałek i sobotę)

Na poniższej ilustracji pokazano ten scenariusz. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Scenariusz z czasem realizacji i kalendarzami.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>Przykład 7. Scenariusz z opóźnieniem i kalendarzami

Jedno zamówienie sprzedaży o wymaganym czasie wydania w dniu 22 stycznia jest objęte jednym zamówieniem zakupu. W tym przykładzie użyto tych samych ustawień, co przykład 6, ale data planowania została przeniesiona na 13 stycznia. Planowanie wstecz (czerwone znaczniki) nie powiedzie się, ponieważ planowana godzina zamówienia musi być wcześniejsza niż dzisiejsza data. Dlatego planowanie główne musi planować w przód i występują opóźnienia.

Na poniższej ilustracji pokazano ten scenariusz. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Scenariusz z opóźnieniem i kalendarzami.](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)

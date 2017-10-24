---
title: "Terminy realizacji zamówień"
description: "Ten artykuł zawiera informacje o terminach wprowadzania zamówień. Termin wprowadzania zamówień to graniczny czas decydujący o tym, czy zamówienie klienta jest traktowane (i realizowane) tak jakby zostało odebrany w dniu bieżącym lub następnym."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOrderEntryDeadlineGroup, InventOrderEntryDeadlineParameters, InventOrderEntryDeadlineTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7151
ms.assetid: bbc4f9a2-df4b-4d92-9f18-25282a85541f
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9e9d1912abf9a356542ce2c317fa717bc991dbf9
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="order-entry-deadlines"></a>Terminy realizacji zamówień

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o terminach wprowadzania zamówień. Termin wprowadzania zamówień to graniczny czas decydujący o tym, czy zamówienie klienta jest traktowane (i realizowane) tak jakby zostało odebrany w dniu bieżącym lub następnym.

W wielu firmach tylko zamówienia sprzedaży odebrane przed konkretną godziną są traktowane jako odebrane danego dnia. Wszystkie zamówienia odebrane po tym czasie są traktowane jako odebrane w następnym dniu roboczym. Ten limit czasowy dla zamówień jest nazywany terminem wprowadzania zamówień.  

Terminy realizacji zamówień są używane jako dane wejściowe dla zobowiązań zamówień. To ułatwia zarządzanie oczekiwaniami klientów odnośnie do dostaw zamówień. Odbiorca wie na przykład, że składając zamówienie przed daną godziną, towary zostaną wysłane w tym samym dniu. Jeśli nie zdążą złożyć zamówienia w odpowiednim czasie, towary zostaną wysłane w następnym dniu roboczym. Terminy realizacji zamówień ustawia się na podstawie zdolności magazynowych i harmonogramu przewoźnika.  

Na stronie **Terminy wprowadzania zamówień** konfiguruje się czasy realizacji zamówień dla wszystkich dni tygodnia. Jeśli zamówienie zostanie złożone po określonej godzinie, jest traktowane jako odebrane w następnym dniu. Domyślnie terminy te są ustawione na godzinę 23:59, tj. minutę przed północą na końcu odpowiedniego dnia. Można zmienić terminy domyślne tak, aby pokrywały się z rzeczywistymi terminami wysyłki lub odbioru.  

Można zdefiniować terminy wprowadzania zamówień dla określonej grupy odbiorców. Na przykład chcesz, aby określona grupa odbiorców miała terminy późniejsze niż pozostali odbiorcy. W takim przypadku najpierw definiuje się terminy wprowadzania zamówień na stronie **Grupy terminów realizacji zamówień**. Następnie przypisuje się grupy do odbiorców na stronie **Odbiorcy**.  

Jeśli firma ma kilka oddziałów, można skonfigurować terminy wprowadzania zamówień dla każdego oddziału. Jeśli oddziały te znajdują się w różnych strefach czasowych, terminy wprowadzania zamówień należy skonfigurować w odpowiednich strefach czasowych. Jednak w przypadku zamówień sprzedaży i ofert sprzedaży terminy wprowadzania zamówień są konwertowane na strefę czasową użytkownika na stronie **Dostępne daty wysyłki i przyjęcia**.  

Na stronie **Uaktywnienie kombinacji terminów realizacji zamówień** definiuje się dozwolone kombinacje lokalizacji i grupy terminów wprowadzania zamówień.

## <a name="example-order-entry-deadline"></a>Przykład: Termin realizacji zamówień
Termin realizacji zamówienia we wtorek na godzinę 16:00. W konkretny wtorek o godzinie 17:00 chcesz ustawić bieżącą datę jako datę wysyłki. (Należy pamiętać, że w tym przykładzie nie ma czasu realizacji zamówienia). Jeśli pole wyboru **Kontrola daty dostawy** jest zaznaczone, pojawia się ostrzeżenie informujące o tym, że dane są nieprawidłowe. To ostrzeżenie jest wyświetlane na stronie **Dostępne daty wysyłki i przyjęcia**, na której można wybrać alternatywne daty.

## <a name="example-different-order-entry-deadlines-per-site"></a>Przykład: różne terminy wprowadzania zamówień dla poszczególnych oddziałów
Firma ma dwa oddziału. Znajdują się one w dwóch różnych strefach czasowych, jak pokazano w poniższej tabeli.

| Oddziałów A                      | Oddziałów B                      |
|-----------------------------|-----------------------------|
| Kalifornia                  | Floryda                     |
| Pacyficzny czas standardowy (PST) | Wschodni czas standardowy (EST) |

Oddziały A i B określiły następujące terminy wprowadzania zamówień:

| Dzień tygodnia             | A: Terminy realizacji zamówień (PST) | B: Terminy wprowadzania zamówień (EST) |
|-----------------------------|--------------------------------|--------------------------------|
| Poniedziałek                      | 13:00                          | 14:00                          |
| Wtorek                     | 13:00                          | 14:00                          |
| Środa                   | 13:00                          | 14:00                          |
| Czwartek                    | 13:00                          | 14:00                          |
| Piątek                      | 13:00                          | 14:00                          |

Odpowiadasz za przetwarzanie zamówień w stanie Utah w strefie czasowej Górski czas standardowy (MST). Oznacza to, że ilekroć wprowadzasz zamówienia w oddziale A przed godziną 14:00 MST i oddziałowi B przed godziną 12:00 MST, robisz to przed upływem terminów wprowadzania zamówień obu oddziałów.  

W następującej tabeli pokazano terminy wprowadzania zamówień obu oddziałów, A i B, przekonwertowane na czas MST:

| Oddział A: PST         | Oddział A: MST        | Oddział B: EST           | Oddział B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00               | 14:00              | 14:00                 | 12:00              |

**Uwaga:** w przypadku zmiany czasu z zimowego na letni i na odwrót terminy wprowadzania zamówień są odpowiednio korygowane.

## <a name="example-same-order-entry-deadline-per-site"></a>Przykład: te same terminy wprowadzania zamówień dla poszczególnych oddziałów
Firma ma dwa oddziału. Znajdują się one w dwóch różnych strefach czasowych, jak pokazano w poniższej tabeli.

| Oddziałów A                      | Oddziałów B                      |
|-----------------------------|-----------------------------|
| Kalifornia                  | Floryda                     |
| Pacyficzny czas standardowy (PST) | Wschodni czas standardowy (EST) |

Oddziały A i B określiły następujące terminy wprowadzania zamówień:

| Dzień tygodnia | PST i EST |
|-----------------|-------------|
| Poniedziałek          | 13:00       |
| Wtorek         | 13:00       |
| Środa       | 13:00       |
| Czwartek        | 13:00       |
| Piątek          | 13:00       |

Odpowiadasz za przetwarzanie zamówień w stanie Utah w strefie czasowej MST. Oznacza to, że ilekroć wprowadzasz zamówienia w oddziale A przed godziną 14:00 MST i oddziałowi B przed godziną 11:00 MST, robisz to przed upływem terminów wprowadzania zamówień obu oddziałów. 

W następującej tabeli pokazano terminy wprowadzania zamówień obu oddziałów, A i B, przekonwertowane na czas MST:

| Oddział A: PST         | Oddział A: MST        | Oddział B: EST           | Oddział B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00               | 14:00              | 13:00                 | 11:00              |

**Uwaga:** w przypadku zmiany czasu z zimowego na letni i na odwrót terminy wprowadzania zamówień są odpowiednio korygowane.

<a name="see-also"></a>Informacje dodatkowe
--------

[Harmonogramy dostaw](delivery-schedules.md)





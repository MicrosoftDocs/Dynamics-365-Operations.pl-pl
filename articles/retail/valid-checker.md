---
title: Sprawdzanie spójności transakcji w rozwiązaniu Retail
description: W tym temacie opisano funkcje sprawdzania spójności transakcji sprzedaży detalicznej w rozwiązaniu Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 972c4d6b244eebc85cc801353ce8fb25ecbc0655
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517144"
---
# <a name="retail-transaction-consistency-checker"></a>Sprawdzanie spójności transakcji w rozwiązaniu Retail


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

W tym temacie opisano funkcje sprawdzania spójności transakcji sprzedaży detalicznej wprowadzone w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations (wersja 8.1.3). Sprawdzanie spójności pozwala zidentyfikować i odizolować niespójne transakcji przed ich pobraniem przez proces księgowania zestawienia.

Po zaksięgowaniu zestawienia w rozwiązaniu Retail funkcja księgowania może zakończyć się niepowodzeniem z powodu niespójności danych w tabelach transakcji sprzedaży detalicznej. Przyczyną tego problemu z danymi mogą być nieprzewidziane problemy w aplikacji punktu sprzedaży (POS) lub jeśli transakcje zostały nieprawidłowo zaimportowane z innych systemów POS. Przykłady wyświetlania tych niespójności: 

  - Suma transakcji w tabeli nagłówka jest niezgodna z łączną wartością transakcji w wierszach.
  - Liczba wierszy w tabeli nagłówka jest niezgodna z liczbą wierszy w tabeli transakcji.
  - Podatki w tabeli nagłówka są niezgodne z kwotą podatku w wierszach. 
  
Kiedy niezgodne transakcje są pobierane przez proces księgowania zestawienia, powstają niespójne faktury sprzedaży i dzienniki płatności i w efekcie cały proces księgowania zestawienia kończy się niepowodzeniem. Odzyskiwanie zestawień w tym stanie wymaga skomplikowanych poprawek danych w wielu tabelach transakcji. Kontroler spójności transakcji sprzedaży detalicznej zapobiega takim problemom.

Wykres poniżej pokazuje proces księgowania z kontrolerem spójności transakcji.

![Proces księgowania zestawień z kontrolerem spójności transakcji sprzedaży detalicznej](./media/validchecker.png "Proces księgowania zestawień z kontrolerem spójności transakcji sprzedaży detalicznej")

Zadanie wsadowe **Sprawdź poprawność transakcji w sklepie** sprawdza spójność tabel transakcji sprzedaży detalicznej w następujących scenariuszach.

- Konto odbiorcy — sprawdza, czy konto odbiorcy w tabelach transakcji sprzedaży detalicznej istnieje w danych głównej odbiorcy w centrali.
- Liczba wierszy — sprawdza, czy liczba wierszy w tabeli nagłówka transakcji jest zgodna z liczbą wierszy w tabelach transakcji sprzedaży.

## <a name="set-up-the-consistency-checker"></a>Konfigurowanie modułu sprawdzania spójności
Skonfiguruj proces wsadowy „Sprawdź poprawność transakcji w sklepie” na **Handel detaliczny \> Składniki IT w handlu detalicznym \> Księgowanie w punkcie sprzedaży**, dla okresowych zadań. Zadanie wsadowe można zaplanować według hierarchii organizacyjnej sklepu w sposób podobny do tego, w jaki skonfigurowane są procesy „Oblicz zestawienie w trybie wsadowym” i „Księgowanie zestawienia w trybie wsadowym”. Zalecamy skonfigurowanie tego procesu w taki sposób, aby uruchamiał się wiele razy w ciągu dnia i każdorazowo po wykonaniu zadania ściągania.

## <a name="results-of-validation-process"></a>Wyniki procesu sprawdzania
Wyniki sprawdzania przez proces wsadowy są zaznaczone na odpowiedniej transakcji sprzedaży detalicznych. Pole **Stan weryfikacji** w rekordzie transakcji sprzedaży detalicznej ma wartość **Powodzenie** lub **Błąd**, a data ostatniej weryfikacji znajduje się w polu **Godzina ostatniej weryfikacji**.

Aby wyświetlić dłuższy opis błędu sprawdzania poprawności, zaznacz odpowiedni rekord transakcji sklepu i kliknij przycisk **Błędy weryfikacji**.

Transakcje, które nie przeszły weryfikacji, oraz transakcji, które nie zostały jeszcze zweryfikowane, nie będą pobierane do zestawień. W trakcie procesu „Oblicz zestawienie” użytkownicy otrzymają powiadomienie, że istnieją transakcje, które mogły zostać uwzględnione w zestawieniu, ale tak się nie stało.

W przypadku wystąpienia błędu weryfikacji można wyeliminować tylko po skontaktowaniu się z Pomocą techniczną firmy Microsoft. W przyszłej wersji zostanie dodana funkcja pozwalająca użytkownikom naprawiać rekordy z błędami za pomocą interfejsu. Zostaną również dodane funkcje rejestrowania i inspekcji pozwalające śledzić historię modyfikacji.

> [!NOTE]
> Oprócz tego w przyszłej wersji pojawią się też dodatkowe reguły weryfikacji dostosowane do innych scenariuszy.

---
title: Sprawdzanie spójności transakcji sprzedaży detalicznej
description: W tym temacie opisano funkcje sprawdzania spójności transakcji sprzedaży detalicznej w rozwiązaniu Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 05/30/2019
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
ms.openlocfilehash: 0413c2b236e442fb56098f1902b4d5b247ed4649
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018427"
---
# <a name="retail-transaction-consistency-checker"></a>Sprawdzanie spójności transakcji sprzedaży detalicznej


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

W tym temacie opisano funkcje sprawdzania spójności transakcji sprzedaży detalicznej. Moduł sprawdzania spójności umożliwia identyfikowanie i izolowanie niespójnych transakcji przed pobraniem ich przez proces księgowania zestawienia.

Po zaksięgowaniu zestawienia w rozwiązaniu Retail funkcja księgowania może zakończyć się niepowodzeniem z powodu niespójności danych w tabelach transakcji sprzedaży detalicznej. Przyczyną tego problemu z danymi mogą być nieprzewidziane problemy w aplikacji punktu sprzedaży (POS) lub nieprawidłowy import transakcji z systemów POS innych firm. Przykłady wyświetlania tych niespójności: 

- Suma transakcji w tabeli nagłówka jest niezgodna z łączną wartością transakcji w wierszach.
- Liczba wierszy w tabeli nagłówka jest niezgodna z liczbą wierszy w tabeli transakcji.
- Podatki w tabeli nagłówka są niezgodne z kwotą podatku w wierszach. 

Kiedy niezgodne transakcje są pobierane przez proces księgowania zestawienia, powstają niespójne faktury sprzedaży i dzienniki płatności i w efekcie cały proces księgowania zestawienia kończy się niepowodzeniem. Odzyskiwanie zestawień w tym stanie wymaga skomplikowanych poprawek danych w wielu tabelach transakcji. Kontroler spójności transakcji sprzedaży detalicznej zapobiega takim problemom.

Wykres poniżej pokazuje proces księgowania z kontrolerem spójności transakcji.

![Proces księgowania zestawień z kontrolerem spójności transakcji sprzedaży detalicznej](./media/validchecker.png "Proces księgowania zestawień z kontrolerem spójności transakcji sprzedaży detalicznej")

Proces wsadowy **Sprawdź poprawność transakcji w sklepie** sprawdza spójność tabel transakcji sprzedaży detalicznej w następujących scenariuszach.

- **Konto odbiorcy** — sprawdza, czy konto odbiorcy w tabelach transakcji sprzedaży detalicznej istnieje w danych głównych odbiorcy w centrali.
- **Liczba wierszy** — sprawdza, czy liczba wierszy w tabeli nagłówka transakcji jest zgodna z liczbą wierszy w tabelach transakcji sprzedaży.
- **Cena zawiera podatek** — sprawdza, czy parametr **Cena zawiera podatek** jest spójny w wierszach transakcji.
- **Kwota płatności** — sprawdza, czy rekordy płatności pasują do kwoty płatności w nagłówku.
- **Kwota brutto** — sprawdza, czy kwota brutto w nagłówku jest sumą kwot netto w wierszach i kwoty podatku.
- **Kwota netto** — sprawdza, czy kwota netto w nagłówku jest sumą kwot netto w wierszach.
- **Niedopłata/Nadpłata** — sprawdza, czy różnica między kwotą brutto w nagłówku a kwotą płatności nie przekracza maksymalnej skonfigurowanej niedopłaty/nadpłaty.
- **Kwota rabatu** — sprawdza, czy kwota rabatu w tabelach rabatów i kwota rabatu w tabelach wierszy transakcji detalicznych są spójne i czy kwota rabatu w nagłówku jest sumą kwot rabatów w wierszach.
- **Rabat wiersza** — sprawdza, czy rabat wiersza w wierszu transakcji jest sumą wszystkich wierszy w tabeli rabatów, które odpowiadają wierszowi transakcji.
- **Towar na kartę upominkową** — rozwiązanie Retail nie obsługuje zwrotów towarów przekazanych za pośrednictwem karty upominkowej. Można jednak wypłacić saldo karty upominkowej. Każdy towar na karcie upominkowej, który jest przetwarzany jako wiersz zwrotu, a nie wiersz wypłaty, powoduje niepowodzenie wykonywania procesu księgowania zestawienia. Proces weryfikacji towarów przekazanych za pośrednictwem karty upominkowej pomaga zagwarantować, że w tabelach transakcji detalicznych będą istnieć tylko wiersze wypłat kart upominkowych.
- **Cena ujemna** — sprawdza, czy nie występują wiersze transakcji z ujemną ceną.
- **Towar i wariant** — sprawdza, czy towary i warianty wymienione w wierszach transakcji istnieją w pliku głównym towarów i wariantów.
- **Kwota podatku** — sprawdza, czy rekordy podatku pasują do kwot podatku w wierszach. 

## <a name="set-up-the-consistency-checker"></a>Konfigurowanie modułu sprawdzania spójności

Skonfiguruj cykliczne uruchamianie procesu wsadowego „Sprawdź poprawność transakcji w sklepie” (w obszarze **Handel detaliczny \> Składniki IT w handlu detalicznym \> Księgowanie w punkcie sprzedaży**). Zadanie wsadowe można zaplanować według hierarchii organizacyjnej sklepu w sposób podobny do tego, w jaki skonfigurowane są procesy „Oblicz zestawienie w trybie wsadowym” i „Księgowanie zestawienia w trybie wsadowym”. Zalecamy skonfigurowanie tego procesu w taki sposób, aby uruchamiał się wiele razy w ciągu dnia i każdorazowo po wykonaniu zadania ściągania.

## <a name="results-of-validation-process"></a>Wyniki procesu sprawdzania

Wyniki sprawdzania przez proces wsadowy są zaznaczone na odpowiedniej transakcji sprzedaży detalicznych. Pole **Stan weryfikacji** w rekordzie transakcji sprzedaży detalicznej ma wartość **Powodzenie** lub **Błąd**, a data ostatniej weryfikacji znajduje się w polu **Godzina ostatniej weryfikacji**.

Aby wyświetlić dłuższy opis błędu sprawdzania poprawności, zaznacz odpowiedni rekord transakcji sklepu i kliknij przycisk **Błędy weryfikacji**.

Transakcje, które nie przeszły weryfikacji, oraz transakcji, które nie zostały jeszcze zweryfikowane, nie będą pobierane do zestawień. W trakcie procesu „Oblicz zestawienie” użytkownicy otrzymają powiadomienie, że istnieją transakcje, które mogły zostać uwzględnione w zestawieniu, ale tak się nie stało.

W przypadku wystąpienia błędu weryfikacji można wyeliminować tylko po skontaktowaniu się z Pomocą techniczną firmy Microsoft. W przyszłej wersji zostanie dodana funkcja pozwalająca użytkownikom naprawiać rekordy z błędami za pomocą interfejsu. Zostaną również dodane funkcje rejestrowania i inspekcji pozwalające śledzić historię modyfikacji.

> [!NOTE]
> Oprócz tego w przyszłej wersji pojawią się też dodatkowe reguły weryfikacji dostosowane do innych scenariuszy.

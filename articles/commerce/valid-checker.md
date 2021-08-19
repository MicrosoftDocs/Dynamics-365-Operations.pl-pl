---
title: Sprawdzanie spójności transakcji sprzedaży detalicznej
description: W tym temacie opisano funkcje sprawdzania spójności transakcji w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 10/07/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c8ba0f99743984860119deb96c889f5d62e1728c8772b9e6786d371690b61489
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741739"
---
# <a name="retail-transaction-consistency-checker"></a>Sprawdzanie spójności transakcji sprzedaży detalicznej

[!include [banner](includes/banner.md)]

W tym temacie opisano funkcje sprawdzania spójności transakcji w rozwiązaniu Microsoft Dynamics 365 Commerce. Moduł sprawdzania spójności umożliwia identyfikowanie i izolowanie niespójnych transakcji przed pobraniem ich za pomocą procesu księgowania zestawienia.

Gdy zestawienie jest księgowane, księgowanie może zakończyć się niepowodzeniem z powodu niespójności danych w tabelach transakcji handlowych. Przyczyną tego problemu z danymi mogą być nieprzewidziane problemy w aplikacji punktu sprzedaży (POS) lub nieprawidłowy import transakcji z systemów POS innych firm. Przykłady wyświetlania tych niespójności: 

- Suma transakcji w tabeli nagłówka jest niezgodna z łączną wartością transakcji w wierszach.
- Liczba wierszy w tabeli nagłówka jest niezgodna z liczbą wierszy w tabeli transakcji.
- Podatki w tabeli nagłówka są niezgodne z kwotą podatku w wierszach. 

Kiedy niezgodne transakcje są pobierane przez proces księgowania zestawienia, powstają niespójne faktury sprzedaży i dzienniki płatności i w efekcie cały proces księgowania zestawienia kończy się niepowodzeniem. Odzyskiwanie zestawień w tym stanie wymaga skomplikowanych poprawek danych w wielu tabelach transakcji. Kontroler spójności transakcji zapobiega takim problemom.

Wykres poniżej pokazuje proces księgowania z kontrolerem spójności transakcji.

![Proces księgowania zestawienia z modułem sprawdzania spójności transakcji.](./media/validchecker.png "Proces księgowania zestawienia z modułem sprawdzania spójności transakcji")

Proces wsadowy **Sprawdź poprawność transakcji w sklepie** sprawdza spójność tabel transakcji handlowych w następujących scenariuszach.

- **Konto odbiorcy** — sprawdza, czy konto odbiorcy w tabelach transakcji istnieje w danych głównych odbiorcy w centrali.
- **Liczba wierszy** — sprawdza, czy liczba wierszy w tabeli nagłówka transakcji jest zgodna z liczbą wierszy w tabelach transakcji sprzedaży.
- **Cena obejmuje podatek** — sprawdza, czy parametr **Cena obejmuje podatek** jest spójny w wierszach transakcji i czy cena w wierszu sprzedaży jest zgodna z konfiguracją ceny obejmującej podatek i zwolnionej z podatku.
- **Kwota płatności** — sprawdza, czy rekordy płatności pasują do kwoty płatności w nagłówku, uwzględniając także w konfiguracji zaokrąglanie groszowe w księdze głównej.
- **Kwota brutto** — sprawdza, czy kwota brutto w nagłówku jest sumą kwot netto w wierszach oraz kwoty podatku, uwzględniając także w konfiguracji zaokrąglanie groszowe w księdze głównej.
- **Kwota netto** — sprawdza, czy kwota netto w nagłówku jest sumą kwot netto w wierszach, uwzględniając także w konfiguracji zaokrąglanie groszowe w księdze głównej.
- **Niedopłata/Nadpłata** — sprawdza, czy różnica między kwotą brutto w nagłówku a kwotą płatności nie przekracza maksymalnej skonfigurowanej niedopłaty/nadpłaty, uwzględniając także w konfiguracji zaokrąglanie groszowe w księdze głównej.
- **Kwota rabatu** — sprawdza, czy kwota rabatu w tabelach rabatów i kwota rabatu w tabelach wierszy transakcji są spójne i czy kwota rabatu w nagłówku jest sumą kwot rabatów w wierszach, uwzględniając także w konfiguracji zaokrąglanie groszowe w księdze głównej.
- **Rabat wiersza** — sprawdza, czy rabat wiersza w wierszu transakcji jest sumą wszystkich wierszy w tabeli rabatów, które odpowiadają wierszowi transakcji.
- **Pozycja na kartę upominkową** — rozwiązanie Commerce nie obsługuje zwrotów pozycji przekazanych za pośrednictwem karty upominkowej. Można jednak wypłacić saldo karty upominkowej. Każda pozycja na karcie upominkowej, który jest przetwarzana jako wiersz zwrotu, a nie wiersz wypłaty, powoduje niepowodzenie wykonywania procesu księgowania zestawienia. Proces weryfikacji pozycji przekazanych za pośrednictwem karty upominkowej pomaga zagwarantować, że w tabelach transakcji będą istnieć tylko wiersze wypłat kart upominkowych.
- **Cena ujemna** — sprawdza, czy nie występują wiersze transakcji z ujemną ceną.
- **Towar i wariant** — sprawdza, czy towary i warianty wymienione w wierszach transakcji istnieją w pliku głównym towarów i wariantów.
- **Kwota podatku** — sprawdza, czy rekordy podatku pasują do kwot podatku w wierszach.
- **Numer seryjny** — sprawdza, czy wiersze transakcji dla pozycji kontrolowanych przez numer seryjny zawierają numer seryjny.
- **Znak** — sprawdza, czy znak na ilości i kwocie netto jest taki sam we wszystkich wierszach transakcji.
- **Data biznesowa** — sprawdza, czy okresy obrachunkowe są otwarte dla wszystkich dat biznesowych dla transakcji.
- **Opłaty** — sprawdza, czy kwota opłaty nagłówka i wiersza jest zgodna z ceną, z uwzględnieniem konfiguracji zawierającej podatek i zwolnionej z podatku.

## <a name="set-up-the-consistency-checker"></a>Konfigurowanie modułu sprawdzania spójności

Skonfiguruj cykliczne uruchamianie procesu wsadowego „Sprawdź poprawność transakcji w sklepie” w obszarze **Retail i Commerce \> Retail i Commerce — składniki IT \> Księgowanie w punkcie sprzedaży**. Zadanie wsadowe można zaplanować według hierarchii organizacyjnej sklepu w sposób podobny do tego, w jaki skonfigurowane są procesy „Oblicz zestawienie w trybie wsadowym” i „Księgowanie zestawienia w trybie wsadowym”. Zalecamy skonfigurowanie tego procesu w taki sposób, aby uruchamiał się wiele razy w ciągu dnia i każdorazowo po wykonaniu zadania ściągania.

## <a name="results-of-validation-process"></a>Wyniki procesu sprawdzania

Wyniki sprawdzania przez proces wsadowy są zaznaczone na odpowiedniej transakcji. Pole **Stan weryfikacji** w rekordzie transakcji ma wartość **Powodzenie** lub **Błąd**, a data ostatniej weryfikacji znajduje się w polu **Godzina ostatniej weryfikacji**.

Aby wyświetlić dłuższy opis błędu sprawdzania poprawności, zaznacz odpowiedni rekord transakcji sklepu i kliknij przycisk **Błędy weryfikacji**.

Transakcje, które nie przeszły weryfikacji, oraz transakcji, które nie zostały jeszcze zweryfikowane, nie będą pobierane do zestawień. W trakcie procesu „Oblicz zestawienie” użytkownicy otrzymają powiadomienie, że istnieją transakcje, które mogły zostać uwzględnione w zestawieniu, ale tak się nie stało.

W przypadku wystąpienia błędu weryfikacji można wyeliminować tylko po skontaktowaniu się z Pomocą techniczną firmy Microsoft. W przyszłej wersji zostanie dodana funkcja pozwalająca użytkownikom naprawiać rekordy z błędami za pomocą interfejsu. Zostaną również dodane funkcje rejestrowania i inspekcji pozwalające śledzić historię modyfikacji.

> [!NOTE]
> Oprócz tego w przyszłej wersji pojawią się też dodatkowe reguły weryfikacji dostosowane do innych scenariuszy.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
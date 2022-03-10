---
title: Sprawdzanie poprawności transakcji sklepu na potrzeby obliczenia zestawienia
description: W tym temacie opisano funkcje sprawdzania poprawności transakcji sklepu w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: f51b1f39aa212fe8587761721194db7791bec5bc
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087456"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>Sprawdzanie poprawności transakcji sklepu na potrzeby obliczenia zestawienia

[!include [banner](includes/banner.md)]

W tym temacie opisano funkcje sprawdzania poprawności transakcji sklepu w rozwiązaniu Microsoft Dynamics 365 Commerce. Proces sprawdzania poprawności umożliwia zidentyfikowanie i oznaczenie transakcji, które będą powodować błędy księgowania, przed pobraniem ich za pomocą procesu księgowania zestawienia.

Podczas próby zaksięgowania zestawienia proces sprawdzania poprawności może zakończyć się niepowodzeniem z powodu niespójności danych w tabelach transakcji handlowych. Oto kilka przykładów czynników, które mogą powodować wspomniane niespójności:

- Suma transakcji w tabeli nagłówka jest niezgodna z łączną wartością transakcji w wierszach.
- Liczba towarów określona w tabeli nagłówka nie odpowiada liczbie towarów w tabeli transakcji.
- Podatki w tabeli nagłówka są niezgodne z kwotą podatku w wierszach. 

Gdy niezgodne transakcje zostaną pobrane przez proces księgowania zestawienia, utworzone faktury sprzedaży i arkusze płatności mogą spowodować, że proces księgowania zestawienia zakończy się niepowodzeniem. Proces **Sprawdź poprawność transakcji w sklepie** zapobiega tego rodzaju problemom, dając gwarancję, że w ramach procesu obliczania zestawień transakcji są uwzględniane tylko te transakcje, które spełniły wymogi reguł sprawdzania poprawności transakcji.

Na poniższej ilustracji przedstawiono realizowane w ciągu dnia cykliczne procesy przekazywania transakcji, sprawdzania poprawności transakcji, obliczania i księgowania zestawień transakcji, a także realizowanych na koniec dnia procesów obliczania i księgowania sprawozdań finansowych.

![Ilustracja przedstawiająca realizowane w ciągu dnia cykliczne procesy przekazywania transakcji, sprawdzania poprawności transakcji, obliczania i księgowania zestawień transakcji, a także realizowane na koniec dnia procesy obliczania i księgowania sprawozdań finansowych.](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>Reguły sprawdzania poprawności transakcji sklepu

Proces wsadowy **Sprawdź poprawność transakcji w sklepie** sprawdza spójność tabel transakcji handlowych na podstawie następujących reguł sprawdzania poprawności.

> [!NOTE]
> Reguły sprawdzania poprawności będą w dalszym ciągu dodawane w kolejnych wydaniach.

### <a name="transaction-header-validation-rules"></a>Reguły sprawdzania poprawności nagłówka transakcji

W poniższej tabeli wymieniono reguły sprawdzania poprawności nagłówka transakcji, pod kątem których nagłówek transakcji detalicznych jest sprawdzany przed przekazem wspomnianych transakcji do księgowania zestawienia.

| Reguła | Opis |
|-------|-------------|
| Data biznesowa | Ta reguła sprawdza, czy data biznesowa transakcji jest skojarzona z otwartym okresem obrachunkowym w księdze. |
| Zaokrąglanie waluty | Ta reguła sprawdza, czy kwoty transakcji są zaokrąglane zgodnie z regułą zaokrąglania walut. |
| Konto odbiorcy | Ta reguła sprawdza, czy odbiorca użyty w transakcji istnieje w bazie danych. |
| Kwota rabatu | Ta reguła sprawdza, czy kwota rabatu w nagłówku jest sumą kwot rabatów w wierszach. |
| Stan księgowania dokumentu podatkowego (Brazylia) | Ta reguła sprawdza, czy dokument podatkowy może zostać pomyślnie zaksięgowany. |
| Kwota brutto | Ta reguła sprawdza, czy kwota brutto w nagłówku transakcji odpowiada podanej w wierszach kwocie netto z podatkiem powiększonej o opłaty. |
| Netto | Ta reguła sprawdza, czy kwota netto w nagłówku transakcji odpowiada podanej w wierszach kwocie netto bez podatku powiększonej o opłaty. |
| Netto + podatek | Ta reguła sprawdza, czy kwota brutto w nagłówku transakcji odpowiada podanej w wierszach kwocie netto bez podatku powiększonej o wszelkie podatki i opłaty. |
| Liczba towarów | Ta reguła sprawdza, czy liczba towarów określona w nagłówku transakcji odpowiada sumie ilości w wierszach transakcji. |
| Kwota płatności | Ta reguła sprawdza, czy kwota płatności w nagłówku transakcji odpowiada sumie wszystkich transakcji płatności. |
| Obliczanie zwolnienia z podatku | Ta reguła sprawdza, czy suma obliczonej kwoty i kwoty zwolnionej z podatku z wierszy opłat jest równa pierwotnej obliczonej kwocie. |
| Ceny uwzględniające podatek | Ta reguła sprawdza, czy flaga **Podatek jest wliczony w cenę** jest spójna między nagłówkiem transakcji i transakcjami podatkowymi. |
| Transakcja nie jest pusta | Ta reguła sprawdza, czy transakcja zawiera wiersze i czy istnieje co najmniej jeden wiersz, który nie został unieważniony. |
| Niedopłata/Nadpłata | Reguła sprawdza, czy różnica między kwotą brutto a kwotą płatności nie przekracza maksymalnej skonfigurowanej niedopłaty/nadpłaty. |

### <a name="transaction-line-validation-rules"></a>Reguły sprawdzania poprawności wiersza transakcji

W poniższej tabeli wymieniono reguły sprawdzania poprawności wiersza transakcji, pod kątem których szczegóły wiersza transakcji detalicznych są sprawdzane przed przekazem wspomnianych transakcji do księgowania zestawienia.

| Reguła | Opis |
|-------|-------------|
| Kod kreskowy | Ta reguła sprawdza, czy wszystkie kody kreskowe używane w wierszach transakcji istnieją w bazie danych. |
| Wiersze opłat | Ta reguła sprawdza, czy suma obliczonej kwoty i kwoty zwolnionej z podatku z wierszy opłat jest równa pierwotnej obliczonej kwocie. |
| Zwroty towarów przekazanych za pośrednictwem karty upominkowej | Ta reguła sprawdza. czy transakcja nie obejmuje zwrotów towarów przekazanych za pośrednictwem kart upominkowych. |
| Wariant towaru | Ta reguła sprawdza, czy wszystkie towary i wszystkie warianty używane w wierszach transakcji istnieją w bazie danych. |
| Rabat wiersza | Ta reguła sprawdza, czy kwota rabatu w wierszu odpowiada sumie transakcji rabatu. |
| Podatek dla wiersza | Ta reguła sprawdza, czy kwota podatku w wierszu odpowiada sumie transakcji podatkowych. |
| Cena ujemna | Ta reguła sprawdza, czy w wierszach transakcji nie są używane ceny ujemne. |
| Kontrolowany numer seryjny | Ta reguła sprawdza, czy w wierszu transakcji dla towarów kontrolowanych przez numer seryjny znajduje się numer seryjny. |
| Wymiar numeru seryjnego | Ta reguła sprawdza, czy w przypadku, gdy wymiar numeru seryjnego towaru jest nieaktywny, nie został podany numer seryjny. |
| Sprzeczność znaku | Ta reguła sprawdza, czy znaki przy ilości i kwocie netto jest taki sam we wszystkich wierszach transakcji. |
| Zwolnienie z podatku | Ta reguła sprawdza, czy suma ceny towaru z wiersza i kwoty zwolnionej z podatku jest równa pierwotnej cenie. |
| Przypisanie grupy podatków | Ta reguła sprawdza, czy połączenie grupy podatków sprzedaży i grupy podatków towaru generuje prawidłowe przecięcie podatkowe. |
| Konwersja jednostki miary | Ta reguła sprawdza, czy jednostka miary wszystkich wierszy ma prawidłową konwersję na jednostkę miary zapasów. |

## <a name="enable-the-store-transaction-validation-process"></a>Włącz proces sprawdzania poprawności transakcji sklepu

Skonfiguruj cykliczne uruchamianie procesu wsadowego **Sprawdź poprawność transakcji w sklepie** w centrali Commerce (**Retail i Commerce \> Retail i Commerce — składniki IT \> Księgowanie w punkcie sprzedaży**). Zadanie wsadowe jest planowane na podstawie hierarchii organizacyjnej sklepu. Zaleca się, aby ten proces wsadowy był uruchamiany z tą samą częstotliwością, co zadania wsadowe: **Zadanie ściągania** i **Obliczanie zestawienia transakcji**.

## <a name="results-of-the-validation-process"></a>Wyniki procesu sprawdzania poprawności

Wyniki procesu wsadowego **Sprawdź poprawność transakcji w sklepie** można wyświetlić dla każdej transakcji sklepu sieci sprzedaży. Pole **Stan weryfikacji** w rekordzie transakcji ma wartość **Powodzenie**, **Błąd** lub **Brak**. Pole **Godzina ostatniej weryfikacji** zawiera datę ostatniego uruchomienia procesu sprawdzania poprawności.

W poniższej tabeli opisano poszczególne stany weryfikacji.

| Stan weryfikacji | Opis |
|-------------------|-------------|
| Powodzenie | Uzyskano pomyślny wynik kontroli wszystkich reguł sprawdzania poprawności. |
| Błąd | Włączona reguła sprawdzania poprawności zidentyfikowała błąd. Więcej szczegółów dotyczących błędu można wyświetlić, wybierając **Błędy weryfikacji** w okienku akcji. |
| Brak | Typ transakcji nie wymaga stosowania reguł sprawdzania poprawności. |

![Na stronie transakcji sklepu jest wyświetlane pole Stan weryfikacji i przycisk Błędy weryfikacji.](./media/valid-checker-validation-status-errors.png)

Tylko transakcje ze stanem weryfikacji **Powodzenie** zostaną pobrane do zestawień transakcyjnych. Aby wyświetlić transakcje ze stanem **Błąd**, przejrzyj kafelek **Weryfikacje transakcji kasowych zakończone niepowodzeniem** w obszarze roboczym **Finanse sklepu**.

![Kafelki w obszarze roboczym Finanse sklepu.](./media/valid-checker-cash-carry-validation-failures.png)

Aby uzyskać więcej informacji na temat rozwiązywania błędów weryfikacji transakcji kasowych zawiera temat [Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką](edit-cash-trans.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

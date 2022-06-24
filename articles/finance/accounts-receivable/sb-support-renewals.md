---
title: Obsługa i odnowienia
description: W tym artykule wyjaśniono, jak tworzyć harmonogram fakturowania towarów, a także tworzyć procedury obsługi i odnowienia zamówień sprzedaży.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: b40e0136883d909755480a3ce101627297bd9ffb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896529"
---
# <a name="support-and-renewals"></a>Obsługa i odnowienia 

W tym artykule opisano sposób wprowadzania pozycji pomocy technicznej lub odnowienia towarów podczas wprowadzania zamówień sprzedaży. Te elementy są używane do obliczania kwoty opłaty dla oryginalnej umowy pomocy technicznej i/lub kwoty odnowienia używanej podczas tworzenia harmonogramu fakturowania w ramach fakturowania subskrypcji. Na przykład firma sprzedaje serwer odbiorcy i oferuje subskrypcję kopii zapasowej danych dla pierwszego roku, a użytkownik ma możliwość odnowienia tej subskrypcji co roku. Element *pomocy technicznej jest* subskrypcją pierwszego roku, *a element odnowienia* jest odnowieniem dla każdego sukcesywnego roku.

Możesz wprowadzić informacje dotyczące umowy pomocy technicznej, umowy przedłużenia lub obu tych umów. Po wprowadzeniu informacji umowy pomocy technicznej do zamówienia sprzedaży jest dodawany tylko element pomocy technicznej. Podczas wprowadzania informacji o umowie przedłużenia element odnowienia jest używany do tworzenia harmonogramu fakturowania.

## <a name="support-and-renewal-setup"></a>Konfiguracja wsparcia i odnawiania

Na stronie **Poziomy pomocy technicznej i odnowienia** można skonfigurować różne poziomy pomocy technicznej dotyczącej elementów pomocy technicznej i odnowienia. Obsługa lub odnowienie może stanowić procent oryginalnej kwoty towaru lub może być kwotą standardową.

Domyślne poziomy wsparcia można wybrać na stronie **Parametry fakturowania umowy cyklicznej**.

Na przykład firma może oferować następujące poziomy pomocy technicznej i odnowienia.

| Poziom pomocy technicznej | Procent obsługi | Procent odnowienia |
|---|---|---|
| Nieograniczone | 40% | 30% |
| Złoto | 25% | 18% |
| Srebro | 20% | 18% |
| Brąz | 15% | 10% |

Aby utworzyć poziom wsparcia lub odnowienia, wykonaj poniższe kroki.

1. Na stronie **Poziomy pomocy technicznej i odnowienia** wybierz pozycję **Nowy**.
2. W polu **Poziom wsparcia** wprowadź unikatową nazwę.
3. W polu **Opis wprowadź** opis.
4. W polu **Metoda obliczania Pomoc** techniczna wybierz metodę obliczania pomocy technicznej. W przypadku wybrania opcji **Procent** wprowadź wartość procentową pomocy technicznej w **polu Procent pomocy technicznej**.
5. W polu **Metoda obliczania odnowienia** techniczna wybierz metodę obliczania odnowienia. W przypadku wybrania opcji **Procent** wprowadź wartość procentową odnowy w **polu Procent odnowy**.
6. Wybierz opcję **Zapisz**.

### <a name="fields"></a>Pola

Strona **Poziomy pomocy technicznej i odnowienia** zawiera następujące pola.

| Pole | Opis |
|---|---|
| Poziom pomocy technicznej | Unikatowy identyfikator poziomu pomocy technicznej lub odnowienia (na przykład **Złota** lub **Srebrna**). |
| Opis | Opis poziomu pomocy technicznej lub odnowienia. |
| Metoda obliczania obsługi | Wybierz metodę obliczania pomocy technicznej dla poziomu: **Procent** lub **Kwota standardowa**. |
| Procent obsługi | Jeśli jako metodę **obliczania pomocy** technicznej wybrano wartość Procent, określ wartość procentową używaną do obliczania ceny elementu pomocy technicznej. Jeśli jako metodę obliczania wybrano opcję **Kwota standardowa**, kwota jest określana podczas tworzenia transakcji. |
| Metoda obliczania odnowienia | Wybierz metodę obliczania odnowy dla poziomu: **Procent** lub **Kwota standardowa**. |
| Procent odnowienia | Jeśli jako metodę **obliczania odnowy** technicznej wybrano wartość Procent, określ wartość procentową używaną do obliczania ceny elementu odnowy. Jeśli jako metodę obliczania wybrano opcję **Kwota standardowa**, kwota jest określana podczas tworzenia transakcji. |

## <a name="support-and-renewal-process"></a>Proces obsługi i odnowienia

Funkcja wsparcia i odnawiania może stosować różne poziomy wsparcia do pozycji i aktualizować informacje o odnowieniu w rozliczeniach subskrypcji.

Przed rozpoczęciem korzystania z funkcji wsparcia i odnawiania należy wykonać następujące zadania.

1. Na stronie **Poziomy pomocy technicznej i odnowienia** utwórz co najmniej jeden poziom pomocy technicznej lub odnowienia.
2. Na stronie **Konfiguracja towaru** skojarz pozycję z pozycjami wsparcia i odnowienia. To zadanie jest wymagane tylko wtedy, gdy trzeba skonfigurować wartości domyślne dla elementów pomocy technicznej lub odnowienia.
3. Na stronie **Parametry fakturowania umowy cyklicznej** określ domyślne ustawienia pomocy technicznej i odnowienia nowych harmonogramów fakturowania.

Aby zastosować różne poziomy pomocy technicznej dla towarów i zaktualizować informacje o odnowienia, wykonaj następujące kroki.

1. Na stronie **Wszystkie zamówienia sprzedaży** utwórz zlecenie sprzedaży.
2. Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj pozycję.
3. Na karcie **Faktura** wybierz pozycję **Pomoc techniczna i odnowienie \> Dodaj obsługę i odnowienie**.
4. Na stronie **Proces pomocy technicznej i odnowienia** sekcja nagłówka jest aktualizowana ustawieniami ze strony **Parametry fakturowania umowy cyklicznej**. Te wartości dotyczą wszystkich pozycji pomocy technicznej i odnowienia. (Jeśli na przykład częstotliwość fakturowania jest ustawiona na wartość **Częstotliwość** roczna wszystkich wierszy sprzedaży utworzonych z towarem odnowienia jest automatycznie tworzona). Aby skojarzyć zamówienie sprzedaży z istniejącym harmonogramem fakturowania, wybierz wartość w polu **Numer harmonogramu fakturowania**.
5. Aby zmienić datę rozpoczęcia pomocy technicznej lub odnowienia, ustaw **opcję Zastąp datę rozpoczęcia** na **Tak**.
6. Aby dodać lub edytować element pomocy technicznej, **zaznacz pole wyboru Pomoc techniczna**, a następnie wprowadź pozycję pomocy technicznej w **polu Element pomocy technicznej**. Ta pozycja zostaje dodana do zamówienia sprzedaży.
7. Aby dodać lub edytować pozycję odnowienia, należy zaznaczyć pole wyboru **Odnowienie**, a następnie wprowadzić pozycję odnowienia w polu **Pozycja odnowienia**. Gdy zamówienie sprzedaży zostanie zafakturowane, zostanie utworzony harmonogram fakturowania, który zawiera towar.
8. Kliknij przycisk **OK**.
9. Na karcie **Utwórz** wybierz pozycję **Faktura**. Po zaksięgowaniu zamówienia sprzedaży zostanie utworzony harmonogram fakturowania. W szczegółach komunikatu zostanie wyświetlone powiadomienie z informacjami o harmonogramie fakturowania.
10. Na stronie listy **Wszystkie/Aktywne harmonogramy billingowe** wybierz numer harmonogramu billingowego, aby przejrzeć szczegóły harmonogramu billingowego na stronie **Harmonogramy billingowe**.
11. Na skróconej **karcie Wiersze harmonogramu fakturowania** wybierz pozycję **Pomoc techniczna i** odnowienie, aby przejrzeć szczegóły utworzonych wierszy.

> [!NOTE]
> Jeśli trzeba zmienić datę rozpoczęcia odnawiania dla linii harmonogramu rozliczeniowego, można edytować wartość **Data rozpoczęcia** dla tej linii na stronie **Harmonogramy rozliczeniowe**. Po otwarciu strony **Wyświetl szczegóły** fakturowania dla wiersza pole **Data rozpoczęcia fakturowania** jest aktualizowane nową datą. Wartość **daty zakończenia fakturowania** jest przeliczana na podstawie częstotliwości fakturowania. Datę rozpoczęcia odnowienia można zaktualizować tylko wtedy, gdy nie utworzono i nie zaksięgowano pierwszej faktury do odnowienia harmonogramu fakturowania. Po utworzeniu i zaksięgowaniu pierwszej faktury nie można edytować daty rozpoczęcia.

Proces pomocy technicznej i odnowienia jest dostępny tylko dla zamówienia sprzedaży. Podczas dodawania pomocy technicznej i odnowienia towarów do zamówienia sprzedaży można utworzyć nowy harmonogram fakturowania lub dodać nowy element odnowienia do istniejącego harmonogramu fakturowania.

## <a name="support-and-renewal-audit"></a>Inspekcja obsługi i odnowienia

Na stronie **Inspekcji pomocy technicznej i** odnowienia możesz przejrzeć szczegóły wierszy harmonogramu fakturowania utworzonych z elementu odnowienia w zamówieniu sprzedaży. Ta opcja jest dostępna, gdy pozycja wiersza harmonogramu rozliczeniowego jest pozycją odnowienia.

Aby edytować informacje dotyczące pomocy technicznej i odnowienia dla wiersza harmonogramu fakturowania, należy wykonać następujące kroki.

1. Na stronie **Wszystkie harmonogramy fakturowania** wybierz numer harmonogramu billingowego.
2. W sekcji **Wiersze harmonogramu fakturowania** zaznacz wiersz, a następnie wybierz pozycję **Obsługa i odnowienie**.
3. Przejrzyj wszystkie informacje dotyczące elementu pomocy technicznej lub odnowienia.
4. Wprowadź wymagane zmiany na poziomie pomocy technicznej albo procent lub kwotę odnowienia, a następnie wprowadź wartość w polu **Przyczyna zmiany**.
5. Wybierz **Proces**.

### <a name="fields"></a>Pola

Strona **Inspekcja obsługi i odnowienia** zawiera następujące pola.

| Pole | Opis |
|-------|-------------|
| Numer towaru | Numer pozycji dla wiersza harmonogramu rozliczeń. |
| Nazwa produktu | Nazwa produktu. |
| Poziom planu obsługi | Wyświetlenie lub zmiana poziomu wsparcia dla pozycji odnowienia. |
| Procent odnowienia | Umożliwia wprowadzenie procentu odnowienia używanego podczas obliczania ceny jednostkowej dla towaru odnowienia w harmonogramie fakturowania. |
| Kwota odnowienia | Umożliwia wprowadzenie ilości odnowienia używanego podczas obliczania ceny jednostkowej dla towaru odnowienia w harmonogramie fakturowania. |
| Przyczyna wprowadzenia zmiany | Wprowadź przyczynę zmiany informacji pomocy technicznej i odnowienia. Musisz podać przyczynę, gdy zmieniasz **wartość procentową odnowienia**, **kwotę odnowienia** lub **wartość poziomu planu pomocy technicznej**. |
| Oryginalna pozycja sprzedawana | Oryginalny numer pozycji sprzedaży z zamówienia sprzedaży. |
| Oryginalna kwota netto | Pierwotna kwota netto dla danej pozycji. |
| Oryginalny poziom obsługi | Pierwotny poziom wsparcia dla danego elementu. |
| Procent oryginalnego odnowienia | Pierwotna wartość procentowa odnowienia dla danej pozycji. |
| Oryginalna kwota odnowienia | Pierwotna kwota odnowienia dla danej pozycji. |
| **Siatka** | |
| Oryginalny poziom obsługi | Poprzedni poziom pomocy technicznej. |
| Procent oryginalnego odnowienia | Poprzedni procent odnowienia. |
| Oryginalna kwota odnowienia | Poprzednia kwota odnowienia. |
| Zmodyfikowane przez | Nazwa użytkownika, który dokonał zmiany. |
| Data i godzina modyfikacji | Data, kiedy nastąpiła zmiana. |
| Przyczyna | Przyczyna zmiany. |

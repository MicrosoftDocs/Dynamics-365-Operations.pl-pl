---
title: Zarządzanie rabatami — umowy
description: W tym temacie opisano, jak tworzyć umowy dotyczące zarządzania rabatami. Transakcje służą do kontrolowania różnych metod i podstaw do obliczania rabatów i tantiem. Obejmują one reguły wtrąceń i wkluczeń.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 7ba42df021eddccbae389321b38828c7a92e50c8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020514"
---
# <a name="rebate-management-deals"></a>Zarządzanie rabatami — umowy

[!include [banner](../includes/banner.md)]

Umowy dotyczące zarządzania rabatami służą do kontrolowania różnych metod i podstaw do obliczania rabatów i tantiem. Obejmują one reguły wtrąceń i wkluczeń. Dostępne są trzy typy umów zarządzania rabatami: rabaty dla odbiorcy, tantiemy dla odbiorcy i rabaty dostawcy. Wszystkie trzy typy używają podobnych ustawień. Ten temat wskazuje na różnice tam, gdzie one istnieją.

## <a name="create-a-deal"></a>Tworzenie umowy

1. Przejdź do oferty **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Wszystkie umowy zarządzania rabatami**. Na stronie listy **Wszystkie umowy zarządzania rabatami** można tworzyć transakcje wszystkich trzech typów i pracować z nimi.

    Alternatywnie wykonaj jeden z poniższych kroków. W każdym przypadku wyświetlana strona listy zawiera wszystkie ustawienia, które zawiera strona listy **Wszystkie umowy zarządzania rabatami**, ale jej filtrowanie pozwala wyświetlić tylko umowy jednego typu.

    - Przejdź do **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Umowy rabatów klienta**, aby stworzyć umowę rabatu klienta.
    - Przejdź do **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Umowy tantiem klienta**, aby stworzyć umowę tantiem klienta.
    - Przejdź do **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Umowy rabatów dostawcy**, aby stworzyć umowę rabatu dostawcy.

1. W okienku akcji wybierz opcję **Nowy**.
1. W oknie dialogowym **Utwórz nową umowę** ustaw następujące pola:

    - **Umowa w zakresie zarządzania rabatami** – Jeśli [ustawiono sekwencję numerów](rebate-management-parameters.md) dla umów rabatowych, w tym polu jest automatycznie ustawiany unikatowy, wygenerowany przez system identyfikator. W przeciwnym razie wprowadź unikalny identyfikator.
    - **Opis** – wprowadź opis umowy.
    - **Moduł** — umożliwia wybór typu partnera, do których odnosi się umowa (*Klient* lub *Dostawca*). W zależności od strony, od której zacząłeś, to pole może zostać ustawione automatycznie na podstawie wybranego typu umowy. W tym przypadku pole jest tylko do odczytu.
    - **Typ** — umożliwia wybranie typu umowy (*Rabat* lub *Tantiemy*). W zależności od strony, od której zacząłeś, to pole może zostać ustawione automatycznie na podstawie wybranego typu umowy. W tym przypadku pole jest tylko do odczytu.
    - **Uzgodnij do** — umożliwia wybór sposobu obliczania i uzgadniania umowy:

        - *Umowa* — jeden rabat powinien zostać przetworzony w przypadku wszystkich rabatów i potrąceń w ramach umowy.
        - *Wiersz* — rabaty powinny być przetwarzane dla każdego wiersza umowy.

    - **Profil księgowania** — umożliwia wybór [profilu księgowania](rebate-management-posting.md), który będzie stosowana dla transakcji, których dotyczy umowa. Ta opcja jest dostępna tylko w przypadku, gdy w polu **Uzgodnij do** jest wartość *Umowa*. Jeśli jest ustawiona wartość *Wiersz*, profil zostanie przypisany później do każdego wiersza, który zostanie przypisany do umowy.
    - **Profil księgowania do zagwarantowania** — umożliwia wybór [profilu księgowania](rebate-management-posting.md), który będzie stosowana dla zagwarantowanych transakcji. Profile księgowania są wymagane dla transakcji gwarancji tylko wtedy, gdy gwarancja dotyczy tantiem. W przeciwnym razie chociaż profil księgowania nie jest wymagany, to jeśli profil księgowania nie jest określony, podczas księgowania poręczenia jest wyświetlany błąd. Ta opcja jest dostępna tylko w przypadku, gdy w polu **Typ** jest wartość *Tantiemy*. 
    - **Wynik rabatu** — Umożliwia wybór sposobu wypłaty rabatu lub tantiem:

        - *Finanse* — generowanie bezpłatnej faktury korygowej lub noty uznaniowej rozrachunków z dostawcami, aby środki pieniężne można było wypłacić lub odbierać później. Należy zauważyć, że ustanowienia **mogą** być stosowane w przypadku rabatów, w przypadku których jest wybrana ta opcja. Ta opcja jest jedyną dostępną w przypadku, gdy w polu **Typ** jest wartość *Tantiemy*.
        - *Towar* — generuje zamówienie sprzedaży dla towarów zgodnie z konfiguracją umowy. W tym zamówieniu sprzedaży cena 0 (zero) jest przypisywana do każdego towaru. Należy zauważyć, że ustanowienia **nie mogą** być stosowane w przypadku rabatów, w przypadku których jest wybrana ta opcja.

    - **Waluta rabatu** — umożliwia wybór waluty, która będzie walutą używaną przy zapłacie rabatu, potrącenia lub tantiem.
    - **Notatki dokumentu** — w razie potrzeby wprowadź uwagi dotyczące umowy.
    - **Gwarancja zbiorcza** – Dla tej opcji można ustawić wartość *Tak* tylko wtedy, gdy w polu **Typ** jest ustawiona wartość *Tantiemy*. Ta opcja wpływa na obliczanie płatności potrąceń gwarantowanych. Oto przykład:

        - Gwarancją umowy jest sprzedaż wartości, która doprowadzi do płatności w $10 000 kwartału.
        - Organizacja sprzedająca towary sprzedaje wartość, która powoduje potrącenie płatności $12 000 w 1. kwartale. W wyniku tego $12 000 jest tantiemy, które są płacone, pomniejszone o $10 000.
        - Jeśli w opcji **Kumuluj gwarancję** jest ustawiona wartość *Tak*, dodatkowe $2000 tantiemy zapłacone w 1 kwartale dotyczą 2. kwartału. Dlatego też odbiorca jest gwarantowany $8 000 ($10 000 pomniejszona o $2 000 płatności).
        - W 2 kwartale rejestruje się sprzedaż, która wywołuje $5 000 tantiemy.
        - System identyfikuje płatność tantiem $3 000 ($8 000 pomniejszona o $5 000 tantiemy).
        - Jeśli w opcji **Kumuluj poręczenia** ustawiono wartość *Nie*, pełne $10000 będą gwarantowane co kwartał. Ta gwarancja odpowiada sugerowanej płatności tantiem $5000 w 2 kwartale ($10000 pomniejszona o $5000 zapłaconych tantiem).

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć umowę.

Ta procedura tworzy poziom nagłówka nowej umowy. Następnie zostaną dodanie wierszy do umowy.

## <a name="add-lines-to-a-deal"></a>Dodawanie wierszy do umowy

Po utworzeniu umowy zgodnie z opisem w poprzedniej sekcji można ją otworzyć ze strony listy. Następnie można dodawać wiersze w celu zidentyfikowania odbiorców lub dostawców, towarów, ram czasowych, podstawy i metod obliczania dla umowy. Umowa może mieć jeden lub wiele wierszy. Jeśli umowa ma wiele wierszy, na ogół są one tego samego typu lub są z nimi skojarzone te same parametry. Dopóki nie dodasz wierszy do umowy, ta umowa w rzeczywistości nie zrobi nic.

1. Otwórz odpowiednią stronę z listą umów rabatowych, zgodnie z opisem w poprzedniej sekcji.
1. Znajdź i otwórz ofertę, z którą chcesz pracować.
1. Na skróconej karcie **Zarządzanie rabatami** wybierz jeden z następujących przycisków, aby dodać wiersz umowy do siatki:

    - **Dodaj wiersz** — dodaj nowy, pusty wiersz umowy.
    - **Kopiuj wiersz** – Jeśli istniejący wiersz umowy przypomina wiersz umowy, który chcesz dodać, możesz wybrać ten przycisk, aby skopiować jego kopię. Nowy wiersz umowy będzie zawierał wszystkie ustawienia z powiązanych szczegółów zarządzania rabatami. Następnie możesz edytować ustawienia. Na przykład zwykle aktualizowane są relacje towaru i procent rabatu.

1. Dla nowego wiersza umowy należy określić następujące pola:

    - **Numer zarządzania rabatami** – Jeśli [ustawiono sekwencję numerów](rebate-management-parameters.md) dla Numerów zarządzania rabatami, w tym polu jest automatycznie ustawiany unikatowy, wygenerowany przez system identyfikator. W przeciwnym razie wprowadź unikalny identyfikator.
    - **Typ** — typ umowy, do których odnosi się wiersz (*Rabat* lub *Tantiemy*). Ta wartość jest kopiowana z nagłówka i nie można jej zmienić.
    - **Opis** – wprowadź opis wiersza umowy.
    - **Firma** — umożliwia wybór firmy, do których odnosi się wiersz umowy. Podczas przetwarzania użytkownicy mogą przetwarzać tylko wiersze umowy przypisane do aktualnie wykorzystywanej firmy. Strona listy **Umów rabatowych dla odbiorcy** umożliwia wyświetlanie informacji o wielu firmach w oparciu o zabezpieczenia dostępu użytkownika. Można jednak edytować i przetwarzać rabaty tylko dla aktualnie wykorzystywanej firmy.
    - **Kod konta** — umożliwia wybór zakresu odbiorców lub dostawców, których dotyczy wiersz umowy:

        - *Tabela* — wiersz umowy dotyczy określonego odbiorcy lub dostawcy.
        - *Grupa* — wiersz umowy dotyczy grupy odbiorców lub dostawców. Aby uzyskać więcej informacji o tworzeniu grup składników kosztów pośrednich, zobacz [Grupy zarządzania rabatami](rebate-management-groups.md).
        - *Wszystkie* — wiersz umowy dotyczy wszystkich odbiorców lub dostawców.

    - **Relacje konta** – Jeśli w polu Kod konta wybrano opcję *Tabela* lub **Grupa**, wybierz klienta lub dostawcę, którego dotyczy transakcja. W przypadku wybrania opcji *Grupa* zaznacz grupę odbiorców lub dostawców. W przypadku wybrania *Wszystko* pole to nie jest dostępne.
    - **Kod towaru** — umożliwia wybór zakresu towarów, których dotyczy wiersz umowy:

        - *Tabela* — wiersz umowy dotyczy określonego towaru.
        - *Grupa* — wiersz umowy dotyczy grupy towarów. Aby uzyskać więcej informacji o tworzeniu grup składników kosztów pośrednich, zobacz [Grupy zarządzania rabatami](rebate-management-groups.md).
        - *Wszyscy* — Wiersz umowy dotyczy wszystkich pozycji.

    - **Relacje towarów** – Jeśli w polu Kod konta wybrano opcję *Tabela* lub **Kod towaru**, wybierz towar, którego dotyczy transakcja. W przypadku wybrania opcji *Grupa* należy zaznaczyć grupę towarów. W przypadku wybrania *Wszystko* pole to nie jest dostępne.
    - **(Parametry zarządzania zapasami)** — w pozostałych polach wiersza umowy należy określić wartości parametrów zarządzania zapasami, które będą używane do definiowania towarów uwzględnionych w układzie (takich jak rozmiar towaru, kolor, styl, witryna i magazyn). Aby dodać lub usunąć wymiary, wybierz pozycję **Wyświetl wymiary** w okienku akcji.

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Aby dodatkowo ograniczyć zestaw towarów, których dotyczy wiersz umowy, zaznacz wiersz, a następnie na skróconej karcie **Zarządzanie rabatami** wybierz opcję **Filtruj**, aby otworzyć standardowe okno dialogowe **Zapytanie**.
1. W przypadku każdego dodajesz wiersza umowy skonfiguruj szczegóły obliczeń i inne szczegóły na skróconej karcie **Zarządzanie rabatami**, zgodnie z opisem w następnej sekcji.

## <a name="add-rebate-management-details-to-a-deal-line"></a>Dodawanie szczegółów zarządzania rabatami do wiersza umowy

Dla każdego wiersza umowy należy skonfigurować szczegóły na skróconej karcie **Zarządzanie rabatami**. Na skróconej karcie **Zarządzanie rabatami** wybierz wiersz umowy. Następnie ustaw wartości dla tego wiersza umowy, korzystając z różnych kart na skróconej karcie **Szczegóły zarządzania rabatami**. W poniższych podsekcjach opisano sposób korzystania z poszczególnych kart.

### <a name="settings-on-the-general-tab"></a>Ustawienia na karcie Ogólne

Karta **Ogólne** w skróconej karcie **Szczegóły zarządzania rabatami** umożliwia skonfigurowanie metody i podstawy obliczania dla wybranego wiersza umowy. Ta konfiguracja określa, czy wymagany jest minimalny zakup, profile księgowania skojarzone z wierszem umowy oraz szczegóły obliczeń. W poniższej tabeli przedstawiono dostępne pola.

| Pole | opis |
|---|---|
| Metoda obliczania | Umożliwia wybór metody, która będzie stosowana, gdy wybrany wiersz umowy zostanie połączony z innymi wierszami umowy (*Zdjęte*, *Skumulowane*, *Kroczące* lub *Razem*). Wartość tego pola może mieć wpływ na wynik obliczeń rabatu. Aby uzyskać pełny opis każdej metody i przykłady, które pokazują, jak wpływa ona na obliczanie rabatów, zobacz sekcję [Metody obliczania wierszy umowy](#calc-methods) w dalszej części tego tematu. |
| Podstawa | Umożliwia określenie, czy rabat jest stosowany na podstawie ilości (to jest łącznej liczby jednostek kupowanych lub sprzedawanych) lub wartości (tj. łącznej ceny towarów, które są kupowane lub sprzedawane). |
| Typ transakcji | <p>Umożliwia wybór punktu procesu, na którym ma nastąpić obliczenie:</p><ul><li>*Zamówienie* — jako podstawy obliczeń należy użyć zamówione ilości lub wartości.</li><li>*Dostarczone* — jako podstawy obliczeń należy użyć dostarczone ilości lub wartości.</li><li>*Faktura* — jako podstawy obliczeń należy użyć zafakturowane ilości lub wartości.</li></ul> |
| Jednostka | Jeśli została wybrana opcja *Ilość* w polu **Podstawa** zoależy wybrać jednostkę, w przypadku gdy ta ilość musi zostać określona. |
| Minimalna kwota | Wprowadź minimalną kwotę, jaka musi zostać wypłacona za okres. Można wprowadzić wartość ujemną, aby zezwolić na ujemne kwoty rabatów, jeśli faktury korygowe przekraczają sprzedaż w tym okresie. |
| Zasada redukcji rabatów | Wybierz [zasadę redukcji rabatu](rebate-reduction-principle.md), która jest stosowana do wiersza. |
| Numer wariantu | Jeśli wiersz umowy dotyczy towaru z wariantami, należy wybrać wariant, do których odnosi się wiersz umowy. |
| Podstawy rabtów dostawcy | <p>To pole jest wyświetlane tylko w przypadku rabatów dostawcy (to jest transakcji, w których w polu **Modułu** ustawiono wartość *Dostawca*). Wybierz podstawę rabatu dostawcy:</p><ul><li>*Zamówienie zakupu* — rabat obierania przez dostawcę jest oparty na ilości lub wartości z zamówienia zakupu.</li><li>*Zamówienie sprzedaży* — dostawca otrzymuje rabat dopiero po sprzedaniu towarów. Rabat jest oparty na ilości lub wartości na zamówieniu sprzedaży.</li></ul> |
| Podstawa ceny | <p>To pole jest wyświetlane tylko w przypadku rabatów dostawcy (to jest transakcji, w których w polu **Modułu** ustawiono wartość *Dostawca*). W przypadku wybrania opcji *Zamówienie sprzedaży* w polu **Podstawa rabatu dostawcy** zaznacz odpowiednie podstawy ceny:</p><ul><li><p>*FIFO* — Aby można było obliczyć rabat, należy uruchomić zadanie okresowe **Obliczanie ceny zakupu FIFO**. (Aby uruchomić zadanie, przejdź do **Zarządzanie rabatami \> Zadania okresowe \> Obliczania ceny zakupu FIFO**). Do obliczenia wartości sprzedawanego zapasu zostanie użyta reguła FIFO. Wartość ta zostanie następnie użyta do obliczenia rabatów dostawcy. Oto przykład:</p><ul><li>**Sprzedane zapasy**: 1000 jednostek po $3,00 = $3000</li><li>**Bieżąca cena zakupu na podstawie FIFO:** $2,00</li><li>**Obliczanie pracy:** *liczba sprzedanych jednostek* × *bieżącej ceny zakupu* = 1000 × $2,00 = $2000</li></ul></li><li><p>*Ostatnia cena zakupu* — wartość z ostatniej transakcji zakupu będzie używana do obliczenia rabatów dostawcy. Oto przykład:</p><ul><li>**Sprzedane zapasy**: 1000 jednostek po $3,00 = $3000</li><li>**Ostatnia cena zakupu:** $2,00</li><li>**Obliczanie pracy:** *liczba sprzedanych jednostek* × *Ostatnia cena zakupu* = 1000 × $2,00 = $2000</li></ul></li><li><p>*Średnia cena zakupu* – Średnia ważona z ostatnich *X* miesięcy będzie używana do obliczania rabatów dostawcy. W przypadku wybrania tej opcji należy w polu **Liczba miesięcy** wprowadzić liczbę miesięcy (która jest dostępna tylko wtedy, gdy w polu **Podstawa ceny** jest ustawiona wartość *Średnia cena zakupu*). Oto przykład:</p><ul><li>**Sprzedane zapasy**: 1000 jednostek po $3,00 = $3000</li><li>**Średnia cena zakupu:** $2,00</li><li>**Obliczanie pracy:** *liczba sprzedanych jednostek* × *Średnia cena zakupu* = 1000 × $2,00 = $2000</li></ul></li><li><p>*Cena sprzedaży* — cena sprzedaży będzie używana do obliczenia rabatów dostawcy. Oto przykład:</p><ul><li>**Sprzedane zapasy**: 1000 jednostek po $3,00 = $3000</li><li>**Średnia cena zakupu:** $2,00</li><li>**Obliczanie pracy:** *liczba sprzedanych jednostek* × *Cena zakupu* = 1000 × $3,00 = $3000</li></ul></li></ul> |
| Ilość miesięcy | To pole jest wyświetlane tylko w przypadku rabatów dostawcy (to jest transakcji, w których w polu **Modułu** ustawiono wartość *Dostawca*). Jeśli w polu **Podstawa ceny** wybrano wartość *Średnia cena zakupu*, należy wprowadzić liczbę miesięcy, która ma zostać użyta. |
| Profil księgowania | Wybierz [profil księgowania](rebate-management-posting.md) dla wybranego wiersza umowy. Ten profil jest używany tylko wtedy, gdy w polu **Uzgodnij do** w nagłówku umowy jest ustawiona wartość *Wiersz*. Jeśli w polu **Uzgodnij do** jest ustawiona wartość *Umowy*, zawsze jest używany profil księgowania ustawiony w nagłówku umowy. Jeśli żaden profil księgowania nie jest ustawiony w wierszu umowy, używany jest profil księgowania ustawiony w nagłówku umowy. |
| Profil księgowania dla gwarancji | To pole działa podobnie do pola **Profil księgowania**, ale dotyczy tylko tantiem. |
| Typ płatności | Typ płatności dla profilu księgowania wybranego do umowy. |
| Podatek wliczony | Umożliwia wybór, czy transakcja jest podatkowa. Włączenie podatku ma zastosowanie tylko w przypadku, gdy w polu **Podstawa** ustawiono *Wartość*. Kwota faktury zostanie użyta jako kwota podatku wliczona w podatek. Jeśli rabat jest oparty na wartości procentowej, system pomnoży procent rabatu przez kwotę uwzględniającą podatek. Należy zwrócić uwagę, że w obliczeniach jest używana wartość podatku z wiersza umowy. |
| Uwzględnij faktury korygujące | <p>Ustaw dla tej opcji wartość *Tak*, aby uwzględnić faktury korygowe w obliczeniach rabatów.</p><p>W przypadku ustawienia tej opcji na wartość *Tak*, efekt będzie się zmieniał w zależności od wartości pola **Typ transakcji**:</p><ul><li>Jeśli w polu **Typ transakcji** została ustawiona wartość *Faktura*, w obliczeniach będą wejmowane faktury korygowane. Ta konfiguracja jest zazwyczaj konfiguracją.</li><li>Jeśli w polu **Typ transakcji** jest ustawiona wartość *Zamówienie*, obliczenia będą się składać zarówno z zamówień sprzedaży, które mają wartości ujemne, jak i otwartych zamówień zwrotu.</li></ul> |
| Kwota rabatu | Ustaw tę opcję na wartość *Tak*, aby opierać się na kwocie rabatu pozycji lub pozycji w przypadkach, gdy są podawane rabaty wiersza umowy. |
| Tylko faktury zapłacone | Ustaw tę opcję na wartość *Tak*, jeśli obliczenia powinny uwzględniać tylko w pełni zapłacone faktury. (Innymi słowy, rabaty nie zostaną obliczone dla częściowo zapłaconych faktur) Ta opcja jest dostępna tylko wtedy, gdy w polu **Typ transakcji** jest ustawiona wartość *Faktura*. |
| Dołączenie dowolnego tekstu | Ustaw dla tej opcji wartość *Tak*, aby uwzględnić faktury z dowolnym tekstem w obliczeniach. Faktury tekstowe mogą być uwzględniane tylko w przypadku wierszy umowy, w których w polu **Kod pozycji** ustawiono wartość *Wszystkie*. |
| Uwzględnij rabat rozliczeniowy | Ustaw dla tej opcji wartość *Tak*, aby zredukować rabat o pierwszy rabat rozliczeniowy. Zakłada się, że organizacja pobrała pierwszy rabat rozliczenia. Ustaw tę opcję na wartość *Nie*, aby włączyć później włączenie rabatu rozliczeniowego. |
| Notatki dotyczące dokumentu | Służy do wprowadzania uwag, które powinny być używane jako tekst transakcji w wierszach arkusza transakcji rabatowych. |

### <a name="settings-on-the-dates-tab"></a>Ustawienia na karcie daty

Ustawienia na karcie **Daty** w skróconej karcie **Szczegóły zarządzania rabatami** określają częstotliwość i czas wykonywania obliczeń określonych na karcie **Ogólne**. Określają one sposób wykonywania obliczeń w czasie przetwarzania.

Ta karta umożliwia określanie zakresu dat, dla których obowiązuje wybrany wiersz umowy, oraz częstotliwości obliczania. Można również określić, czy i kiedy ma być księgowana gwarancja.

Za pomocą przycisków na pasku narzędzi można dodawać produkty do siatki lub usuwać je z siatki. Jeśli istnieje wiele wierszy dat, prawidłowe zakresy dat nie mogą się nakładać. W przeciwnym razie przy próbie zapisania umowy zostanie wyświetlony komunikat o błędzie.

W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego wiersza daty.

| Pole | opis |
|---|---|
| Data rozpoczęcia | Służy do wprowadzania daty, do których odnosi się wiersz daty. Jeśli w nagłówku umowy określono daty „od” i „do”, będą one używane jako wartości domyślne dla każdego nowego wiersza daty. |
| Data zakończenia | Służy do wprowadzania ostatniej daty, do których odnosi się wiersz daty. Jeśli w nagłówku umowy określono daty „od” i „do”, będą one używane jako wartości domyślne dla każdego nowego wiersza daty. |
| Na | Umożliwia określenie, jak często ma być obliczany wiersz umowy. W tym polu należy wprowadzić liczbę całkowitą, a następnie wybrać jednostkę w polu **Kumuluj według**. Na przykład aby obliczyć wartość co drugi tydzień, w polu **Na** ustaw wartość *2*, a w polu **Kumuluj według** ustaw wartość *Tygodnie*. |
| Kumuluj według | Wybierz jednostkę, która dotyczy ustawienia **Na**. Wybierz okres użytkowania, aby obliczyć wartość w całym *Okresie istnienia* wiersza umowy. Wybierz opcję *Niestandardowy okres*, aby wybrać okres zdefiniowany w księdze głównej. W tym przypadku należy także ustawić pole **Typ okresu**. |
| Typ okresu | Ta opcja jest dostępna tylko w przypadku, gdy w polu **Kumuluj według** jest wartość *Okres niestandardowy*. Wartości dostępne do wyboru pochodzą z typów okresów zdefiniowanych w księdze głównej. |
| Pierwszy dzień tygodnia | Określ sposób, w jaki tygodnie są identyfikowane dla okresu. Ta opcja jest dostępna tylko w przypadku, gdy w polu **Kumuluj do** jest wartość *Tygodnie*. |
| Odbieranie na | Określ, jak często mogą być żądane kwoty rabatowe dla wiersza umowy. W tym polu należy wprowadzić liczbę całkowitą, a następnie wybrać jednostkę w polu **Odbierz do**. |
| odbieranie do | Wybierz jednostkę, która dotyczy ustawienia **Odbieranie na**. Wybierz *okres istnienia*, aby zezwolić na roszczenia tylko raz w całym okresie istnienia wiersza umowy. Wybierz opcję *Niestandardowy okres*, aby wybrać okres zdefiniowany w księdze głównej. W tym przypadku należy także ustawić pole **Typ okresu odbioru**. |
| Typ okresu odbioru | Ta opcja jest dostępna tylko w przypadku, gdy w polu **Odbiór do** jest wartość *Okres niestandardowy*. Wartości dostępne do wyboru pochodzą z typów okresów zdefiniowanych w księdze głównej. |
| Proces w trakcie księgowania | To pole wyboru należy zaznaczyć, jeśli wiersz roszczenia ma być przetwarzany w czasie księgowania. Ta opcja jest dostępna tylko w przypadku wierszy umowy, w których pole **Typ transakcji** na karcie **Ogólne** ma wartość *Dostarczone* lub *Faktura*. W przypadku rezerw warunki zostaną zaksięgowane po wygenerowaniu dokumentu dostawy lub faktury. |
| Gwarancja na | To pole dotyczy tylko umów na tantiemy. Określ, jak często mają być obliczane gwarancje tantiem w okresie zdefiniowanym przez ustawienie **Kumuluj według**. W tym polu należy wprowadzić czas płatności, a następnie wybrać jednostkę w polu **Zagwarantowana płątność**. |
| Gwarancja opłacona | <p>To pole dotyczy tylko umów na tantiemy. To pole działa w połączeniu z polem **Poręcznie na**, aby określić częstotliwość obliczania gwarancji. Należy wybrać jedną z następujących opcji:</p><ul><li><p>*Początek okresu* – Poręcznie zostanie zapłacone na początku okresu umowy zdefiniowanego dla wiersza daty. Pełna gwarancja jest przetwarzana jako pierwsza. Jako tantiemy jest księgowana tylko wartość tantiem przekraczaca kwotę gwarantowaną. Oto przykład:</p><ul><li>**Minimum gwarancji:** $10 000 przez dwa miesiące.</li><li>**Miesiąc 1:** $10 000 zaksięgowano jako poręcznie, a $0 zaksięgowano tantiemy.</li><li>**Miesiąc 2:** $2 000 zaksięgowano jako tantiemy, a $0 zaksięgowano jako poswiadczenia.</li><li>**Obliczanie pracy:** *pozostałe poświadczenia* – *zaksięgowane tantiemy* = $0 – $2000 = -$2000.</li></ul><p>Ponieważ płatność tantiem $2000 jest wymagana, arkusz jest tworzony dla $2000.</p><p>**Uwaga:** Poręczenie powinno zostać obliczone i zaksięgowane razem z potrąceniami za pierwszy okres.</p></li><li><p>*Koniec okresu* — poręczenie nie zostanie zapłacone do końca umowy dotyczącej potrąceń, zgodnie z wierszem daty. Oto przykład:</p><ul><li>**Minimum gwarancji:** $10 000 przez dwa miesiące.</li><li>**Miesiąc 1:** $5000 zaksięgowano jako tantiemy i utworzono arkusz.</li><li>**Miesiąc 2:** $7000 zaksięgowano jako tantiemy i utworzono arkusz.</li><li>**Obliczanie pracy:** ponieważ tantiemy przekraczają kwotę gwarancji, $0 jest księgowane w poręczeniach.</li></ul><p>**Uwaga:** Gwarancja powinna być obliczana i księgowana tylko razem z transakcją potrąceń i rabatów za ostatni okres.</p></li></ul> |
| Minimum gwarancji | To pole dotyczy tylko umów na tantiemy. Umożliwia wprowadzenie minimalnej kwoty gwarancji na tantiemy w walucie zdefiniowanej w nagłówku umowy. |

### <a name="settings-on-the-lines-tab"></a>Ustawienia na karcie Wierszy

Karta **Wiersze** w skróconej karcie **Szczegóły zarządzania rabatami** umożliwia skonfigurowanie obliczania wierszy dla wybranego wiersza umowy. Każdy wiersz obliczania ustala próg ilości lub wartości oraz powiązaną z nim kwotę lub pozycje wynagrodzenia. Pole **Podstawa** w polu **Ogólne** określa, czy każdy wiersz obliczania jest oparty na ilości czy wartości.

Za pomocą przycisków na pasku narzędzi można dodawać obliczenia do siatki lub usuwać je z siatki. Można mieć dowolną liczbę wierszy obliczeń. Jeśli jednak istnieje wiele wierszy obliczeń, ilości „do” i „od” nie mogą się nakładać.

W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego wiersza obliczeń.

| Pole | opis |
|---|---|
| Od ilości/wartości | Umożliwia wprowadzenie minimalnej ilości lub wartości, do których odnosi się wiersz obliczania. |
| Do ilości/wartości | Umożliwia wprowadzenie maksymalnej ilości lub wartości, do których odnosi się wiersz obliczania. |
| Zarządzanie rabatami — metoda | <p>To pole jest dostępne tylko w przypadku transakcji, w których w polu **danych wyjściowych rabatu** w nagłówku ustawiono wartość *Finansowe*. Umożliwia wybranie metody obliczania rabatów.</p><ul><li>*Stałe* — dla wiersza jest używana stała kwota ceny.</li><li>*Procent* — jest używany procent kwoty sprzedaży.</li><li>*Stawka* — jest używana stała kwota ceny na zamówienie.</li></ul><p>**Ważne:** Stanowczo zaleca się użycie tej samej metody dla każdego wiersza obliczania na karcie **Wiersze**. Jeśli wymagana jest nowa metoda, należy utworzyć nowy wiersz umowy. Należy pamiętać, że aby utworzyć nowy wiersz umowy na podstawie istniejącego wiersza umowy, można użyć przycisku **Kopiuj wiersz** na skróconej karcie **Zarządzanie rabatami**.</p><p>**Uwaga:** Jeśli w polu **Danych wyjściowych rabatu** jest ustawiona wartość *Towar*, to pole zawsze ma wartość *Stała*. Aby uzyskać więcej informacji na temat sposobu określania towarów, zobacz tekst, który następuje po tej tabeli. |
| Zarządzanie rabatami — kwota | To pole jest dostępne tylko w przypadku transakcji, w których w **Danych wyjściowych rabatu** w nagłówku ustawiono wartość *Finansowe*. Służy do wprowadzania kwoty, która ma zostać użyta do obliczenia rabatu na podstawie metody wybranej w polu **Metoda zarządzania rabatami**. |

Jak dano w poprzedniej tabeli, w przypadku transakcji, w których pole **Dane wyjściowe rabatu** w nagłówku ma wartość *Towar*, należy określić towary, które będą dostarczone dla każdego wiersza obliczenia na karcie **Wiersze**. Aby określić towary, należy wykonać następujące czynności.

1. Na karcie **Wiersze** utwórz wymagany wiersz obliczenia, jeśli nie istnieje, i wybierz go.
1. Jeśli umowa nie została zapisana od czasu utworzenia wiersza obliczania, wybierz opcję **Zapisz** w okienku akcji.
1. Na karcie **Wiersze** wybierz pozycję **Towary**.
1. Na stronie **Towary** użyj przycisków w okienku akcji, aby dodać towary do siatki lub w razie potrzeby usunąć towary. Dla każdego wiersza ustaw następujące pola:

    - **Numer towaru** — umożliwia wybór dostarczonego towaru
    - **(Inne wymiary)** — umożliwia określenie większej liczby wymiarów (np. konfiguracji towaru, rozmiaru, koloru, stylu, lokalizacji lub magazynu). Aby dodać lub usunąć dostępne wymiary, wybierz pozycję **Wyświetl wymiary** w okienku akcji.
    - **Ilość** — służy do wprowadzania ilości, która zostanie dostarczony po przekroczeniu progu wybranego wiersza obliczania.
    - **Jednostka** — umożliwia wybór jednostki, w przypadku gdy jest określona wartość **ilości**.
    - **Wiele** – Pole to jest powiązane z polem **Ilość**. Na przykład w wierszu towaru można ustawić pole **Ilość** na wartość *2* oraz pole **Wielokrotność** na wartość *100*. Jeśli łączna ilość zamówienia sprzedaży wynosi 150, dwa towary będą bezpłatne (dwa na 100).

### <a name="settings-on-the-inventory-dimensions-tab"></a>Ustawienia na karcie Wymiary magazynowe

Karta **Wymiary magazynowe** w skróconej karcie **Szczegóły zarządzania rabatami** zawiera wszystkie dostępne wartości wymiarów dla produktu określonego dla wybranego wiersza umowy. Zawiera ona wymiary, które nie są wyświetlane na skróconej **karcie Zarządzanie rabatami**. Wartości można edytować tylko dla wymiarów, które mają zastosowanie do wybranego produktu.

Aby dodać więcej wymiarów do siatki na skróconej karcie **Zarządzanie rabatami**, wybierz opcję **Wyświetl wymiary** w okienku akcji.

## <a name="calculation-methods-for-deal-lines"></a><a name="calc-methods"></a>Metody obliczania dla wierszy umowy

Po każdym skonfigurowaniu szczegółów jednego z wierszy umowy, jak opisano w poprzedniej sekcji, należy wybrać metodę obliczania dla tego wiersza. W tej sekcji opisano każdą z metod obliczania i przedstawiono przykłady, które pokazują, w jaki sposób poszczególne metody obliczają łączny rabat dla zamówień i wierszy umowy. W tych przykładach zamówienia i wiersze umowy są identyczne. Różnią się tylko metody obliczania.

### <a name="stepped-calculation-method"></a>Metoda obliczeń zajęta

Stosowana metoda obliczania jest obliczana krok po kroku, w którym każdy wiersz umowy stopniowo wpływa na rabat, dopóki nie zostanie osiągnięta ilość lub wartość sprzedaży. Kroki mogą być oparte na ilości lub wartości sprzedawanych towarów, zależnie od ustawienia pola **Podstawa** na karcie **Ogólne** w skróconej karcie **Zarządzanie rabatami**.

Na przykład wiersz umowy jest tak ustawiony, że w polu **Metoda obliczania** jest ustawiona wartość *Zdjęta*, a w polu **Podstawa** jest *Wartość*. Wiersze te zawierają następujące wiersze obliczeń dotyczące rabatów:

- **Wiersz A:** 10 procent do $1,000
- **Wiersz B:** 25 procent do $2,500

Jeśli wartość towarów, które zostały nabyte lub sprzedane, $2000 rabat w $350 jest obliczany w następujący sposób:

- **Rabat (A):** *próg (A)* × *procent (A)* = $1000 × 10 procent = $100
- **Rabat (B):** (*Wartość sprzedana* – *próg (A)*) × *procent (B)* = (2000 USD – $1000) × 25 procent = $250
- **Rabat ogółem:** *Rabat (A)* + *Rabat (B)* = $100 + $250 = $350

Jeśli w polu **Podstawa** zostanie ustawiona wartość *Ilość* zamiast *wartości*, metoda obliczania zostanie ustawiona w podobny sposób. Pierwszy krok jest używany dla określonej ilości do momentu osiągnięciu drugiego etapu. Drugi stopień jest następnie używany dla wszystkich ilości powyżej pierwszego stopnia, aż do osiągnięcia trzeciego stopnia. Następnie proces jest kontynuowany przez wszystkie kolejne kroki.

### <a name="cumulative-calculation-method"></a>Kumulacja metody obliczania

W metodzie obliczania skumulowanego rabat jest obliczany tylko za pomocą jednego wiersza obliczeń. Jeśli dla wiersza umowy dostępnych jest wiele wierszy obliczeń, dla całej ilości lub wartości jest używany wiersz obliczania najwyższej lub najwyższej ilości. Podobnie jak w przypadku innych metod obliczania, w celu określenia, czy do obliczania rabatów jest używana wartość sprzedaży, w metodzie kumulowania stosowane jest pole **Podstawa** na karcie **Ogólne** w skróconej karcie **Szczegóły zarządzania rabatami**.

Na przykład wiersz umowy jest tak ustawiony, że w polu **Metoda obliczania** jest ustawiona wartość *Kumulatywne*, a w polu **Podstawa** jest *Wartość*. Wiersze te zawierają następujące wiersze obliczeń dotyczące rabatów:

- **Wiersz A:** 10 procent do $1,000
- **Wiersz B:** 25 procent do $2,500

Jeśli wartość towarów, które zostały zakupione lub sprzedane, wynosi 2000 USD, do obliczenia wykorzystuje się tylko wiersz B. Otrzymany rabat w wysokości 500 USD jest obliczany w następujący sposób:

- **Rabat ogółem:** *wartość sprzedana* × *rabat (B)* = $2000 × 25% = $500

### <a name="rolling-calculation-method"></a>Metoda obliczeń kroczących

Metoda obliczania toczenia oblicza wszystkie możliwe wiersze obliczeń dla umowy. Jeśli istnieje wiele wierszy obliczeń i zostanie osiągniętych więcej niż jeden z nich, zostaną użyte wszystkie osiągnięte wiersze obliczeń, ale górne progi dotyczą każdej wartości procentowej. Podobnie jak w przypadku innych metod obliczania, w celu określenia, czy do obliczania rabatów jest używana wartość sprzedaży, w metodzie kroczącej stosowane jest pole **Podstawa** na karcie **Ogólne** w skróconej karcie **Szczegóły zarządzania rabatami**.

Na przykład wiersz umowy jest tak ustawiony, że w polu **Metoda obliczania** jest ustawiona wartość *krocząca*, a w polu **Podstawa** jest *Wartość*. Wiersze te zawierają następujące wiersze obliczeń dotyczące rabatów:

- **Wiersz A:** 10 procent do $1,000
- **Wiersz B:** 25 procent do $2,500

Jeśli wartość towarów, które zostały nabyte lub sprzedane, $2,000 rabat w $600 jest obliczany w następujący sposób:

- **Rabat (A):** *próg (A)* × *procent (A)* = $1000 × 10 procent = $100
- **Rabat (B):** *wartość sprzedana* × *procent (B)* = $2000 × 25 procent = $500
- **Rabat ogółem:** *Rabat (A)* + *Rabat (B)* = $100 + $500 = $600

### <a name="total-calculation-method"></a>Metoda obliczania całkowita

W metodzie obliczania całkowitej rabat jest obliczany tylko za pomocą wszystkich wierszy obliczeń. Ma ono zastosowanie do łącznej ilości w celu obliczenia rabatu dla każdego osiągniętego wiersza obliczenia, a każdy wiersz obliczania stosuje jego wartość procentową do pełnej kwoty. Podobnie jak w przypadku innych metod obliczania, w celu określenia, czy do obliczania rabatów jest używana wartość sprzedaży, w metodzie całkowitej stosowane jest pole **Podstawa** na karcie **Ogólne** w skróconej karcie **Szczegóły zarządzania rabatami**.

Na przykład wiersz umowy jest tak ustawiony, że w polu **Metoda obliczania** jest ustawiona wartość *Całkowita*, a w polu **Podstawa** jest *Wartość*. Wiersze te zawierają następujące wiersze obliczeń dotyczące rabatów:

- **Wiersz A:** 10 procent do $1,000
- **Wiersz B:** 25 procent do $2,500

Jeśli wartość towarów, które zostały nabyte lub sprzedane, $2000 rabat w $700 jest obliczany w następujący sposób:

- **Rabat (A):** *wartość sprzedana* × *procent (A)* = $2000 × 10 procent = $200
- **Rabat (B):** *wartość sprzedana* × *procent (B)* = $2000 × 25 procent = $500
- **Rabat ogółem:** *Rabat (A)* + *Rabat (B)* = $200 + $500 = $700

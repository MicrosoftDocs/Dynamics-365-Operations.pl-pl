---
title: Gotowość produktu
description: W tym temacie wyjaśniono, w jaki sposób można używać sprawdzania gotowości, aby upewnić się, że wymagane dane podstawowe dla produktu zostały uzupełnione przed użyciem w transakcjach.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f7ab6165e85cd2b1165292b74cd036f1233b22b4
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103020"
---
# <a name="product-readiness"></a>Gotowość produktu

[!include [banner](../includes/banner.md)]

Możesz użyć kontroli gotowości, aby pomóc upewnić się, że wszystkie wymagane dane podstawowe zostały określone dla produktu przed jego użyciem w transakcjach. Gdy używane są testy gotowości, użytkownik lub zespół jest odpowiedzialny za weryfikację określonych predefiniowanych danych związanych z produktem.

Zaznacz pole wyboru **Aktywny** dla produktu inżynieryjnego, wariantu lub wersji dopiero po wprowadzeniu i zweryfikowaniu wszystkich wymaganych danych oraz po przetworzeniu wszystkich kontroli gotowości. Jeśli co najmniej jedna kontrola produktu, wersji lub wariantu nie została przetworzona, przy próbie zaznaczenia pola wyboru **Aktywny** pojawi się monit z ostrzeżeniem, że nie wszystkie weryfikacje zostały zakończone.

Możesz tworzyć kontrole gotowości dla nowych produktów inżynieryjnych, wariantów i wersji. Możesz również zastosować kontrolę gotowości do standardowych (nietechnicznych) produktów (patrz również [Kontrola gotowości na standardowych produktach](#standard-products)). 

Możesz używać standardowych produktów w transakcjach, nawet jeśli nie wszystkie kontrole gotowości zostały zakończone. Jeśli chcesz zablokować produkt przed użyciem w transakcjach, użyj jego stanu cyklu życia. Można przypisać stan cyklu życia, który blokuje użycie produktu w transakcjach, a następnie, po zakończeniu wszystkich kontroli gotowości, przypisać nowy stan cyklu życia, który zezwala na wymagane transakcje.

## <a name="types-of-readiness-checks"></a>Typy kontroli gotowości

Istnieją trzy typy kontroli gotowości:

- **Sprawdzanie systemu** — system weryfikuje, czy rekord jest prawidłowy. Na przykład rekord może być aktywnym BOM.
- **Sprawdzanie ręczne** — użytkownik sprawdza, czy rekord jest ważny. Na przykład sprawdzenie gotowości może wymagać sprawdzenia poprawności domyślnych ustawień zamówienia. W niektórych przypadkach, na przykład gdy produkt jest nadal projektowany i dlatego nie będzie dostępny w magazynie, nie są wymagane żadne domyślne ustawienia zamówienia. Jednak dla innego produktu tego samego typu mogą być wymagane domyślne ustawienia zamówienia, ponieważ produkt może być przechowywany w magazynie. Użytkownik jest odpowiedzialny za poznanie sposobu, jak prawidłowo zdecydować, czy kontrola gotowości jest wymagana.
- **Lista kontrolna** — użytkownik odpowiada na listę pytań z listy kontrolnej, a system określa, czy odpowiedzi odpowiadają oczekiwaniom. Lista kontrolna może mieć dowolny temat. Można na przykład użyć do określenia, czy materiały marketingowe lub dokumentacja produktu są wypełnione.

<a name="checks-engineering"></a>

## <a name="how-readiness-checks-are-created-for-a-new-engineering-product-variant-or-version"></a>W jaki sposób tworzone są kontrole gotowości dla nowego produktu inżynieryjnego, wariantu lub wersji

Zasady sprawdzania gotowości można zastosować na poziomie wydanego produktu, wydanym wariancie i poziomie wersji inżynierskiej.

Podczas tworzenia nowego *produktu inżynieryjnego* system określa, czy ma do niego zastosowanie zasada [kontroli gotowości](#assign-policy). Jeśli mają zastosowanie zasady kontroli gotowości, mają miejsce następujące zdarzenia:

- Dla produktu są tworzone kontrole gotowości zgodnie z odpowiednią zasadą.
- Wersja inżynierii jest ustawiona jako nieaktywna, aby zablokować używanie produktu. Wszystkie wersje inżynieryjne tego produktu są ustawione jako nieaktywne.

Jeśli dla produktu jest tworzony nowy *wariant*, system sprawdza, czy ma zastosowanie zasada kontroli gotowości. (Kontrole gotowości można zastosować na poziomie zwolnionego wariantu i na poziomie wersji inżynierskiej). Jeśli kontrola gotowości jest zastosowana, występują następujące zdarzenia:

- Dla produktu są tworzone kontrole gotowości zgodnie z odpowiednią zasadą.
- Wersja inżynierii i wariant jest ustawiona jako nieaktywna, aby zablokować używanie produktu.

Jeśli dla produktu jest tworzona nowa *wersja* inżynieryjna, system sprawdza, czy ma zastosowanie zasada kontroli gotowości. (Kontrole gotowości można zastosować na poziomie wersji inżynierskiej). Jeśli kontrola gotowości jest zastosowana, występują następujące zdarzenia:

- Dla produktu są tworzone kontrole gotowości zgodnie z odpowiednią zasadą.
- Wersja inżynierii jest ustawiona jako nieaktywna, aby zablokować używanie produktu.

> [!NOTE]
> Można również skonfigurować zasady sprawdzania gotowości dla produktów standardowych (nie inżynierskich). Aby uzyskać więcej informacji, zobacz sekcję [Testy gotowości dla standardowych produktów](#standard-products) w dalszej części tego tematu.

## <a name="view-readiness-checks"></a>Wyświetlanie kontroli gotowości

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Wyświetl otwarte kontrole gotowości produktu lub wersji produktu

Aby znaleźć otwarte sprawdzenie gotowości produktu, otwórz stronę **Szczegóły zwolnionych produktów**. Następnie w okienku akcji na karcie **Produkt** w grupie **Kontrole gotowości** wybierz opcję **Kontrole gotowości**.

Aby wyszukać otwarte sprawdzenie gotowości dla wersji produktu, należy otworzyć stronę **Wersje inżynieryjne** dla zwolnionego produktu i wybrać wersję. Następnie w okienku akcji na karcie **Produkt** w grupie **Lista kontrolna** wybierz opcję **Kontrole gotowości**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Wyświetl otwarte kontrole gotowości przypisane do użytkownika

Aby wyświetlić otwarte kontrole gotowości przypisane do użytkownika, wykonaj jedną z tych czynności.

- Przejdź do **Zarządzanie zmianami projektowymi \> Wspólne \> Gotowość produktu \> Moje otwarte kontrole gotowości**.
- Przejdź do **Zarządzanie informacjami o produktach \> Obszary robocze \> Gotowość produktu do dyskretnej produkcji**.

Konfiguracja określająca, do kogo przypisane jest sprawdzenie gotowości, jest wykonywana dla zasady gotowości. Kontrole gotowości można przypisać do osoby lub zespołu. Jeśli do zespołu przypisana jest kontrola gotowości, w zespole jest jedna osoba, która musi przeprowadzić kontrolę gotowości.

## <a name="process-open-readiness-checks"></a>Przetwarzaj otwarte kontrole gotowości

### <a name="process-system-and-manual-readiness-checks"></a>Przetwórz kontrole systemu i kontroli gotowości ręcznej

Po otwarciu strony **Kontrole gotowości** można wyświetlić temat systemu i kontrole gotowości ręcznej, wybierając **Przeglądanie informacji pokrewnych** w okienku akcji. Następnie można ukończyć i/lub sprawdzić poprawność danych dla kontroli gotowości. Otwarte kontrole gotowości mają wartość **Stan** jako *Oczekujący*. Ten stan wskazuje, że kontrola gotowości musi być nadal przetwarzana. Aby przeprowadzić kontrolę gotowości, wykonaj jedną z następujących czynności.

- W okienku akcji wybierz pozycję **Sprawdź/zakończono**, aby przejrzeć i ukończyć sprawdzanie gotowości. Po zakończeniu pole **Stan** zostanie zaktualizowane do stanu *Powodzenie*.
- W okienku akcji wybierz opcję **Pomiń**, jeśli chcesz pominąć sprawdzanie gotowości, które nie jest wymagane. Na przykład można skonfigurować sprawdzanie gotowości dla obliczeń ceny. Należy jednak pominąć tę kontrolę, dopóki produkt nadal jest w fazie projektowania. W takim przypadku pole **Stan** jest aktualizowane na *Pominięte*.

W zależności od konfiguracji zasady gotowości, gdy pole **Stan** dla kontroli gotowości zostanie zaktualizowane do wartości *Powodzenie*, może być konieczne wykonanie dodatkowego kroku w celu zatwierdzenia kontroli gotowości. W takim przypadku należy wybrać opcję **Zatwierdzanie**, aby zakończyć sprawdzanie gotowości. Ten krok zatwierdzania jest zawsze obowiązkowy, gdy sprawdzanie gotowości zostanie pominięte.

Kiedy wszystkie otwarte kontrole gotowości dla nowego produktu, wariantu lub wersji zostaną przetworzone i zatwierdzone zgodnie z wymaganiami, pozycja automatycznie staje się aktywna, a zatem gotowa do użycia.

### <a name="process-checklist-readiness-checks"></a>Sprawdź gotowość listy kontrolnej procesu

Aby otworzyć listę kontrolną, otwórz stronę **Kontrole gotowości**, a następnie w okienku akcji wybierz opcję **Rozpocznij listę kontrolną**. Po wypełnieniu listy kontrolnej system sprawdza, czy kontrola gotowości została zakończona pomyślnie, na podstawie ustawień w kwestionariuszu.. Jeśli czek został zakończony, pole **Stan** jest aktualizowane na *Powodzenie*. Jeśli kontrola gotowości nie jest obowiązkowa, można ją pominąć. W takim przypadku pole **Stan** jest aktualizowane na *Pominięte*.

W zależności od konfiguracji zasady gotowości, gdy pole **Stan** dla kontroli gotowości zostanie zaktualizowane do wartości *Powodzenie*, może być konieczne wykonanie dodatkowego kroku w celu zatwierdzenia kontroli gotowości. W takim przypadku należy wybrać opcję **Zatwierdzanie**, aby zakończyć sprawdzanie gotowości. Ten krok zatwierdzania jest zawsze obowiązkowy, gdy sprawdzanie gotowości zostanie pominięte.

Kiedy wszystkie otwarte kontrole gotowości dla nowego produktu, wariantu lub wersji zostaną przetworzone i zatwierdzone zgodnie z wymaganiami, pozycja automatycznie staje się aktywna, a zatem gotowa do użycia.

## <a name="create-and-manage-product-readiness-policies"></a>Tworzenie zasad gotowości produktów i zarządzanie nimi

Użyj zasad gotowości produktu, aby zarządzać kontrolami gotowości, które mają zastosowanie do produktu. Każda zasada gotowości zawiera zbiór kontroli gotowości. Gdy zasada gotowości jest przypisana do kategorii produktu inżynierskiego lub produktu współdzielonego, wszystkie produkty, które są powiązane z tą kategorią lub produktem współdzielonym, będą miały kontrole gotowości, które są zawarte w polityce gotowości.

Aby pracować z zasadami gotowości produktów, przejdź do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Zasady gotowości produktów**. Następnie wykonaj jeden z następujących kroków.

- Aby utworzyć nową zasadę, wybierz opcję **Nowa** w okienku akcji, a następnie określ te pola zgodnie z poniższymi podsekcjami.
- Aby edytować istniejącą zasadę, wybierz ją w okienku listy, wybierz opcję **Edytuj** w okienku akcji, a następnie określ pola w sposób opisany w poniższych podsekcjach.
- Aby usunąć istniejącą zasadę, wybierz ją w okienku listy, wybierz opcję **Edytuj** w okienku akcji, a następnie na skróconej karcie **Ogólne** upewnij się, że opcja **Aktywne** jest ustawiona na wartość *Nie*. Następnie w okienku akcji wybierz opcję **Usuń**.

### <a name="header"></a>Nagłówek

Określ następujące pola w nagłówku zasady gotowości produktu.

| Pole | opis |
|---|---|
| Imię i nazwisko | Wprowadź nazwę zasady. |
| opis | Wprowadź opis zasady. |

### <a name="general-fasttab"></a>Skrócona karta Ogólne

Określ następujące pola na karcie skróconej **Ogólne**, należącej do zasady gotowości produktu.

| Pole | opis |
|---|---|
| Typ produktu | Umożliwia określenie, czy zasady dotyczą produktów typu *Towar* czy *Usługa*. Nie można zmienić tego ustawienia po zapisaniu rekordu. |
| Aktywni | Ta opcja służy do obsługi gotowości zwolnienia. Ustaw tę opcję na wartość *Tak* dla wszystkich używanych zasad gotowości. Jeśli zasada gotowości nie jest używana, należy wybrać opcję *Nie*, aby oznaczyć ją jako nieaktywną. Należy zauważyć, że nie można dezaktywować zasady gotowości przypisanej do kategorii produktów inżynieryjnych lub produktu współdzielonego i można usunąć tylko nieaktywne zasady zwalniania. |

### <a name="readiness-control-fasttab"></a>Skrócona karta Kontrola gotowości

Dla każdego typu kontroli gotowości, który chcesz uwzględnić w zasadzie, dodaj wiersz do skróconej karcie **Kontroli gotowości**. Użyj następujących przycisków na pasku narzędzi FastTab, aby dodawać i usuwać wiersze według potrzeb:

- **Dodaj czek** — umożliwia dodanie do zasady standardowego sprawdzenia gotowości. Po wybraniu tego przycisku pojawi się okno dialogowe **Dodaj pole** wyboru. Można wybrać opcję z listy dostępnych kontroli.
- **Dodaj istniejący kwestionariusz** — umożliwia dodanie pustego wiersza do siatki. Następnie można przypisać istniejący kwestionariusz, ustawiając pola w poniższej tabeli.
- **Kopiuj** — umożliwia dodanie kopii wybranego wiersza do siatki.
- **Usuń** — umożliwia usunięcie wybranego wiersza z siatki.

Dla każdego dodawanego wiersza należy określić następujące pola:

| Pole | opis |
| --- | --- |
| Obszar procesu | Umożliwia wybranie obszaru, z którym jest powiązana kontrola. |
| Typ | Wybierz, czy kontrola jest kontrolą systemu, kontrolą ręczną czy listą kontrolną (kwestionariuszem). |
| Imię i nazwisko | Jeśli czek jest listą kontrolną, wprowadź nazwę. W przypadku kontroli systemowych i ręcznych to pole jest ustawiane automatycznie. |
| opis | Jeśli czek jest listą kontrolną, wprowadź opis. W przypadku kontroli systemowych i ręcznych to pole jest ustawiane automatycznie, a opis wyjaśnia, na czym skupia się kontrola. |
| Zastosuj kontrole dla | Wybierz, czy wiersz powinien generować kontrole gotowości w odpowiedzi na nowy wydany produkt, wydany wariant lub wydaną wersję. |
| Wykonaj w: | Umożliwia określenie, czy w ramach kontroli gotowości wiersz ma być stosowany do wszystkich firm lub do jednej firmy. |
| Firma | Jeśli pole **Wykonaj w** jest ustawione na wartość *Pojedyncza firma*, należy wybrać firmę. |
| Typ właściciela | Wybierz, czy kontrole gotowości generowane przez wiersz powinny być przypisane do osoby czy zespołu. |
| Właściciel | Wybierz osobę lub zespół, do którego mają być przypisane kontrole gotowości generowane przez wiersz. |
| Kwestionariusz | Umożliwia wybranie kwestionariusza, który ma być używany dla listy kontrolnej. Lista kontrolna jest lokalną listą kontrolną w firmie, w której jest wykonywane sprawdzanie gotowości. System musi być w stanie ocenić, czy na liście kontrolnej jest poprawnie udzielona odpowiedź. Dlatego należy skonfigurować listę kontrolną, aby ocena była przeprowadzana na podstawie prawidłowych odpowiedzi. Aby uzyskać więcej informacji na temat tworzenia kwestionariuszy, zobacz temat [Używanie kwestionariuszy](/dynamicsax-2012/appuser-itpro/using-questionnaires) i tematy pokrewne. |
| Automatyczne zatwierdzanie | Rekordy kontroli gotowości zawierają pole wyboru **Zatwierdzona** wskazujące stan zatwierdzenia. Zaznacz pole wyboru **Automatyczne zatwierdzanie** dla kontroli, które mają zostać zatwierdzone natychmiast po zakończeniu przez przypisanego do nich użytkownika. Wyczyść to pole wyboru, aby wymagać wyraźnego zatwierdzenia jako dodatkowego kroku. |
| Wymagany | Zaznacz to pole wyboru w przypadku kontroli, które musi wykonać przypisany użytkownik. Obowiązkowych kontroli nie można pominąć. |

<a name="assign-policy"></a>

## <a name="assign-readiness-policies-to-standard-and-engineering-products"></a>Przypisywanie zasad gotowości do produktów standardowych i inżynieryjnych

Podczas tworzenia nowego produktu na podstawie kategorii inżynieryjnej jest tworzony zarówno *zwolniony produkt*, jak i powiązany *wspólny produkt*. Sposób, w jaki zasady gotowości są rozwiązywane dla zwolnionego produktu, zależy od tego, czy funkcja *Kontrola gotowości produktu* jest włączona w Twoim systemie (zobacz sekcję [Kontrole gotowości produktów standardowych](#standard-products) w dalszej części tego tematu aby uzyskać szczegółowe informacje na temat tej funkcji oraz sposobu jej włączania i wyłączania).

- Gdy funkcja *sprawdzania gotowości produktu* jest *wyłączona* w systemie, zasady gotowości są ustawiane i wyświetlane tylko w rekordach [kategorii inżynieryjnych](engineering-versions-product-category.md). Aby dowiedzieć się, które zasady dotyczą zwolnionego produktu, system sprawdza pole **Zasady gotowości produktu** dla powiązanej kategorii inżynieryjnej. Możesz zmienić zasady gotowości dla istniejącego produktu poprzez edycję powiązanej kategorii inżynieryjnej (nie współdzielonego produktu).
- Gdy funkcja *sprawdzania gotowości produktu* jest *włączona*, powoduje ona dodanie pola **Zasady gotowości produktu** do strony **Produkt** (na której są ustawione wspólne produkty) oraz do strony **Zwolniony produkt** (na której wartość jest tylko do odczytu i jest łączona z powiązanego produktu udostępnionego). System znajduje politykę gotowości dla wydanego produktu poprzez sprawdzenie powiązanego z nim produktu współdzielonego. Gdy do utworzenia nowego produktu inżynieryjnego jest używana kategoria inżynieryjna, system tworzy zarówno wspólny produkt, jak i zwolniony produkt i kopiuje wszystkie ustawienia **zasad gotowości produktu** dla kategorii inżynieryjnej do nowego produktu udostępnionego. Następnie można zmienić politykę gotowości dla istniejącego produktu poprzez edycję powiązanego produktu współdzielonego (nie kategorii inżynierii zwolnionej).

Aby przypisać politykę gotowości do udostępnionego produktu, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Informacje o produktach \> Produkty \> Produkty**.
1. Otwórz lub utwórz produkt, do którego chcesz przypisać zasady gotowości.
1. Na skróconej karcie **Ogólne** ustaw nazwę **zasady gotowości produktu** na nazwę, która mieć zastosowanie do produktu.

Aby przypisać politykę gotowości do kategorii inżynierskiej, wykonaj poniższe kroki.

1. Przejdź do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Szczegóły kategorii produktów inżynieryjnych**.
1. Otwórz lub utwórz kategorię inżynieryjną do której chcesz przypisać zasady gotowości.
1. Na skróconej karcie **Zasady gotowości produktu** ustaw nazwę **zasady gotowości produktu** na nazwę, która mieć zastosowanie do kategorii inżynieryjnej.

<a name="standard-products"></a>

## <a name="readiness-checks-on-standard-products"></a>Testy gotowości dla standardowych produktów

Sprawdzanie gotowości produktu dla standardowych (nie inżynieryjnych) produktów można włączyć, włączając funkcję *kontroli gotowości produktu* w zarządzaniu funkcjami. Ta funkcja wprowadza kilka małych zmian w systemie kontroli gotowości, dzięki czemu obsługuje produkty standardowe.

### <a name="enable-or-disable-readiness-checks-on-standard-products"></a>Włącz lub wyłącz kontrole gotowości na standardowych produktach

Funkcja wymaga włączania w *systemie zarówno zarządzania zmianami inżynieryjnymi*, jak i *Kontrole gotowości produktu*. Aby uzyskać szczegółowe informacje dotyczące sposobu włączanie i wyłączanie tych funkcji, zobacz [omówienie zarządzania zmianami inżynieryjnymi](product-engineering-overview.md).

### <a name="create-readiness-policies-for-standard-products"></a>Tworzenie zasad gotowości dla standardowych produktów

Zasady gotowości dla produktów standardowych tworzyć można tak samo jak w przypadku tworzenia produktów. Zobacz informacje we wcześniejszej części tego tematu.

### <a name="assign-readiness-policies-to-standard-products"></a>Przypisanie zasad gotowości do produktów standardowych

Aby przypisać zasady gotowości do standardowego produktu, otwórz powiązany produkt udostępniony i ustaw pole **Zasady gotowości produktu** na nazwę zasady, która ma mieć zastosowanie. Aby uzyskać więcej informacji, zobacz sekcję [Przypisywanie zasad gotowości do produktów standardowych i inżynieryjnych](#assign-policy) wcześniej w tym temacie.

### <a name="view-and-process-readiness-checks-on-standard-products"></a>Przeglądanie i przeprowadzanie kontroli gotowości produktów standardowych

Gdy ta funkcja jest włączona, można przeglądać i przetwarzać kontrole gotowości dla produktów standardowych w taki sam sposób, jak dla produktów inżynieryjnych. Zobacz informacje we wcześniejszej części tego tematu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

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
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 3acdde483cb997b4a16a497f145c7c087c6906b5
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909726"
---
# <a name="product-readiness"></a>Gotowość produktu

[!include [banner](../includes/banner.md)]

Możesz użyć kontroli gotowości, aby upewnić się, że wszystkie wymagane dane podstawowe zostały określone dla produktu przed jego użyciem w transakcjach. Gdy używane są testy gotowości, użytkownik lub zespół jest odpowiedzialny za weryfikację określonych predefiniowanych danych związanych z produktem. Jeśli istnieje otwarta kontrola gotowości produktu, produkt nie może zostać zwolniony ani używany w transakcjach.

Pole wyboru **Aktywny** dla produktu inżynieryjnego, wariantu lub wersji jest dostępne dopiero po wprowadzeniu i zweryfikowaniu wszystkich wymaganych danych oraz po przetworzeniu wszystkich kontroli gotowości. W tym momencie produkt, wersja lub wariant mogą zostać zwolnione do innych firm i używane w transakcjach. Można tworzyć kontrole gotowości dla nowych produktów, nowych wariantów i nowych wersji inżynieryjnych.

## <a name="types-of-readiness-checks"></a>Typy kontroli gotowości

Istnieją trzy typy kontroli gotowości:

- **Sprawdzanie systemu** — system weryfikuje, czy rekord jest prawidłowy. Na przykład rekord może być aktywnym BOM.
- **Sprawdzanie ręczne** — użytkownik sprawdza, czy rekord jest ważny. Na przykład sprawdzenie gotowości może wymagać sprawdzenia poprawności domyślnych ustawień zamówienia. W niektórych przypadkach, na przykład gdy produkt jest nadal projektowany i dlatego nie będzie dostępny w magazynie, nie są wymagane żadne domyślne ustawienia zamówienia. Jednak dla innego produktu tego samego typu mogą być wymagane domyślne ustawienia zamówienia, ponieważ produkt może być przechowywany w magazynie. Użytkownik jest odpowiedzialny za poznanie sposobu, jak prawidłowo zdecydować, czy kontrola gotowości jest wymagana.
- **Lista kontrolna** — użytkownik odpowiada na listę pytań z listy kontrolnej, a system określa, czy odpowiedzi odpowiadają oczekiwaniom. Lista kontrolna może mieć dowolny temat. Można na przykład użyć do określenia, czy materiały marketingowe lub dokumentacja produktu są wypełnione.

## <a name="how-readiness-checks-are-created-for-a-new-product-variant-or-version"></a>W jaki sposób tworzone są kontrole gotowości dla nowego produktu, wariantu lub wersji

Podczas tworzenia nowego produktu **inżynieryjnego** system określa, czy dla kategorii produktów inżynieryjnych skonfigurowano zasady sprawdzania gotowości. (Zasady sprawdzania gotowości można zastosować na poziomie wydanego produktu, wydanym wariancie i poziomie wersji inżynierskiej). Jeśli skonfigurowano zasady, występują następujące zdarzenia:

- Dla produktu są tworzone kontrole gotowości zgodnie z odpowiednią zasadą.
- Wersja inżynierii jest ustawiona jako nieaktywna, aby zablokować używanie produktu. Wszystkie wersje określonego produktu, którego to dotyczy, są ustawione jako nieaktywne.

Jeśli dla produktu zostanie utworzony nowy **wariant**, system sprawdza, czy w kategorii produktów technologicznych skonfigurowano kontrole gotowości. (Kontrole gotowości można zastosować na poziomie zwolnionego wariantu i na poziomie wersji inżynierskiej). Jeśli skonfigurowano kontrolę gotowości, występują następujące zdarzenia:

- Dla produktu są tworzone kontrole gotowości.
- Wersja inżynierii jest ustawiona jako nieaktywna, aby zablokować używanie produktu.

Jeśli dla produktu zostanie utworzony nowa **wersja** inżynieryjna, system sprawdza, czy w kategorii produktów technologicznych skonfigurowano kontrole gotowości. (Kontrole gotowości można zastosować na poziomie wersji inżynierskiej). Jeśli skonfigurowano kontrolę gotowości, występują następujące zdarzenia:

- Dla produktu są tworzone kontrole gotowości.
- Wersja inżynierii jest ustawiona jako nieaktywna, aby zablokować używanie produktu.

## <a name="view-readiness-checks"></a>Wyświetlanie kontroli gotowości

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Wyświetl otwarte kontrole gotowości produktu lub wersji produktu

Aby znaleźć otwarte sprawdzenie gotowości produktu, otwórz stronę **Szczegóły zwolnionych produktów**. Następnie w okienku akcji na karcie **Produkt** w grupie **Kontrole gotowości** wybierz opcję **Kontrole gotowości**.

Aby wyszukać otwarte sprawdzenie gotowości dla wersji produktu, należy otworzyć stronę **Wersje inżynieryjne** dla zwolnionego produktu i wybrać wersję. Następnie w okienku akcji na karcie **Produkt** w grupie **Lista kontrolna** wybierz opcję **Kontrole gotowości**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Wyświetl otwarte kontrole gotowości przypisane do użytkownika

Aby wyświetlić otwarte kontrole gotowości przypisane do użytkownika, wykonaj jedną z tych czynności.

- Przejdź do **Zarządzanie zmianami projektowymi \> Wspólne \> Gotowość produktu \> Moje otwarte kontrole gotowości**.
- Przejdź do **Zarządzanie informacjami o produktach \> Obszary robocze \> Gotowość produktu do dyskretnej produkcji**.

Konfiguracja określająca, do kogo przypisane jest sprawdzenie gotowości, jest wykonywana dla kategorii produktów inżynieryjnych. Kontrole gotowości można przypisać do osoby lub zespołu. Jeśli do zespołu przypisana jest kontrola gotowości, w zespole jest jedna osoba, która musi przeprowadzić kontrolę gotowości. Aby uzyskać więcej informacji, zobacz [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).

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

Użyj zasad gotowości produktu, aby zarządzać kontrolami gotowości, które mają zastosowanie do produktu. Ponieważ zasada gotowości jest przypisana do kategorii inżynieryjnej, wszystkie kontrole w zasadach gotowości mają zastosowanie do wszystkich produktów inżynieryjnych opartych na kategorii inżynieryjnej. Aby uzyskać więcej informacji, zobacz [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).

Każda zasada gotowości zawiera zbiór kontroli gotowości. Kiedy polityka gotowości jest przypisana do kategorii produktów inżynieryjnych, wszystkie produkty utworzone z tej kategorii produktów inżynieryjnych będą miały kontrole gotowości, które są wskazane w zasadach gotowości.

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
| Aktywni | Ta opcja służy do obsługi gotowości zwolnienia. Ustaw tę opcję na wartość *Tak* dla wszystkich używanych zasad gotowości. Jeśli zasada gotowości nie jest używana, należy wybrać opcję *Nie*, aby oznaczyć ją jako nieaktywną. Należy zauważyć, że nie można dezaktywować zasady gotowości przypisanej do kategorii produktów inżynieryjnych i można usunąć tylko nieaktywne zasady zwalniania. |

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
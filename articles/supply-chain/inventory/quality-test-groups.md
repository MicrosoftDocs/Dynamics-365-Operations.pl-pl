---
title: Grupy testowe zarządzania jakością
description: W tym artykule opisano sposób tworzenia grup testowych, dzięki czemu można używać wielu testów ze zleceniami kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7722bc92d8c2bf52d6a798a93f07af44037d4e0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857714"
---
# <a name="quality-management-test-groups"></a>Grupy testowe zarządzania jakością

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób tworzenia grup testowych, dzięki czemu można używać wielu testów ze zleceniami kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.

Strona **Grupy testowe** służy do konfigurowania, edytowania i wyświetlania grup testowych oraz testów indywidualnych do nich należących. W górnej części strony pokazane są grupy testowe, a w dolnym — testy przypisane do wybranej grupy testowej.

Do grupy testowej można przypisać różne zasady, w tym plan próbkowania, akceptowany poziom jakości i wymaganie dotyczące testowania destrukcyjnego. Po przypisaniu każdego z tych testów do grupy testowej, można zdefiniować dodatkowe informacje, takie jak sekwencje, dokumenty i daty ważności. W przypadku testu ilościowego zdefiniowane informacje zawierają również akceptowalne wartości pomiaru. W przypadku testu jakościowego informacje zmienną testową i domyślny rezultat.

Za pomocą grupy testów przypisanej do zlecenia kontroli jakości określa się domyślny zestaw testów, które muszą zostać przeprowadzone odnośnie do określonego towaru. Testy można dodawać, usuwać lub zmieniać w zleceniu kontroli jakości. Wyniki testu są raportowane dla każdego testu w zleceniu kontroli jakości.

Podczas definiowania grupy testowej można opcjonalnie określić próbkowanie towaru. Próbkowanie towaru służy do definiowania ilości produktu, który musi być testowany. Aby uzyskać więcej informacji, zobacz temat [Kontrola wyrywkowa towaru zarządzania jakością](quality-item-sampling.md). Można także wskazać, czy testy w grupie testowej są destrukcyjne. W teście destrukcyjnym próbkowany towar jest niszczony, a ilość jest usuwana z dostępnych zapasów.

## <a name="example-of-a-test-group"></a>Przykładowa grupa testowa

W przedsiębiorstwie produkcyjnym zdefiniowano grupę testową dla każdego odchylenia dotyczącego zasad kontroli jakości. Poszczególne grupy testowe odpowiadają różnym planom próbkowania, seriom testów, które muszą być wykonywane razem, akceptowanemu poziomowi jakości i innym czynnikom. W testach ilościowych są również różnice we właściwych wartościach pomiaru. Aby wymusić zasady kontroli jakości, firma przypisuje grupę testową do każdej reguły używanej do automatycznego generowania zleceń kontroli jakości na stronie **Skojarzenia jakości**. Ponadto grupa testowa jest przypisywana do zleceń kontroli jakości, które są tworzone ręcznie.

## <a name="create-a-test-group"></a>Tworzenie grupy testowej

Aby utworzyć grupę testową, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy testowe**.
1. W okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki w górnej części strony. Następnie ustaw następujące pola dla nowego wiersza:

    - **Grupa testowa** – wpisz unikatowy identyfikator lub nazwę grupy testowej.
    - **Opis** – wprowadź szczegółowy opis grupy testowej.
    - **Akceptowany poziom jakości** — umożliwia wprowadzenie łącznego procentu wyników testu, które muszą zostać zaliczone, aby grupa testów została uznana za zaliczoną.
    - **Kontrola wyrywkowa towaru** — umożliwia wybór kontroli wyrywkowej towaru. Aby uzyskać więcej informacji, zobacz temat [Kontrola wyrywkowa towaru zarządzania jakością](quality-item-sampling.md).
    - **Destrukcyjny** — zaznaczenie tego pola wyboru umożliwia wskazanie, że grupa testowa będzie niszczyć testowane towary.

1. W trakcie zaznaczania nowego wiersza wybierz kartę **Ogólne** w górnej części strony. W tym miejscu są powtarzane niektóre ustawienia grupy testowej wybranej na karcie **Przegląd**. Dodatkowo dla grupy można ustawić następujące pola:

    - **Aktualizacja atrybutu partii zapasów** – W przypadku ustawienia tej opcji na wartość *Tak* w tym miejscu dla każdego nowego testu dodawanego do grupy testowej w dolnej części strony zostanie automatycznie ustawiona wartość *Tak*.
    - **Aktualizuj dyspozycję partii** — Po ustawieniu tej opcji na wartość *Tak*, jeśli testowany towar jest kontrolowany przez partię, dyspozycja partii zostanie automatycznie zaktualizowana wartością wybraną w polu **Dyspozycja partii nieudanego zlecenia kontroli jakości** lub **Dyspozycja partii udanego zlecenia kontroli jakości**.
    - **Dyspozycja partii nieudanego zlecenia kontroli jakości** — należy wybrać kod dyspozycji partii, który zostanie przypisany w przypadku niespełnienia warunku akceptowalnego poziomu jakości przez zlecenie kontroli jakości, które zawiera tę grupę testową.
    - **Dyspozycja partii udanego zlecenia kontroli jakości** — należy wybrać kod dyspozycji partii, który zostanie przypisany w przypadku spełnienia warunku akceptowalnego poziomu jakości przez zlecenie kontroli jakości, które zawiera tę grupę testową.
    - **Aktualizuj stan zapasów** — Po ustawieniu tej opcji na wartość *Tak*, jeśli opcja **Stan zapasów** jest włączona w grupie wymiarów magazynowania testowanego towaru stan zostanie automatycznie zmieniony na stan wybrany w polu **Stan nieudanego zlecenia kontroli jakości** lub **Stan udanego zlecenia kontroli jakości**.
    - **Stan nieudanego zlecenia kontroli jakości** — należy wybrać stan zapasów, który zostanie przypisany do towaru w przypadku niespełnienia warunku akceptowalnego poziomu jakości przez zlecenie kontroli jakości, które zawiera tę grupę testową.
    - **Stan udanego zlecenia kontroli jakości** — należy wybrać stan zapasów, który zostanie przypisany do towaru w przypadku spełnienia warunku akceptowalnego poziomu jakości przez zlecenie kontroli jakości, które zawiera tę grupę testową.

## <a name="add-a-qualitative-test-to-a-test-group"></a>Dodawanie testu jakościowego do grupy testowej

Aby dodać test jakościowy do grupy testowej, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy testowe**.
1. Na karcie **Przegląd** w górnej części strony wybierz grupę testową, do której chcesz dodać test.
1. W dolnej części strony, na karcie **Przegląd** wybierz pozycję **Dodaj** na pasku narzędzi, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Numer sekwencyjny** — umożliwia wprowadzenie liczby całkowitej określającej kolejność, w jakiej należy wykonywać testy. Testy o mniejszych numerach sekwencyjnych będą uruchamiane przed testami o większych numerach sekwencyjnych.

        > [!NOTE]
        > Zaleca się pozostawienie odstępu między numerami sekwencyjnymi. Ustaw **Numer sekwencyjny** na przykład wartość *10* dla pierwszego testu, a następnie zwiększaj wartość o 10 dla każdego dodatkowego testu. W ten sposób będzie można później dodać nowe testy bez konieczności usuwania i ponownego tworzenia wierszy, aby umieścić je w żądanej kolejności.

    - **Test** — Służy do wybierania testu, który ma zostać wykonany. W przypadku testu jakościowego wybierz test, w którym pole **Typ** ma wartość *Opcja*.
    - **Ważność od** — Data początku okresu ważności testu. Jeśli to pole jest puste, żaden limit nie obowiązuje.
    - **Ważność do** — Data końca okresu ważności testu. Jeśli to pole jest puste lub ustawiono dla niego wartość *Nigdy*, ważność jest bezterminowa.
    - **Określenie wartości testowej** – Należy wybrać sposób określania akceptowalnego poziomu jakości w przypadku, gdy jest rejestrowanych wiele wyników tego samego testu. W przypadku testu jakościowego można wybrać tylko opcję *Ręcznie*. W przypadku wybrania jednej z pozostałych wartości (*Średnia*, *Minimum* lub *Maksimum*) podczas zapisywania grupy testowej pojawi się komunikat o błędzie.
    - **Atrybut** — Jeśli chcesz rejestrować wyniki testu dotyczące atrybutu partii, zaznacz ten atrybut w tym miejscu i zaznacz pole wyboru **Aktualizuj atrybuty partii zapasów**.
    - **Aktualizuj atrybuty partii zapasów** — Zaznacz to pole wyboru, aby rejestrować wyniki testu dotyczące atrybutu partii, który jest wybrany w polu **Atrybut**.

1. W dolnej części strony wybierz kartę **Ogólne**. W tym miejscu są powtarzane niektóre ustawienia testu wybranego na karcie **Przegląd**. Dodatkowo dla testu można ustawić następujące pola:

    - **Raport certyfikatu analizy** – Ustaw tę opcję na Wartość *Tak*, aby wskazać, że wyniki testu mają być drukowane na certyfikacie analizy (CoA). Ten raport może być generowany na podstawie zlecenia kontroli jakości.
    - **Akcja w przypadku wyniku negatywnego** — wybierz opcję *Akceptacja* lub *Niepowodzenie*, aby określić, czy test ma być zaliczany czy nie, jeśli jego warunek akceptowalnego poziomu jakości nie jest spełniony.
    - **Akceptowany poziom jakości** — umożliwia wprowadzenie łącznego procentu wyników testu, które muszą zostać zaliczone, aby test został uznana za zaliczony.

1. W dolnej części strony, na karcie **Test** ustaw następujące pola:

    - **Zmienna** — Umożliwia wybranie zmiennej testu służącej do rejestrowania wyników testu jakościowego.
    - **Wynik domyślny** — umożliwia wybór wyniku domyślnego, który powinien być rejestrowany dla wyników testu.
    - **Przyrząd testowy** — należy wybrać urządzenie, które ma być używane w teście. Jeśli zostanie zdefiniowany przyrząd testowy, zostanie on automatycznie wprowadzony do testu w grupie testowej.

1. Zamknij stronę.

## <a name="add-a-quantitative-test-to-a-test-group"></a>Dodawanie testu ilościowego do grupy testowej

Aby dodać test ilościowy do grupy testowej, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy testowe**.
1. Na karcie **Przegląd** w górnej części strony wybierz grupę testową, do której chcesz dodać test.
1. W dolnej części strony, na karcie **Przegląd** wybierz pozycję **Dodaj** na pasku narzędzi, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Numer sekwencyjny** — umożliwia wprowadzenie liczby całkowitej określającej kolejność, w jakiej należy wykonywać testy. Testy o mniejszych numerach sekwencyjnych będą uruchamiane przed testami o większych numerach sekwencyjnych.

        > [!NOTE]
        > Zaleca się pozostawienie odstępu między numerami sekwencyjnymi. Ustaw **Numer sekwencyjny** na przykład wartość *10* dla pierwszego testu, a następnie zwiększaj wartość o 10 dla każdego dodatkowego testu. W ten sposób będzie można później dodać nowe testy bez konieczności usuwania i ponownego tworzenia wierszy, aby umieścić je w żądanej kolejności.

    - **Test** — Służy do wybierania testu, który ma zostać wykonany. W przypadku testu ilościowego wybierz test, w którym pole **Typ** ma wartość *Ułamek* lub *Liczba całkowita*.
    - **Ważność od** — Data początku okresu ważności testu. Jeśli to pole jest puste, żaden limit nie obowiązuje.
    - **Ważność do** — Data końca okresu ważności testu. Jeśli to pole jest puste lub ustawiono dla niego wartość *Nigdy*, ważność jest bezterminowa.
    - **Określenie wartości testowej** – Należy wybrać sposób określania akceptowalnego poziomu jakości w przypadku, gdy jest rejestrowanych wiele wyników tego samego testu. Dostępne opcje to *Średnia*, *Minimum*, *Maksimum* i *Ręcznie*.
    - **Atrybut** — Jeśli chcesz rejestrować wyniki testu dotyczące atrybutu partii, zaznacz ten atrybut w tym miejscu i zaznacz pole wyboru **Aktualizuj atrybuty partii zapasów**.
    - **Aktualizuj atrybuty partii zapasów** — Zaznacz to pole wyboru, aby rejestrować wyniki testu dotyczące atrybutu partii, który jest wybrany w polu **Atrybut**.

1. W dolnej części strony wybierz kartę **Ogólne**. W tym miejscu są powtarzane niektóre ustawienia testu wybranego na karcie **Przegląd**. Dodatkowo dla testu można ustawić następujące pola:

    - **Raport certyfikatu analizy** – Ustaw tę opcję na Wartość *Tak*, aby wskazać, że wyniki testu mają być drukowane na certyfikacie analizy. Ten raport może być generowany na podstawie zlecenia kontroli jakości.
    - **Akcja w przypadku wyniku negatywnego** — wybierz opcję *Akceptacja* lub *Niepowodzenie*, aby określić, czy test ma być zaliczany czy nie, jeśli jego warunek akceptowalnego poziomu jakości nie jest spełniony.
    - **Akceptowany poziom jakości** — umożliwia wprowadzenie łącznego procentu wyników testu, które muszą zostać zaliczone, aby test został uznana za zaliczony.

1. W dolnej części strony, na karcie **Test** ustaw następujące pola:

    - **Standard** — służy do wprowadzania oczekiwanej ilości (liczby całkowitej lub ułamkowej) dla wyników testu. Wprowadzona wartość zostanie domyślnie wprowadzona w wynikach testu. Ponadto jest ona automatycznie wprowadzana jako wartość domyślna w polach **Minimum** i **Maksimum**.
    - **Minimum** — należy wprowadzić minimalną dozwoloną wartość wyników testu. Wprowadzana wartość musi być mniejsza niż ilość ustawiona w polu **Standard**. Aktualizacja pola **Min.** powoduje automatycznie aktualizację pola **Min. tolerancja (%)**. Analogicznie, aktualizacja pola **Min. tolerancja (%)** powoduje automatycznie aktualizację pola **Min.**
    - **Maks.** — należy wprowadzić maksymalną dozwoloną wartość wyników testu. Wprowadzana wartość musi być większa niż ilość ustawiona w polu **Standard**. Aktualizacja pola **Maks.** powoduje automatycznie aktualizację pola **Maks. tolerancja (%)**. Analogicznie, aktualizacja pola **Maks. tolerancja (%)** powoduje automatycznie aktualizację pola **Maks.**
    - **Przyrząd testowy** — należy wybrać urządzenie, które ma być używane w teście. Jeśli zostanie zdefiniowany przyrząd testowy, zostanie on automatycznie wprowadzony do testu w grupie testowej.

1. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Przyrządy testowe zarządzania jakością](quality-management-processes.md)
- [Testy zarządzania jakością](quality-management-processes.md)
- [Zmienne testu zarządzania jakością](quality-management-processes.md)
- [Powiązania jakości](quality-management-processes.md)
- [Atrybuty partii](../production-control/batch-attributes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

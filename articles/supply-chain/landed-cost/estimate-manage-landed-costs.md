---
title: Szacowanie kosztów z wyładunkiem i zarządzanie nimi
description: W systemie automatycznie są używane ustawienia kosztów, które określają szacowanie kosztów z wyładunkiem. W tym artykule opisano, jak można definiować różne scenariusze w celu zapewnienia dokładniejszego oszacowania.
author: Weijiesa
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 2e7cdd7c7439a24ec75a59bcee1e8f42f37bb2cd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854449"
---
# <a name="estimate-and-manage-landed-costs"></a>Szacowanie kosztów z wyładunkiem i zarządzanie nimi

[!include [banner](../../includes/banner.md)]

W systemie są używane [automatycznie ustawienia kosztów](auto-cost-setup.md), które określają szacowanie kosztów z wyładunkiem. Ponadto można definiować różne scenariusze w celu zapewnienia dokładniejszego oszacowania. Te scenariusze są przechowywane. W związku z tym można je później przejrzeć i porównać z wartościami rzeczywistymi w raporcie. Można również zaktualizować cenę towaru.

## <a name="set-up-cost-estimates"></a>Konfigurowanie szacowania kosztów

### <a name="set-up-cost-templates"></a>Ustawianie szablonów kosztów

Szablony kosztów określają domyślne ustawienia, których użytkownicy, którzy otrzymują oszacowanie, niekoniecznie muszą znać. Szablony mogą pomóc zmniejszyć złożoność procesu szacowania, minimalizując wybory, które użytkownicy muszą podjąć, aby uzyskać dokładne oszacowanie. W przypadku używania standardowego modelu kosztów podczas tworzenia kosztu towarów można używać szablonów kosztów.

Aby skonfigurować szablony kosztów, przejdź do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Szablon kosztu**. Na stronie **Szablony kosztów** w okienku listy po lewej stronie są widać wszystkie bieżące szablony kosztów. Możesz używać przycisków w Okienku akcji do tworzenia, usuwania i edytować szablony.

W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego szablonu.

| Pole | opis |
|---|---|
| Szablon kosztów | Wprowadź unikatową nazwę szablonu kosztu. Nazwa zwykle opisuje współczynnik lub mnożnik kosztu dla szablonu. |
| opis | Umożliwia wprowadzenie krótkiego opisu szablonu kosztu. |
| Firma przewozowa | Wybierz firmę przewozową, która ma zostać zastosowana podczas korzystania z szablonu. |
| Metoda dostawy | Wybierz sposób dostawy, taki jak morski lub lotniczy, który ma być zastosowany, gdy używany jest szablon. To pole pomaga ustalić automatyczne koszty, które są skojarzone z towarami w szacowaniu kosztów. |
| Typ kontenera wysyłkowego | Wybierz typ kontenera wysyłkowego, który ma zostać zastosowany, gdy używany jest szablon. To pole pomaga ustalić automatyczne koszty, które są skojarzone z towarami w szacowaniu kosztów. |
| Broker urzędu celnego | Broker celny (sprzedawca), który powinien zostać zastosowany podczas korzystania z szablonu. To pole pomaga ustalić automatyczne koszty, które są skojarzone z szacowaniem kosztów. |
| Współczynnik | Wprowadź mnożnik (wartość procentową), który powinien być automatycznie zastosowany do oszacowania kosztów w przypadku użycia szablonu. Na przykład aby dodać 10 procent do obliczonego oszacowania kosztów, wprowadź *1,10*. |

### <a name="create-a-cost-estimate"></a>Utwórz kosztorys

Okno dialogowe **Szacowanie kosztów** pozwala wygenerować nowe szacowanie kosztów na podstawie wybranego szablonu kosztów, wybranego zestawu towarów i innych szczegółów wyjazdu. Te ustawienia są używane do określania szacowanych kosztów z wyładunkiem towarów. Te szacowane koszty są używane głównie do pracy z kosztami standardowymi. Dodając szacunkowe koszty wyładunku do standardowego kosztu towarów w zapasach, należy doświadczyć mniejszych transakcji odchylenia, gdy towary są dodawane do podróży, ponieważ koszt standardowy będzie odzwierciedlał szacunki tych kosztów wyładunku.

Aby otworzyć okno dialogowe **Szacowanie kosztów**, przejdź do **Koszt z wyładunkiem \> Zadania okresowe \> Szacowanie kosztów**. Następnie ustaw pola, które są opisane w kolejnych podrozdziałach. Na koniec wybierz **OK**, aby utworzyć oszacowanie. Zostanie wyświetlona strona **Szacowanie kosztów** (**Koszt z wyładunkiem \> Zapytania \> Szacowanie kosztów**) i pokazuje nowe szacowanie opisane dalej w tym artykule.

### <a name="settings-on-the-parameters-tab"></a>Ustawienia na karcie Parametry

W poniższej tabeli opisano pola dostępne na karcie **Parametry** w oknie dialogowym **Szacowanie kosztów**.


| Pole | opis |
|---|---|
| Szablon kosztów | Wybierz szablon kosztu. Ustawienia skojarzone z wybranym szablonem będą używane do określania stosowanych automatycznie kosztów. |
| Data szacowania | Domyślnie w tym polu jest ustawiona data dzisiejsza, ale można ją zmienić. Określona data zostanie użyta do wybrania odpowiednich cen sprzedaży, cen zakupu, kosztów automatycznych i kursu wymiany, jeśli używany jest kurs wysyłki. |
| Miara | Koszty mogą być zależne od miary. Na przykład w przypadku frachtu lotniczego mogą obowiązywać ceny wolumetryczne. Jeśli koszt zależy od miary, należy wprowadzić wartość tej miary. W przeciwnym razie zalecane jest ustawienie tego pola na wartość *1*, chyba że użytkownik ma pewność, że użycie miary nie nastąpi żadne rozwiązanie. Wprowadź wartość dziesiętną. Jednostka jest jednostką zdefiniowaną w stosownym rekordzie automatycznego kosztu. |
| Szablon podróży | Wybierz [szablon podróży](multi-leg-journey-setup.md). To pole służy do określania poprawnych kosztów automatycznych, które powinny zostać zastosowane. |
| Port źródłowy | Port, z którego zostaną wysłane produkty. To pole jest ustawiane na podstawie wybranego szablonu podróży. |
| Port docelowy | Port, do którego zostaną wysłane produkty. To pole jest ustawiane na podstawie wybranego szablonu podróży. |
| Waluta | Umożliwia wybranie waluty, w jakiej będą kupowane towary |
| Kontenery | Jeśli jest zwykle używanych wiele kontenerów, należy określić ich liczbę. Podczas szacowania kosztów system użyje kosztów dla wielu kontenerów. |
| Folio | Jeśli zwykle jest używanych wiele folio, określ ilość. (Ilość zazwyczaj wynosi *1*.) |
| Oddział | Umożliwia określenie miejsca, do którego zostaną dostarczone towary. |

### <a name="settings-on-the-items-tab"></a>Ustawienia na karcie Pozycje

Na karcie **Pozycje** można dodać do oszacowania jak najwięcej towarów. Użyj paska narzędzi, aby dodać elementy do siatki lub usunąć elementy. Wybierz **Zapasy \> Wyświetl wymiary** na pasku narzędzi, aby otworzyć okno dialogowe, w którym można dodawać kolumny wymiarów do siatki lub usuwać kolumny.

W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdej pozycji.

| Pole | opis |
|---|---|
| Numer towaru | Wybierz pozycję, dla której ma być określana cena. (Jeśli przedmiot nie istnieje jeszcze w systemie, utwórz przedmiot fikcyjny, opcjonalnie dołącz go do grupy kosztów towarów z podróży, a następnie pozostaw cenę pustą lub utwórz lub zmień cenę). |
| Konto dostawcy | Wybierz dostawcę, którego chcesz użyć do oszacowania tej pozycji. Jeśli do towaru przypisany jest domyślny dostawca, to pole jest ustawiane automatycznie. |
| Ilość | Zaznacz ilość, jaką kupisz. |
| Koszt własny | System wykorzystuje swoje reguły cenowe, aby znaleźć cenę początkową, ale w razie potrzeby możesz zmienić tę cenę. |
| Cena sprzedaży | Wprowadź oczekiwaną cenę sprzedaży towarów. |
| Miara | Umożliwia wprowadzenie wartości dziesiętnej dla miary towarów. Jednostka skonfigurowana dla odpowiedniego wydanego produktu. |
| Aktualizuj wagę/objętość pozycji | Zaznaczenie tego pola wyboru umożliwia zaktualizowanie miary wagi lub objętości zwolnionego produktu, tak aby była taka, jak wartość **Miara** wprowadzona dla tego wiersza. |
| (Inne wymiary) | W zależności od wymiarów wybranych do pokazania mogą zostać wyświetlane dodatkowe kolumny informacji o każdym towarze. |

Aby wyświetlić lub skorygować szczegóły objętości i/lub wagi towaru, zaznacz towar w siatce, a następnie użyj pól u dołu strony.

## <a name="manage-estimated-costs"></a>Zarządzanie kosztami szacowanymi

Aby wyświetlić i edytować utworzone oszacowania kosztów, przejdź do **Koszt z wyładunkiem \> Zapytania \> Szacowanie kosztów**. Na stronie **Szacowanie kosztów** w okienku listy po lewej stronie są widać wszystkie bieżące szacowane koszty. Możesz użyć przycisków w Okienku akcji, aby pracować z wybranymi szacunkami. Pamiętaj, że nie można utworzyć nowego szacowania kosztów na stronie **Szacowanie kosztów**. Zamiast tego należy użyć okna dialogowego **Szacowanie kosztów** (**Koszt z wyładunkiem \> Zadania okresowe \> Szacowanie kosztów**) w sposób opisany wcześniej w tym artykule.

Na stronie **Szacowanie kosztów** pokazano sposób pochodnego kosztu szacowanego. Zawiera również szacowany z wyładunkiem dla każdego towaru. Szacowanie kosztów można zmodyfikować, zmieniając koszt i/lub walutę skojarzoną z różnymi towarami. Skojarzone koszty podróży można również modyfikować na poziomie podróży i na poziomie kontenera. Podczas korzystania z tej strony w celu zmodyfikowania kosztów wyświetlany jest monit o ponowne obliczanie szacowanych kosztów towarów w szacowaniu kosztów. Gdy jesteś gotowy, możesz użyć szacunków, aby zaktualizować koszt własny towarów w szablonie kosztów.

### <a name="information-on-the-header"></a>Informacje w nagłówku

W górnej części strony **Szacowanie kosztów** są opisane w poprzedniej sekcji ustawienia użyte do wygenerowania wybranego oszacowania kosztów. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>Ustawienia i przyciski na skróconej karcie Wiersze

Na skróconej karcie **Wierszy** znajduje się lista towarów uwzględnionych w bieżącym szacowaniu. W poniższej tabeli przedstawiono pole dostępne w nagłówku dla każdego wiersza.

| Pole | opis |
|---|---|
| Konto dostawcy | Konto dostawcy skojarzone z pozycją. |
| Numer towaru | Kod towaru. |
| Ilość | Liczba towarów używanych do określenia kosztu. |
| Koszt własny | Koszt kosztowy zgodnie z umową handlową. Ta wartość jest pokazana w lokalnej walucie. |
| Miara | Pojedyncza miara. Jednostka określona dla odpowiedniego wydanego produktu. |
| Koszty szacowane z wyładunkiem | Szacowany koszt z wyładunkiem dla ilości całkowitej. |
| Na jednostkę | Szacowany koszt wyładunku podzielony przez ilość. |
| (Inne wymiary) | W zależności od wymiarów wybranych do pokazania mogą zostać wyświetlane dodatkowe kolumny informacji o każdym towarze. |

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na pasku narzędzi na skróconej karcie **Wiersze**.

| Przycisk | opis |
|---|---|
| Dodawanie | Dodaj pozycje do szacowania kosztów. Po dodaniu elementów należy wybrać polecenie **Oblicz ponownie** w okienku akcji. |
| Usuń | Usuwanie pozycji z szacowania kosztów. Po usunięciu elementów należy wybrać polecenie **Oblicz ponownie** w okienku akcji. |
| Koszty podróży | Otwórz stronę, na której można wyświetlać i edytować różne typy kosztów podróży dla towaru. |
| Zapasy \> Wyświetl wymiary | Powoduje otwarcie okna dialogowego, w którym można dodawać kolumny wymiarów do siatki lub usuwać kolumny. |

### <a name="settings-on-the-general-fasttab"></a>Ustawienia na skróconej karcie Ogólne

Na skróconej karcie **Ogólne** są dostępne szczegóły dotyczące pozycji aktualnie wybranej na skróconej karcie **Wiersze**. Większość tych informacji jest powtarzana na skróconej karcie **Wiersze** i można ją edytować w obu tych miejscach. Jednak dodatkowe szczegóły są również dostępne tutaj. Wartości dodatkowych pól są oparte na ustawieniach odpowiedniego zwolnionego produktu.

### <a name="settings-on-the-dimension-fasttab"></a>Ustawienia na skróconej karcie Wymiar

Skrócona karta **Wymiar** zawiera wartości wszystkich dostępnych wymiarów magazynowych dla towaru wybranego na skróconej karcie **Wiersze**, niezależnie od wymiarów, które zostały wybrane do wyświetlenia. Wyświetlane tutaj wartości pochodzą z odpowiedniego szablonu szacowania kosztów. Są one opcjonalne w szablonie szacowania kosztów.

### <a name="buttons-on-the-action-pane"></a>Przyciski w okienku akcji

Za pomocą przycisków w okienku akcji na stronie **Szacowanie kosztów** można pracować z wybranym szacowaniem kosztów. W poniższej tabeli przedstawiono dostępne przyciski.

| Akcja | opis |
|---|---|
| Zapytanie dotyczące kosztu | Umożliwia wyświetlenie wszystkich kosztów podróży. W razie potrzeby można wyświetlić koszty na poziomie pojedynczego towaru. |
| Aktualizuj koszt standardowy | <p>Zaktualizuj koszt standardowy przy użyciu domyślnej wersji ceny zdefiniowanej na stronie **Parametry Koszt z wyładunkiem**. Tę wersję można zastąpić.</p><p>**Uwaga:** Jeśli przedmiot ma kilka wymiarów (na przykład różne rozmiary, kolory i konfiguracje), ale te wymiary nie zostały wybrane do oszacowania, system utworzy oczekującą cenę dla każdej kombinacji.</p><p>**Ważne:** Podział ceny jest tworzony i służy do określania standardowego odchylenia kosztów według kosztów z wyładunkiem.</p> |
| Koszty podróży | Umożliwia wyświetlanie i edytowanie kosztów podróży dla wszystkich towarów w wysyłce. |
| Oblicz ponownie | Zaktualizuj szacowane koszty ziemne po zaktualizowaniu, dodaniu lub usunięciu kosztów podróży. |
| Zablokuj | Zablokuj rekord szacowania kosztów, aby nie wprowadzać kolejnych zmian. |

## <a name="item-cost-price-update"></a>Aktualizacja kosztu własnego pozycji

W zadaniu okresowym **Aktualizacja ceny kosztu przedmiotu** są aktualizowane wszystkie oszacowania kosztów zgodne z filtrami ustawionymi podczas uruchamiania zadania. Efekt jest podobny do skutku wybrania opcji **Aktualizuj koszt standardowy** w okienku akcji dla pojedynczego szacowania. W tym przypadku jednak aktualizacja dotyczy wszystkich pasujących oszacowań.

Aby uruchomić zadanie okresowe, wykonaj następujące kroki.

1. Przejdź do **Koszt z wyładunkiem \> Zadania okresowe \> Aktualizacja ceny kosztu przedmiotu**.
1. W oknie dialogowym **Aktualizacja kosztu zakupu** z oszacowania ustaw w razie potrzeby następujące pola, aby ograniczyć zakres aktualizacji:

    - **Wersja** — aktualizowane są tylko szacowania, w których jest określonej wersji ceny.
    - **Miejsce** — aktualizowane są tylko szacowania, w których jest określone miejsce.
    - **szablon kosztu** — aktualizowane są tylko szacowania, w których jest określony szablon.
    - **Do portu** — Aktualizuj tylko szacunki, które używają określonego portu „do”.
    - **Data szacowania** — aktualizowane są tylko szacowania z podaną datą.

1. Ustaw opcje w **Rekordy do uwzględnienia** i **Uruchom w tle**, jak zwykłe w przypadku zadań okresowych.
1. Wybierz przycisk **OK**, aby uruchomić zadanie.

> [!NOTE]
> To zadanie okresowe będzie wykonywane pomyślnie, pod warunkiem że dostępne są następujące informacje:
>
> - Dla każdego odpowiedniego produktu musi być zdefiniowana **Długość brutto**, **Szerokość brutto** i **Wysokość brutto**.
> - Dla każdego odpowiedniego dostawcy musi być zdefiniowany **Port od**.

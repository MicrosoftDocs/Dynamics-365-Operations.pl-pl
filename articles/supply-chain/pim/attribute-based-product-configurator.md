---
title: Ceny sprzedaży oparte na atrybutach dla konfiguracji produktu opartej na ograniczeniu
description: W tym temacie opisano sposób budowania modeli cen sprzedaży z cenami sprzedaży na podstawie składników i atrybutów, a nie na fizycznej liście składowej (BOM) i marszrucie.
author: sorenva
manager: tfehr
ms.date: 10/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2020-08-17
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: cba4b1eac33ae53e214297728c1cdf2710ebd9d9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007923"
---
# <a name="attribute-based-sales-prices-for-constraint-based-product-configuration"></a>Ceny sprzedaży oparte na atrybutach dla konfiguracji produktu opartej na ograniczeniu

W tym temacie opisano sposób budowania modeli cen sprzedaży z cenami sprzedaży na podstawie składników i atrybutów, a nie na fizycznej liście składowej (BOM) i marszrucie. Można utworzyć kilka modeli cen sprzedaży dla każdego modelu konfiguracji produktu.

## <a name="set-relevant-product-information-management-parameters"></a>Ustawianie istotnych parametrów zarządzania informacjami o produktach

Przed rozpoczęciem konstruowania modeli ceny należy zdefiniować domyślną walutę używaną podczas konstruowania modeli cen sprzedaży. Można również określić, czy dołączyć plik Microsoft Excel z podziałem ceny wszystkich wierszy zamówień i ofert. Podział cen umożliwi udostępnianie klientom szczegółowych informacji o sposób obliczania ceny sprzedaży dla skonfigurowanego produktu.

Aby określić walutę domyślną:

1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Parametry modułu Zarządzanie informacjami o produktach**.
1. Otwórz kartę **Modele konfiguracji produktów oparte na ograniczeniach**.
1. Otwórz listę rozwijaną **Waluta domyślna** i wybierz walutę.

    ![Określanie domyślnej waluty dla konfiguracji produktu opartej na ograniczeniu](media/prod-config-currency.png "Określanie domyślnej waluty dla konfiguracji produktu opartej na ograniczeniu")

1. Jeśli chcesz dołączyć plik programu Excel z podziałem cen dla wszystkich wierszy zamówień lub ofert, w sekcji **Model cen** ustaw opcję **Dołącz** na *Tak*.

## <a name="build-your-sales-price-models"></a><a name="build-price-model"></a>Budowanie modeli cen sprzedaży

Aby utworzyć model cen sprzedaży:

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Wybierz model konfiguracji produktu docelowego.
1. W okienku akcji otwórz kartę **Model** i z grupy **Ustawienia** wybierz pozycję **Modele cen**.
1. Zostanie otwarta strona **Modele cen**.
1. Wybierz model cen lub dodaj nowy do tabeli.
1. Wybierz opcję **Edytuj**, aby otworzyć stronę edycji dla wybranego modelu, która oferuje następujące funkcje:
    - W nagłówku formularza wyświetlana jest waluta domyślna i można dodawać nowe waluty do ustawień ceny.
    - W lewym okienku są wyświetlane wszystkie składniki i wymagania użytkownika dotyczące modelu produktu. Każdy węzeł w drzewie modelu produktu może mieć jedno wyrażenie ceny bazowej i opcjonalną liczbę reguł wyrażeń. Reguła wyrażenia składa się z warunku i wyrażenia, a każda reguła wyrażenia dotyczy opcji produktu, która ułatwia kontrolę ceny produktu.
    - Podczas tworzenia warunków i wyrażeń są dostępne te same operatory, co w przypadku obliczeń w modelu produktu. Edytor wyrażeń obsługuje zarówno warunki, jak i wyrażenia.
1. Wybierz węzeł w lewej kolumnie, a następnie skorzystaj z funkcji opisanych w poprzednim kroku, aby ustalić dla niego reguły cenowe (zob. przykład po tej procedurze). Powtórz ten krok dla każdego węzła w razie potrzeby.

W poniższym przykładzie przedstawiono cenę podstawową o stałej wartości 899,95 EUR, która może zostać zmodyfikowana przez co najmniej jedną z następujących pięciu reguł wyrażenia, w zależności od konfiguracji wybranej przez klienta:

- W przypadku białego wykończenia szafki odejmij 59,95 EUR.
- W przypadku ochrony narożnika dodaj 35,95 EUR.
- W przypadku osłony metalowej z przodu, dodaj 89,95 EUR.
- W przypadku wykończenia szafki rosewood dodaj 119,95 EUR.
- Dodaj 12,95 EUR dla każdej jednostki wysokości głośnika.

![Przykładowy model cen](media/prod-config-rules-example.png "Przykładowy model cen")

## <a name="add-support-for-multiple-currencies"></a>Dodawanie obsługi wielu walut

Po sprzedaniu konfigurowalnego produktu system sprawdza, czy ceny zostały ustawione jawnie w walucie odbiorcy. Jeśli tak, używane są jawne wartości. Jeśli nie, system używa kursów wymiany walut, które zostały ustalone dla firmy obsługującej sprzedaż, do przeliczenia wartości waluty domyślnej na walutę odbiorcy.

Aby dodać ceny jawne w walucie dodatkowej:

1. Otwórz stronę edycji modelu ceny, zgodnie z opisem w temacie [Tworzenie modeli cen sprzedaży](#build-price-model).
1. Wybierz przycisk **Dodaj** w nagłówku modelu cen, aby otworzyć rozwijane okno dialogowe **Waluty**, w którym znajduje się lista dostępnych walut.
1. Wybierz walutę, którą chcesz dodać w rozwijanym oknie dialogowym **Waluty**, a następnie kliknij przycisk **OK**.
1. Lista rozwijana **Bieżąca waluta** zawiera obecnie dodaną walutę oraz wszystkie inne waluty, które mogły zostać wcześniej dodane. Wybierz nową walutę i zwróć uwagę, że tabela w sekcji **Reguły wyrażeń** zawiera teraz dwa pola wyrażeń:
    - **Wyrażenie** — zawiera wyrażenie (lub wartość stałą) na potrzeby wyszukiwania ceny w walucie aktualnie wybranej dla opcji **Waluta bieżąca**.
    - **Wyrażenie domyślne** — zawiera wyrażenie (lub wartość stałą) na potrzeby wyszukiwania ceny w walucie domyślnej (widocznej w polu **Waluta bieżąca**).

    > [!NOTE]
    > Pole **Warunek** dla reguł wyrażeń „należy” do waluty domyślnej, co oznacza, że nie można modyfikować warunku innych walut. Nie można również dodawać nowych reguł wyrażeń, jeśli jako walutę bieżącą wybrano walutę inną niż **Waluta bieżąca**.
1. Przeprowadź edycję wartości w kolumnie **Wyrażenie** w zależności od wymagań dla bieżącej waluty.

W poniższym przykładzie walutą domyślną jest _EUR_ a _USD_ dodano jako walutę dodatkową.

![Przykład modelu z wieloma walutami](media/prod-config-rules-currency-example.png "Przykład modelu z wieloma walutami")

> [!NOTE]
> Nie można dodać reguł wyrażeń, które są unikatowe w walucie innej niż domyślna. Aby utworzyć reguły wyrażeń, które byłyby odpowiednie tylko dla waluty innej niż waluta domyślna, ustaw wyrażenie ceny dla domyślnej waluty na zero. Następnie ustaw odpowiednie wyrażenie dla waluty innej niż domyślna.

## <a name="test-your-price-model"></a>Testowanie modelu cen

Aby sprawdzić, jak działają ceny sprzedaży w sesji konfiguracji, otwórz stronę edycji dla modelu cen, zgodnie z opisem w temacie [Tworzenie modeli cen sprzedaży](#build-price-model), a następnie w okienku akcji wybierz opcję **Test**. Zostanie otwarte okno dialogowe **Testuj model produktu**, w którym można wykonać następujące czynności:

- Skorzystaj z ustawień konfiguracji dostępnych tutaj, aby wybrać opcje produktu, a następnie zobaczyć, jak mają wpływ na wartość wyświetloną w sekcji **Cena i data wysyłki**.
- Wybierz opcję **Wyświetl podział cen**, aby pobrać dokument programu Excel zawierający szczegóły dotyczące sposobu obliczenia ceny.

![Testowanie modelu produktu](media/prod-config-test.png "Testowanie modelu produktu")

Pobrany arkusz kalkulacyjny zawiera zarówno wartość bezwzględną, jak i udział jako wartość procentową każdego aktywnego elementu ceny. Jeśli ustawiono opcję **Dołącz** modelu ceny na stronie **Parametry zarządzania informacjami o produktach**, ten arkusz programu Excel zostanie dołączony do wiersza zamówienia lub oferty.

![Arkusz kalkulacyjny programu Excel zawierający podział cen](media/prod-config-excel-example.png "Arkusz kalkulacyjny programu Excel zawierający podział cen")

## <a name="set-up-selection-criteria-for-price-models"></a>Ustawianie kryteriów wyboru dla modeli cen

Jeśli modele cen są dostępne, należy wybrać co najmniej jedno kryterium wyboru w celu pobrania modelu ceny podczas konfigurowania oferty lub zamówienia. W tym celu należy skonfigurować co najmniej jedną kwerendę. W połączeniu z uzgodnionymi modelami cen sprzedaży kwerendy zapewniają bardzo elastyczną określanie cen sprzedaży dla określonych odbiorców, regionów, okresów i innych kryteriów.

Aby ustawić kryteria wyboru dla modeli cen:

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Wybierz model konfiguracji produktu docelowego.
1. W okienku akcji otwórz kartę **Model** i z grupy **Ustawienia** wybierz pozycję **Kryteria modelu cen**. Zostanie otwarta strona **Kryteria modelu cen**.
1. Jeśli wymagany wiersz kwerendy już nie istnieje, wybierz opcję **Nowy** w okienku akcji, aby dodać nowy wiersz do tabeli i wybrać dla niego następujące ustawienia:
    - **Nazwa** – wprowadź nazwę tego wiersza.
    - **Opis** — krótko opisz kwerendę i jej przeznaczenie.
    - **Model cen** — wybierz [modelu cen](#build-price-model) (z bieżącego modelu konfiguracji), który będzie stosowany po wyzwoleniu.
    - **Typ zamówienia** — wybierz typu zamówienia, w którym będzie stosowana kwerenda.
    - **Obowiązuje od** — określ pierwszy dzień, w którym zostanie zastosowana kwerenda.
    - **Data ważności** — określa ostatni dzień stosowanie kwerendy.

    ![Kryteria modelu ceny](media/prod-config-price-model-criteria.png "Kryteria modelu ceny")

1. Wybierz wiersz kwerendy, którą chcesz zdefiniować, a następnie wybierz opcję **Edytuj** w **okienku akcji**. Otworzy się okno dialogowe konstruktora zapytań. Działa jak większość konstruktorów kwerend w Supply Chain Management. Użyj go w celu zdefiniowania warunków, pod jakimi należy zastosować model cen dla wybranego wiersza.

1. Powtórz kroki 4–5 dla każdej wymaganej kwerendy.
    > [!TIP]
    > Można oszczędzić czas, kopiując istniejący wiersz już podobny do nowego, który należy dodać. W tym celu wybierz wiersz docelowy, a następnie w okienku akcji wybierz opcję **Duplikuj**.

1. Po zakończeniu konfigurowania kryteriów umieść je w odpowiedniej kolejność na liście **Kryteria modelu cen**. Aby zmienić pozycję wiersza, zaznacz wiersz, a następnie w okienku akcji wybierz **W górę** lub **W dół**.

    > [!IMPORTANT]
    > W czasie konfigurowania system rozpoczyna wyszukiwanie od góry listy i używa pierwszej kwerendy zgodnej z danymi w ofercie lub wierszu zamówienia. Dlatego należy umieścić na początku najbardziej szczegółowe kwerendy. Jeżeli umieścisz kwerendę ogólną na początku listy zostanie użyta nawet wtedy, gdy istnieje kwerenda znajdująca się w dalszej kolejności na liście, przeznaczona dla określonego odbiorcy lub potencjalnego klienta w konfiguracji.

## <a name="set-attribute-based-sales-prices-for-the-product-model-version"></a>Ustawianie opartych na atrybutach cen sprzedaży dla wersji modelu produktu

Ostatnim krokiem jest określenie cen sprzedaży opartych na atrybutach dla wersji modelu produktu. W tym celu:

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Wybierz model konfiguracji produktu docelowego.
1. W okienku akcji otwórz kartę **Model** i z grupy **Szczegóły modelu produktu** wybierz pozycję **Wersje**.
1. Zostanie otwarta strona **Wersje**. Upewnij się, że **Metoda kalkulacji cen** jest ustawiona na wartość **Oparta na atrybutach**.
    ![Ustawianie metody kalkulacji cen na opartą na atrybutach](media/prod-config-versions.png "Ustawianie metody kalkulacji cen na opartą na atrybutach")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
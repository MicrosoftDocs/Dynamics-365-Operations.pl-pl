---
title: Atrybuty inżynieryjne i wyszukiwanie atrybutów inżynieryjnych
description: W tym temacie wyjaśniono, w jaki sposób można stosować atrybuty inżynieryjne w celu określenia wszystkich niestandardowych charakterystyk w celu zapewnienia, że wszystkie dane główne produktu mogą być zarejestrowane w systemie. Wyjaśniono również, w jaki sposób można stosować wyszukiwanie atrybutów inżynierskich w celu łatwego wyszukiwania produktów na podstawie zarejestrowanych charakterystyk.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductAttributeSearch, EngChgMaintainAttributeInheritance, EngChgAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 5a4f31af3f76c1af6a0f5546955e810bd1cca375
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435681"
---
# <a name="engineering-attributes-and-engineering-attribute-search"></a>Atrybuty inżynieryjne i wyszukiwanie atrybutów inżynieryjnych

[!include [banner](../includes/banner.md)]

Aby zapewnić, że wszystkie dane główne produktu mogą być rejestrowane w systemie, należy zastosować atrybuty inżynieryjne w celu określenia wszystkich niestandardowych charakterystyk. Pozwoli to stosować wyszukiwanie atrybutów inżynierskich w celu łatwego wyszukiwania produktów na podstawie zarejestrowanych charakterystyk.

## <a name="engineering-attributes"></a>Atrybuty projektowe

Zazwyczaj produkty inżynieryjne mają wiele cech i właściwości, które należy przechwycić. Mimo że niektóre właściwości można zarejestrować za pomocą standardowych pól produktu, można również utworzyć nowe właściwości technologiczne stosownie do potrzeb. Można zdefiniować własne *atrybuty inżynierskie* i uczynić je częścią definicji produktu.

### <a name="create-engineering-attributes-and-attribute-types"></a>Tworzenie atrybutów inżynieryjnych i typów atrybutów

Każdy atrybut inżynierski musi należeć do *typu atrybutu*. To wymaganie istnieje, ponieważ każdy atrybut musi mieć *typ danych* definiujący typy wartości, które może ono zawierać. Typem atrybutu inżynieryjnego może być standardowy typ (np. tekst niezależny, liczba całkowita lub liczba dziesiętna) lub typ niestandardowy (np. tekst zawierający określony zbiór wartości, z których można wybierać). Można użyć ponownie każdego typu atrybutu z dowolną liczbą atrybutów inżynierskich.

#### <a name="set-up-engineering-attribute-types"></a>Ustawianie typów atrybutów inżynieryjnych

Aby wyświetlić, utworzyć lub edytować typ atrybutu inżynierskiego, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie zmianami inżynieryjnymi \> Konfiguracja \> Atrybuty \> Typy atrybutów**.
1. Wybierz istniejący atrybut wpisz okienko listy lub wybierz opcję **Nowy** w okienku akcji, aby utworzyć nowy typ atrybutu.
1. Ustaw wartości w następujących polach:

    - **Typ atrybutu** – Wprowadź nazwę typu atrybutu.
    - **Typ** —  Wybierz standardowy typu danych (*Waluta*, *DataCzas*, *Dziesiętne*, *Liczba całkowita*, *Tekst*, *Wartość logiczna* lub *Odwołanie*).
    - **Lista stałych** — Ta opcja jest dostępna tylko wtedy, gdy w polu **Typ** ustawiono wartość *Tekst*. Aby określić określone wartości atrybutów tego typu, należy je skonfigurować na wartość *Tak*. W takim przypadku zostanie utworzona lista rozwijana. Należy użyć skróconej karty **Wartość** do ustalania wartości dostępnych dla danego typu atrybutu. Ustawienie tej opcji na *Nie* spowoduje, że użytkownicy będą mogli wprowadzać dowolne wartości. W takim przypadku zostanie utworzone pole wejściowe.
    - **Zakres wartości** — Ta opcja jest dostępna tylko w przypadku, gdy w polu **Typ** ustawiono wartość *Liczba całkowita*, *Dziesiętna* lub *Waluta*. Ustawienie tej opcji na wartość *Tak* spowoduje ustanowienie wartości minimalnych i maksymalnych, które będą akceptowane dla atrybutów tego typu. Skrócona karta **Zakres** umożliwia ustalenie wartości minimalnej i maksymalnej oraz (dla waluty) waluty stosowanej w odniesieniu do wprowadzonych limitów. Ustawienie tej opcji na *Nie* spowoduje akceptowanie dowolnych wartości. 
    - **Zakres wartości**  — To pole jest dostępne tylko w przypadku, gdy w polu  **Typ** ustawiono wartość *Liczba całkowita* lub *Dziesiętna*. Wybierz jednostkę miary stosowanego dla tego typu atrybutu. Jeśli jednostka nie jest wymagana, należy pozostawić to pole puste.

#### <a name="set-up-engineering-attributes"></a>Ustawianie atrybutów inżynieryjnych

Aby wyświetlić, utworzyć lub edytować atrybut inżynierski, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie zmianami inżynieryjnymi \> Konfiguracja \> Atrybuty \> Typy atrybutów**.
1. Wybierz istniejący atrybut w okienku listy lub wybierz opcję **Nowy** w okienku akcji, aby utworzyć nowy atrybut.
1. Ustaw wartości w następujących polach:

    - **Nazwa** – wprowadź nazwę dla atrybutu. Nazwa ta pojawia się tylko na stronie **Atrybuty inżynierskie**. W każdym innym miejscu w systemie wartość pola **przyjazna nazwa** jest zwykle wyświetlana w celu identyfikacji atrybutu.
    - **Typ atrybutu** — umożliwia wybór typu atrybutu zdefiniowanego w poprzedniej sekcji.
    - **Przyjazna nazwa** — umożliwia wprowadzenie nazwy, która będzie identyfikować atrybut w systemie (z wyjątkiem **strony z atrybutami inżynierskimi**). 
    - **Opis** – wprowadź opis atrybutu.
    - **Tekst pomocowy** — umożliwia wprowadzenie tekstu pomocowego informującego o tym, jakie są atrybuty dla innych użytkowników.
    - **Wartość domyślna** — umożliwia wprowadzenie wartości domyślnej dla atrybutu. Przedstawione opcje zależą od wybranego typu atrybutu.
    - **Waluta** — Jeśli wybrany typ atrybutu to waluta, należy wybrać walutę, która będzie akceptować atrybut, i wyświetlić wartości w polu.

1. Jeśli wybrany typ atrybutu jest liczbą całkowitą lub dziesiętną, pokazywany jest **zakres** na skróconej karcie. Na skróconej karcie ustaw następujące wymagane pola:

    - **Akcja tolerancji** — umożliwia wybór sposobu odpowiedzi systemu, jeśli użytkownik wprowadzi wartość spoza określonego zakresu. W przypadku wybrania opcji *Ostrzeżenie* zostanie wyświetlone ostrzeżenie, ale użytkownik będzie mógł zapisać wartość. Jeśli wybierzesz opcję *niedozwolone*, wyświetlane jest ostrzeżenie i nie będzie można zapisać wartości, dopóki użytkownik jej nie poprawi.
    - **Minimum** — umożliwia wprowadzenie minimalnej zalecanej lub zaakceptowanej wartości minimalnej.
    - **Maksimum** — umożliwia wprowadzenie maksymalnej zalecanej lub zaakceptowanej wartości.

### <a name="connect-engineering-attributes-to-an-engineering-product-category"></a>Łączenie atrybutów inżynieryjnych z kategorią produktów inżynierii

Niektóre atrybuty inżynieryjne dotyczą wszystkich produktów, natomiast inne są charakterystyczne dla poszczególnych produktów lub kategorii produktów. Na przykład atrybuty elektryczne nie są wymagane w przypadku produktów mechanicznych. Można więc skonfigurować *Kategorie produktów inżynieryjnych*. Kategoria produktów inżynierii określa zbiór atrybutów inżynieryjnych, które muszą być częścią definicji produktów należących do danej kategorii. Można również określić, które atrybuty inżynieryjne są wymagane i czy mają wartość domyślną.

Aby uzyskać więcej informacji na temat pracy z kategoriami produktów inżynieryjnych, w tym informacje o sposobach łączenia atrybutów z kategoriami, zapoznaj się z [Wersjami inżynieryjnymi i kategoriami produktów inżynieryjnych](engineering-versions-product-category.md).

### <a name="set-values-for-engineering-attributes"></a>Ustawienie wartości atrybutów inżynieryjnych

Atrybuty inżynieryjne połączone z kategorią produktów inżynierii są prezentowane podczas tworzenia nowego produktu inżynieryjnego, który jest oparty na tej kategorii. W tym momencie można określić wartości atrybutów. Później wartości te można zmienić na stronie **wersji inżynierskiej** lub w ramach zarządzania zmianami inżynieryjnymi w ramach inżynieryjnego żądania zmiany. Aby uzyskać więcej informacji, zobacz [Zarządzanie zmianami dotyczącymi produktów inżynieryjnych](engineering-change-management.md).

### <a name="create-an-engineering-product"></a>Tworzenie produktu inżynieryjnego

Aby utworzyć produkt inżynieryjny, otwórz stronę **uwolnione produkty**. Następnie w okienku akcji na karcie **Produkt** w grupie **Nowy** wybierz opcję **Atrybuty produktu**.

Należy określić kategorię inżynieryjną, do której należy dany produkt. Kategoria ustawi wszystkie wartości domyślne i charakterystyki produktu. Spowoduje to również ustawienie atrybutów dotyczących produktu. Po wybraniu kategorii wartości zostaną ustawione dla atrybutów. Następnie można zmodyfikować te wartości.

## <a name="search-for-products-by-using-engineering-attribute-values"></a>Wyszukiwanie produktów przy użyciu wartości atrybutów inżynierskich

Funkcja wyszukiwania atrybutów inżynieryjnych umożliwia znajdowanie produktów przez wyszukiwanie wartości ich atrybutów inżynieryjnych. Dzięki temu można łatwo znajdować produkty inżynieryjne na podstawie ich charakterystyki. Można przeszukiwać produkty należące do kategorii produktów inżynieryjnych lub przeszukiwać wszystkie produkty.

Wyszukiwanie jest dostępne na stronach danych głównych produktu oraz na podstawie towarów transakcyjnych w systemie, takich jak zamówienia sprzedaży. W przypadku towaru transakcyjnego można skorzystać ze **strony wyszukiwania atrybutów inżynierskich** w celu wyszukania produktu. Następnie można skorzystać z przycisku **Dodaj jako nowy wiersz**, aby dodać produkt do wierszy zamówienia sprzedaży. Produkty z wyników wyszukiwania można również dodawać bezpośrednio do zamówienia.

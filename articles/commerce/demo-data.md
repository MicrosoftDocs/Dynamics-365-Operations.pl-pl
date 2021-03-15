---
title: Układy ekranu danych demonstracyjnych w aplikacjach Modern POS (MPOS) i Cloud POS
description: Ten temat zawiera informacje o układach ekranu zawartych w zestawie danych demonstracyjnych dla doświadczeń punktu sprzedaży w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: e55db57089c8ea5bd3def25d79d9c65a3165526c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982722"
---
# <a name="demo-data-screen-layouts-in-modern-pos-mpos-and-cloud-pos"></a>Układy ekranu danych demonstracyjnych w aplikacjach Modern POS (MPOS) i Cloud POS

[!include [banner](includes/banner.md)]

Ten temat zawiera informacje o układach ekranu zawartych w zestawie danych demonstracyjnych dla doświadczeń punktu sprzedaży w rozwiązaniu Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Przykładowe układy ekranu zawarte w danych demonstracyjnych Commerce obejmują zawartość zoptymalizowaną dla różnych segmentów sprzedaży detalicznej, ról pracowników sklepu i urządzeń. Jeden układ może zawierać kilka rozmiarów układu i kombinacji siatek przycisków, aby zapewnić możliwość obsługi, gdy pracownicy sklepu zmienią urządzenia i stacje. W tym temacie omówiono różnice między tymi układami, operacja, jakie udostępniają i ogólne zapewniane doświadczenia.

![Układy danych demonstracyjnych działające między urządzeniami](../commerce/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a>Struktura identyfikatora układu ekranu

Aby znaleźć układy ekranu w rozwiązaniu Retail, przejdź do **Retail i Commerce** \> **Ustawienia kanału** \> **Ustawienia punktu sprzedaży** \> **Punkt sprzedaży** \> **Układy ekranu**.

![Strona układu ekranu](../commerce/media/demo-screen-layouts-fig-2-1.png)

Identyfikatory układu ekranu mogą mieć maksymalnie 10 znaków. Identyfikator to ciąg składający się z trzech informacji w następującej kolejności:

1. Firma
2. Wersja układu
3. Osoba

### <a name="company"></a>Firma

| List | Firma         |
|--------|-----------------|
| A      | Adventure Works |
| F      | Fabrikam        |
| F      | Contoso         |

### <a name="layout-version"></a>Wersja układu

| Numer wersji | opis                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| 3              | Wersja podstawowa, która obsługuje wiele ekranów dla różnych urządzeń i współczynników proporcji |
| 3.1            | Wersja podstawowa, która oferuje dodatkową obsługę panelu **Rekomendowane produkty**        |
| 4              | Rozszerzona wersja aktualizacji układu Fabrikam                                  |

### <a name="persona"></a>Osoba

| Skrót | Osoba       | Zawartość |
|--------------|---------------|----------|
| CSH          | Kasjer       | Układy kasjera zawierają wszystkie operacje dotyczące transakcji, takie jak zamówienia odbiorców, zwroty, rabaty, unieważnienia i karty upominkowe. Te układy zawierają także codzienne zadania do zarządzania zapasami, takie jak sprawdzenia ceny, wyszukiwanie zapasów i inwentaryzację. Dostępne jest także podstawowe zarządzanie zmianami dla kwot początkowych, zawieszania zmian i zegara. |
| MGR          | Kierownik sklepu | Układy kierownika sklepu obejmują wszystkie operacje dotyczące transakcji dostępne w układach Kasjer, ale także zmiany podatków. Te układy zawierają także codzienne zadania do zarządzania zapasami, takie jak sprawdzenia ceny, wyszukiwanie zapasów i inwentaryzację. Dostępne jest zarządzanie zmianami na potrzeby rozpoczynania zawieszania i zamykania zmiany. Ponadto układy zawierają operacje z użyciem szuflady dla wpisów, usunięć, deklaracji środków płatniczych oraz przekazywania pieniędzy do sejfu i banku. I wreszcie układy obejmują dostęp do raportu o wynikach i umożliwiają drukowanie częściowych i końcowych raportów sprzedaży. |
| STK          | Magazynier   | Układy Magazynier są zoptymalizowane pod kątem zarządzania zapasami. Umożliwiają dostęp do codziennych zadań sprawdzania ceny, wyszukiwania zapasów, pobieranie i przyjęcie, inwentaryzację i dekompletację zestawu. Układy te udostępniają podstawowe operacje zmiany dla zegara i zawieszania zmian. Mimo że te układy są przeznaczone głównie do zadań zaplecza, magazynierzy mogą wykonywać te same operacje co kasjerzy dla ekranów transakcji. |

### <a name="example-layout"></a>Układ przykładowy

Poniżej przedstawiono przykładowy identyfikator układu ekranu dla firmy Fabrikam, wersja 4 układu i stanowiska Kierownik sklepu:

F4MGR

Poniższa ilustracja przedstawia przykładowy ekran powitalny kierownika sklepu firmy Fabrikam.

![Ekran powitalny dla kierownika sklepu firmy Fabrikam](../commerce/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a>Rozmiary układów

### <a name="full-vs-compact-layouts"></a>Układ pełny a kompaktowy

Układ ekranu może mieć konfiguracje dla urządzeń pełnoekranowych i kompaktowych. Dlatego można przypisać użytkownika do jednego układu ekranu, który będzie działał w urządzeniach o różnych rozmiarach i typach znajdujących się w sklepie.

- **Modern POS - Pełna wersja** — Pełne układy zazwyczaj najlepiej nadają się do większych ekranów, takich jak w monitorach komputerów stacjonarnych i tabletach. Użytkownicy mogą wybrać elementy interfejsu użytkownika zawarte w układzie, określić rozmiar i umieszczenie tych elementów oraz skonfigurować ich szczegółowe właściwości. Układy pełne obsługują konfiguracje poziome i pionowe.
- **Modern POS - Wersja kompaktowa** — Układy kompaktowe zazwyczaj najlepiej nadają się do telefonów lub małych tabletów. Możliwości projektowania są ograniczone do urządzeń kompaktowych. Użytkownicy mogą konfigurować kolumny i pola okienka pokwitowania i sum.

### <a name="screen-resolutions-that-are-provided"></a>Dostępne rozdzielczości ekranu

Poniższa tabela przedstawia rozmiary układu dostępne dla typowych rozdzielczości ekranu.

| Typ układu | Rozdzielczość | Współczynnik proporcji | Docelowy wyświetlacz          |
|-------------|------------|--------------|-------------------------|
| Kompaktowanie\*   | 480 × 853  | 16:9         | Telefony                  |
| Pełny        | 1024 × 768 | 4:3          | Tablety                 |
| Pełny\*      | 1280 × 720 | 16:9         | Tablety                 |
| Pełny        | 1366 × 768 | 16:9         | Tablety, większe ekrany |
| Pełny        | 1440 × 960 | 3:2          | Tablety, większe ekrany |
| Pełny\*      | 1536 x 864 | 16:9         | Tablety, większe ekrany |

\* Te dodatkowe rozmiary układów są dostępne tylko w układach firmy Adventure Works i Fabrikam.

> [!TIP]
> Punkt sprzedaży automatycznie wybiera rozmiary układu na podstawie najbliższego rozmiaru dostępnego dla rozdzielczości ekranu okna bieżącej aplikacji. Aby znaleźć aktualnie używany identyfikator układu ekranu i rozdzielczość układu, w module Modern POS (MPOS) lub Retail Cloud POS (CPOS) otwórz stronę **Ustawienia** i sprawdź informacje w sekcji **Informacje o sesji**. Możesz także zobaczyć rzeczywistą rozdzielczość okna dla bieżącej aplikacji lub ramki przeglądarki. Po uzyskaniu tych informacji można znaleźć źródło zawartości układu przechodząc do okna **Ustawienia kanału** \> **Ustawienia punktu sprzedaży** \> **Punkt sprzedaży** \> **Układy ekranu**.

![Układy ekranu i rozdzielczości/rozmiary układu w rozwiązaniu Commerce i punkcie sprzedaży](../commerce/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a>Firmy i marki

Każda firma fikcyjna odnosi się do innego segmentu sprzedaży detalicznej i zawiera katalogi produktów dostosowane do rynku firmy. Każda firma stosuje unikatowe elementy wizualne marki związane z jej produktami. Elementy dotyczące marki obejmują kolor akcentu, ciemny lub jasny motyw i powiązane zdjęcia, zapewniające realizm doświadczeń.

### <a name="company-segment-and-visual-characteristics"></a>Segment firmy i charakterystyka wizualna

| Firma         | Lokalizacja | Segment        | Akcent | Motyw |
|-----------------|----------|----------------|--------|-------|
| Adventure Works | Seattle  | Artykuły sportowe | Niebieski   | Ciemny  |
| Fabrikam        | San Francisco  | Moda        | Zielony  | Jasny |
| Contoso         | Boston   | Elektronika    | Czerwony    | Ciemny  |

> [!NOTE]
> Adventure Works i Fabrikam to dwie marki flagowe. Firma Contoso jest dostępna, ale nie dostarczono wszystkich układów.

Poniższe ilustracje przedstawiają przykłady strony powitalnej i strony transakcji dla trzech fikcyjnych firm.

### <a name="adventure-works"></a>Adventure Works

![Stron powitalna danych demonstracyjnych dla firmy Adventure Works](../commerce/media/demo-screen-layouts-fig-4-1a.png)

![Stron transakcji danych demonstracyjnych dla firmy Adventure Works](../commerce/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a>Fabrikam

![Stron powitalna danych demonstracyjnych dla firmy Fabrikam](../commerce/media/demo-screen-layouts-fig-4-2a.png)

![Stron transakcji danych demonstracyjnych dla firmy Fabrikam](../commerce/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a>Contoso

![Układy danych demonstracyjnych dla firmy Contoso](../commerce/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a>Macierz logowania użytkowników

Użytkownikom udostępniono różne układy ekranu. Korzystając z poniższej tabeli, można uzyskać dostęp do dowolnego ekranu. Wystarczy zalogować się, używając odpowiedniego identyfikatora operatora.

| Firma         | Identyfikator układu ekranu | Osoba       | Identyfikatory operatora           |
|-----------------|------------------|---------------|------------------------|
| Adventure Works | A3MGR            | Kierownik sklepu | 000154, 000137, 000073 |
| Adventure Works | A3CSH            | Kasjer       | 000150, 000175, 000165 |
| Adventure Works | A3STK            | Magazynier   | 000155, 000181, 000152 |
| Fabrikam        | F4MGR            | Kierownik sklepu | 000160, 000713         |
| Fabrikam        | F3CSH            | Kasjer       | 000161, 000113, 000114 |
| Fabrikam        | F3STK            | Magazynier   | 000164, 000112, 000123 |
| Contoso         | C3MGR            | Kierownik sklepu | 000100, 000111         |
| Contoso         | C3CSH            | Kasjer       | 000110, 000120         |
| Contoso         | Nie dotyczy   | Magazynier   | Nie dotyczy         |

> [!TIP]
> Aby uzyskać najlepsze wyniki, uaktywnij kasę w odpowiedniej lokalizacji sklepu i ustaw firmę na dotyczącą osoby, której konta chcesz używać po zalogowaniu. Zapewnia to zgodność profilu wizualnego i obrazów marki z doświadczeniem. Jeżeli na przykład chcesz zobaczyć układ Fabrikam dla kasjera, uaktywnij kasę w sklepie w Houston.

<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail and Commerce \> Channel setup \> POS setup \> POS \> Images**. -->

<!-- ![Images in Dynamics 365 Commerce](../commerce/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../commerce/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->


[!INCLUDE[footer-include](../includes/footer-banner.md)]
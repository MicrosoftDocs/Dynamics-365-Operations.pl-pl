---
title: Hierarchia wymiarów
description: Ten temat zawiera informacje o hierarchiach wymiarów. Hierarchie wymiarów służą do definiowania struktury raportowania, zasad kosztów i ustawień zabezpieczeń w module Rachunek kosztów.
author: AndersGirke
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 40ae7b61537cdcd1934056b9e289f342e96b57d3eebe5a6e713b2db91310ed9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766987"
---
# <a name="dimension-hierarchy"></a>Hierarchia wymiarów

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o hierarchiach wymiarów. Hierarchie wymiarów służą do definiowania struktury raportowania, zasad kosztów i ustawień zabezpieczeń w module Rachunek kosztów.  

## <a name="overview"></a>Przegląd

Hierarchie wymiarów są używane w różnych miejscach w rachunku kosztów. Hierarchia wymiarów pozwala zdefiniować następujące informacje:

-  Struktura raportowania pasująca do wymagań organizacji
-  Zasady kosztów
-  Ustawienia zabezpieczeń

Oto przykład hierarchii wymiarów.

![Przykład hierarchii wymiarów.](./media/dimension-hierarchy.png)

Hierarchię wymiarów można utworzyć dla następujących typów wymiarów:

-  Wymiary składników kosztów
-  Wymiary obiektów kosztów
-  Wymiary statystyczne

> [!NOTE]
> - Można utworzyć wiele hierarchii wymiarów dla tego samego wymiaru, jeśli są wymagane różne perspektywy.
> - Hierarchię wymiarów można skojarzyć tylko z jednym wymiarem.
> - Hierarchia wymiarów może mieć nieograniczoną liczbę poziomów w swojej strukturze. Wszystkie poziomy będą dostępne w obszarze roboczym **Kontrola kosztów**. Jeśli używasz programu Microsoft Excel lub Microsoft Power BI na potrzeby sprawozdawczości, eksportowanych jest tylko pierwszych 15 poziomów hierarchii wymiarów. To ograniczenie istnieje, ponieważ programy Excel i Power BI wymagają ustalonego schematu.
> - Hierarchia wymiarów nie ma daty obowiązywania. Dlatego wszelkie zmiany w hierarchii wymiarów są natychmiast zapisywane w rekordzie i nie można porównać stanów sprzed daty modyfikacji i po dacie modyfikacji.

## <a name="dimension-hierarchy-type"></a>Typ hierarchii wymiarów

Tworząc nową hierarchię wymiarów, trzeba wybrać typ hierarchii. Wybierz kolejno opcje **Rachunek kosztów** > **Wymiary** > **Hierarchie wymiarów**. Kliknij przycisk **Nowy** i wybierz typ hierarchii wymiarów. Można wybrać opcję **Hierarchia kategoryzacji wymiarów** lub **Hierarchia klasyfikacji wymiarów**.

### <a name="dimension-categorization-hierarchy"></a>Hierarchia kategoryzacji wymiarów

Typ **Hierarchia kategoryzacji wymiarów** jest używany na potrzeby sprawozdawczości. Obsługuje tylko wymiary składników kosztów. Po wybraniu tego typu obowiązują następujące reguły:

-  Element członkowski wymiaru może być skojarzony więcej niż jeden raz w strukturze hierarchii.
-  Element członkowski wymiaru składnika kosztów można umieścić w różnych węzłach, przypisując zachowanie kosztów do węzła liścia.

### <a name="dimension-classification-hierarchy"></a>Hierarchia klasyfikacji wymiarów

Typ **Hierarchia klasyfikacji wymiarów** jest używany do definiowania reguł i na potrzeby sprawozdawczości. Obsługuje wszystkie wymiary, takie jak obiekty kosztów, składniki kosztów i wymiary statystyczne. Po wybraniu tego typu element członkowski wymiaru może być skojarzony tylko jeden raz w strukturze hierarchii.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>Tworzenie i obsługa hierarchii wymiarów

Hierarchia wymiarów jest tworzona jako struktura drzewa z relacjami węzłów i węzłów liścia.

-  Węzeł może mieć 1:_n_ podwęzłów.
-  Węzeł nie mieć przypisanych równocześnie węzłów liścia i podwęzłów (węzłów podrzędnych).
-  Węzeł liścia można przypisać tylko na najniższym poziomie w hierarchii.

### <a name="example"></a>Przykład

Mała firma ma następującą strukturę organizacyjną, gdzie Finanse i Kadry to działy w pionie Administracja, a Montaż i Pakowanie to działy w pionie Produkcja.

![Przykład struktury organizacyjnej.](./media/dimension-hierarchy-org.png)

Wymiar obiektu kosztów reprezentuje wszystkie centra kosztów w organizacji.

- Wymiar obiektu kosztów
    - Centra kosztów

Wymiar obiektu kosztów reprezentujący wszystkie centra kosztów można skonfigurować w sposób pokazany poniżej.

| Centra kosztów | opis |
|--------------|-------------|
| CC001        | Zasoby ludzkie          |
| CC002        | Finanse     |
| CC003        | Podatek         |
| CC007        | AR/AP       |
| CC005        | Zestaw    |
| CC006        | Opakowanie   |

Wymiar składnika kosztu reprezentuje wszystkie składniki kosztów w organizacji.

- Wymiar składnika kosztu
    - Składniki kosztów

Wymiar składnika kosztów reprezentujący wszystkie składniki kosztów można skonfigurować w sposób pokazany poniżej.

| Składniki kosztów | opis |
|---------------|-------------|
| 10001         | Elektryczność |
| 10010         | Sprzątanie    |
| 10011         | Ogrzewanie     |
| 40001         | KWS        |

Hierarchię wymiarów spełniającą wymagania sprawozdawcze organizacji można skonfigurować w sposób pokazany poniżej.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar    | Nazwa typu hierarchii wymiarów      | Hierarchia list dostępu |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizacja             | Centra kosztów | Hierarchia klasyfikacji wymiarów | Nie                    |

Hierarchię wymiarów dla sprawozdawczości można skonfigurować w sposób pokazany poniżej.

**Zakresy elementów członkowskich wymiaru**

|   Węzły           |   Element członkowskiego wymiaru źródłowego   |   Element członkowski wymiaru docelowego   |
|-------------------|---------------------------|-------------------------|
| Organizacja      |                           |                         |
| &nbsp;&nbsp;Administrator         |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanse   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Zasoby ludzkie        | CC001                     | CC001                   |
| &nbsp;&nbsp;Produkcja    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Opakowanie | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Zestaw  | CC006                     | CC006                   |

Hierarchię wymiarów spełniającą wymóg zasady można skonfigurować w sposób pokazany poniżej.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar     | Nazwa typu hierarchii wymiarów      |
|--------------------------|---------------|------------------------------------|
| Zachowanie kosztów            | Składniki kosztów | Hierarchia klasyfikacji wymiarów |

Hierarchię wymiarów dla zasady można skonfigurować w sposób pokazany poniżej.

**Zakresy elementów członkowskich wymiaru**

|   Węzły           |   Element członkowskiego wymiaru źródłowego   |   Element członkowski wymiaru docelowego   |
|-------------------|---------------------------|-------------------------|
| Zachowanie kosztów     |                           |                         |
| &nbsp;&nbsp;Koszt stały    | 10001                     | 10011                   |
| &nbsp;&nbsp;Koszt zmienny | 40001                     | 40010                   |

> [!NOTE]
> W obszarze **Zakresy elementów członkowskich wymiaru** węzeł może zawierać 1:_n_ zakresów elementów członkowskich wymiaru. Można wstawić identyfikatory elementów członkowskich wymiaru, które jeszcze nie istnieje jako elementy członkowskie wymiaru. Ta funkcjonalność pozwala przygotować hierarchię na przyszłe potrzeby.  

### <a name="copy-a-hierarchy"></a>Kopiowanie hierarchii

Można skopiować bieżącą hierarchię wymiarów jako punkt wyjściowy dla nowej hierarchii wymiarów. Jest to przydatne, gdy chcesz porównywać poprzednią hierarchię wymiarów z nową hierarchią wymiarów.

### <a name="rearrange-nodes-in-a-hierarchy"></a>Zmiana rozmieszczenia węzłów w hierarchii

Węzeł można przenosić w górę i w dół w granicach jego bieżącego poziomu w strukturze. W ten sposób można zmienić kolejność węzłów na potrzeby raportowania w obszarze roboczym **Kontrola kosztów**.

Przenoszenie węzła do nowej lokalizacji w hierarchii odbywa się poprzez zaznaczenie węzła docelowego. Istnieją dwa sposoby przenoszenia węzłów:

- **Przenieś pod** — wybrany węzeł jest przenoszony z bieżącej pozycji w hierarchii i wstawiany **pod** wybranym węzłem docelowym.
- **Przenieś za** — wybrany węzeł jest przenoszony z bieżącej pozycji w hierarchii i wstawiany **za** wybranym węzłem docelowym na swoim poziomie w hierarchii.

> [!NOTE] 
> Kolejność węzłów nie jest zachowywana podczas eksportowania danych do programu Excel lub Power BI, ponieważ te narzędzia domyślnie używają alfanumerycznego porządku sortowania. Kolejność należy zmienić ręcznie.

## <a name="define-dimension-hierarchies-for-reporting"></a>Definiowanie hierarchii wymiarów dla raportowania

Hierarchie wymiarów są ważne w raportowaniu. Umożliwiają zdefiniowanie konkretnej struktury pasującej do danej organizacji. Agregacje wykonywane na poziomie węzła w hierarchii wymiarów umożliwiają zainteresowanym stronom na każdym poziomie organizacji wgląd w dane na wszystkich poziomach.

Hierarchie wymiarów są dostępne w następujących narzędziach sprawozdawczych. Ta funkcjonalność pomaga zagwarantować spójność w strukturze raportowania.

- Obszar roboczy **Kontrola kosztów** (urządzenie klienckie):

    - Kontrolowany przez konfigurację.

- Obszar roboczy **Kontrola kosztów** (aplikacja komórkowa):

    - Kontrolowany przez konfigurację.

- Program Excel

    - Zawiera opcję umożliwiającą wybór określonych hierarchii wymiarów dla definicji eksportu:

        - Jedna hierarchia wymiarów składników kosztów (wymagana)
        - Jedna hierarchia wymiarów obiektów kosztów (opcjonalna)
        - Jedna hierarchia wymiarów statystycznych (opcjonalna)

- Power BI:

    - Są dostępne wszystkie hierarchie wymiarów.
    
Jeśli tworzysz raporty za pomocą programu Excel lub Power BI, eksportowanych jest tylko pierwszych 15 poziomów hierarchii wymiarów. To ograniczenie istnieje, ponieważ programy Excel i Power BI wymagają ustalonego schematu. Jeśli hierarchia ma więcej niż 15 poziomów, dodatkowe poziomy nie będą eksportowane. Znormalizowana tabela zawiera rekord dla każdego elementu członkowskiego wymiaru w hierarchii. W związku z tym następuje automatyczna agregacja. To zachowanie pozwala zagwarantować, że salda w każdym z 15 dostępnych poziomów w hierarchii są wciąż poprawne.

W poniższym przykładzie pokazano, jak hierarchia wymiarów może wyglądać w strukturze raportowania.

| Hierarchia wymiarów obiektów kosztów — poziom 1 | Hierarchia wymiarów obiektów kosztów — poziom 2 | Hierarchia wymiarów obiektów kosztów — poziom 3 | Hierarchia wymiarów obiektów kosztów — poziom 4 | Hierarchia wymiarów obiektów kosztów — poziom 15 |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| Organizacja                              | Administrator                                     | Finanse                                   | CC002                                     |                                            |
| Organizacja                              | Administrator                                     | Finanse                                   | CC003                                     |                                            |
| Organizacja                              | Administrator                                     | Finanse                                   | CC007                                     |                                            |
| Organizacja                              | Administrator                                     | Zasoby ludzkie                                        | CC001                                     |                                            |
| Organizacja                              | Produkcja                                | Opakowanie                                 | CC005                                     |                                            |
| Organizacja                              | Produkcja                                | Zestaw                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>Aktualizacja hierarchie wymiarów używanych do raportowania 

Z czasem hierarchie wymiarów używane we wspomnianych wyżej narzędziach raportowania muszą być aktualizowane. Hierarchie wymiarów można zaktualizować przez odświeżenie klienta

- Obszar roboczy **Kontrola kosztów** (urządzenie klienckie)
- Obszar roboczy **Kontrola kosztów** (aplikacja komórkowa)

Aktualizacje hierarchii wymiarów są pobierane co 24 godziny przez zadanie umieszczone wstępnie w pamięci podręcznej. Po zaktualizowaniu wyeksportowanych danych zaktualizowane hierarchie wymiarów są dostępne w następujących narzędziach:

- Plik programu Excel
- Power BI

> [!NOTE] 
> Aby ręcznie zainicjować aktualizację pamięci podręcznej hierarchii wymiarów, można utworzyć nową operację eksportu do programu Excel dla odnośnych hierarchii wymiarów.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>Definiowanie hierarchii wymiarów dla zasad kosztów

Moduł Rachunek kosztów zawiera wiele zasad, w których są zdefiniowane szczegółowe reguły. Należy zdefiniować co najmniej jedną hierarchię wymiarów dla następujących zasad:

- Zachowanie kosztów
- Dystrybucja kosztów
- Alokacja kosztu
- Akumulacja kosztów

Hierarchie wymiarów ułatwiają tworzenie reguł. Aby uniknąć konieczności tworzenia reguł dla każdego elementu członkowskiego wymiaru, można użyć agregacji elementów członkowskich wymiarów, które są dostępne na poziomach hierarchii wymiarów. Jeśli masz nakładające się reguły, należy zdefiniować konkretne reguły, które system będzie brał pod uwagę przy obliczaniu kosztów ogólnych.

### <a name="example-define-a-cost-behavior-policy"></a>Przykład: Definiowanie zasady zachowania kosztów

Jest tworzona nowa zasada zachowania kosztów, a do zasady są przypisywane odpowiednie hierarchie wymiarów, jak pokazano poniżej.

**Zasada zachowania kosztów**

| Nazwa zasad   | Hierarchia wymiarów składników kosztów | Hierarchia wymiarów obiektów kosztów | Waluta rozliczeniowa |
|---------------|----------------------------------|---------------------------------|---------------------|
| Zachowanie kosztów | Zachowanie kosztów                    | Organizacja                    | USD                 |

**Reguły**

| Węzeł hierarchii wymiarów składników kosztów | Węzeł hierarchii wymiarów obiektów kosztów | Stały procent | Stała kwota | Obowiązuje od | Obowiązuje do |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| Koszt stały                            | Organizacja                         | 100,00           | 0,00         | 1/1/2017   | Nigdy    |
| 10001                                 | Organizacja                         | 0,00             | 150,00       | 1/1/2017   | Nigdy    |
| 10001 (\*)                             | Finanse                              |                  | 50,00        | 1/1/2017   | Nigdy    |
| Zachowanie kosztów lub koszt zmienny (\*\*)   | Organizacja                         | 0,00             | 0,00         | 1/1/2017   | Nigdy    |

\* Węzeł kosztu zmiennego nie jest wymagany. Jeśli koszt nie jest sklasyfikowany jako koszt stały, musi być kosztem zmiennym.

\*\* Jest tworzona szczegółowa reguła dla kombinacji elementu członkowskiego składnika kosztu 10001 i wszystkich elementów członkowskich obiektów kosztów, które są zagregowane na poziomie hierarchii Finanse (CC002, CC003, CC007).

Poprzednie reguły pokazują elastyczność, jaką oferują hierarchie wymiarów. Definiując reguły wysokiego poziomu, można zminimalizować czynności konserwacyjne. Następnie można zdefiniować szczegółowe reguły pasujące do konkretnych celów biznesowych.

Jeśli zostaną zaktualizowane hierarchie wymiarów używane w regułach, system automatycznie je pokazuje.

Jeśli poziom szczegółowości w regułach nie jest już wymagany, reguły można wygasić.

Na przykład nie jest już potrzebna określona reguła zachowania kosztów dla węzła hierarchii wymiaru obiektu kosztów Finanse. W takim przypadku kliknij przycisk **Wygaś regułę**, a reguła przestanie obowiązywać.

| Węzeł hierarchii wymiarów składników kosztów | Węzeł hierarchii wymiarów obiektów kosztów | Stały procent | Stała kwota | Obowiązuje od | Obowiązuje do  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| Koszt stały                            | Organizacja                         | 100,00           | 0,00         | 1/1/2017   | Nigdy     |
| 10001                                 | Organizacja                         | 0,00             | 150,00       | 1/1/2017   | Nigdy     |
| 10001                                 | Finanse                              |                  | 50,00        | 1/1/2017   | 20/1/2017 |
| Zachowanie kosztów lub koszt zmienny        | Organizacja                         | 0,00             | 0,00         | 1/1/2017   | Nigdy     |

Reguła przestanie być uwzględniana we wszystkich obliczeniach kosztów ogólnych wykonywanych po 20 stycznia 2017 r.

> [!NOTE] 
> Pola **Obowiązuje od** i **Obowiązuje do** mają daty i godziny obowiązywania. Można wygasić regułę i uruchomić nowe obliczanie kosztów ogólnych w tym samym dniu.

## <a name="define-dimension-hierarchies-for-security-setup"></a>Definiowanie hierarchii wymiarów dla ustawień zabezpieczeń

Dane rachunku kosztów powinny być dostępne dla wszystkich menedżerów odpowiedzialnych za jednostkę raportowania. W terminologii rachunku kosztów jednostka raportowania jest reprezentowana jako obiekt kosztów lub zbiór obiektów kosztów.

Potencjalnie wszyscy menadżerowie mają dostęp do poufnych danych biznesowych, takich jak przychody i marże. Dlatego ważne jest skonfigurowanie zabezpieczeń, tak aby menedżerów widzieli tylko dane, które ich dotyczą. Aby pomóc kontrolować bezpieczeństwo danych, definiuje się hierarchie wymiarów.

- Hierarchie wymiarów należy stosować tylko wtedy, gdy wartość wymiaru wybranego w odwołaniu do hierarchii wymiarów jest wymiarem obiektu kosztów.
- Można włączyć tylko jedną hierarchię wymiarów dla każdego wymiaru obiektu kosztów w hierarchii list dostępu.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar    | Nazwa typu hierarchii wymiarów      | Hierarchia list dostępu |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizacja             | Centra kosztów | Hierarchia klasyfikacji wymiarów | **Tak**               |

W projektancie hierarchii jest dostępna nowa skrócona karta **Użytkownicy**. Na niej można wstawić jeden lub więcej identyfikatorów użytkowników w każdym węźle w hierarchii.

**Zakresy użytkowników i elementów członkowskich wymiaru**

|   Węzły         |   Identyfikator użytkownika        |   Element członkowski wymiaru początkowego   |   Element członkowski wymiaru docelowego   |
|-----------------|------------------|---------------------------|-------------------------|
| Organizacja    | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Administrator         | kwiecień            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanse   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Zasoby ludzkie        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produkcja    | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Opakowanie | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Zestaw  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> Księgowi kosztów powinni być przypisani do najwyższego poziomu hierarchii, tak aby widzieli wszystkie wpisy w module Rachunek kosztów.

Aby włączyć hierarchię list dostępu i jej ustawienia zabezpieczeń, wybierz kolejno opcje **Rachunek kosztów** > **Ustawienia** > **Parametry** > **Ogólne**. Zaznacz parametr **Włącz dostęp z prawem do wyświetlania elementów członkowskich wymiaru obiektu kosztów**.

Ustawienia hierarchii list dostępu umożliwiają kontrolowanie danych, które są wyświetlane w następujących obszarach:

- Obszar roboczy **Kontrola kosztów** (urządzenie klienckie):

    - Dane w formularzach używanych w scenariuszach drążenia wskroś

- Obszar roboczy **Kontrola kosztów** (aplikacja komórkowa):

    - Salda na kartach

- Power BI:

    - Dane wyświetlane w wizualizacjach programu Power BI
    - Wizualizacje danych w rozwiązaniu Power BI osadzone w Dynamics 365 Finance, wersja kliencka

> [!NOTE] 
> - Aby hierarchia list dostępu mogła wpływać na dane w programie Power BI, należy w tym programie sparować hierarchię list dostępu i zabezpieczenia na poziomie wiersza w programie Power BI. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zabezpieczeń pakietu zawartości Rachunek kosztów](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - Hierarchia list dostępu nie pomaga zabezpieczyć eksportu danych do programu Excel. W związku z tym tego narzędzia sprawozdawczego mogą używać tylko księgowi i menedżerowie kosztów, którzy muszą mieć pełny dostęp w celu wyświetlania danych.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: "Nazewnictwo numerów i nazw wariantów produktu"
description: "W tym temacie opisano sposób ustawiania nazewnictwa numerów produktów w celu zastąpienia stałego formatu [numer produktu głównego — konfiguracja — rozmiar — kolor — styl numeracji] format. Nowe nazewnictwo ma format docelowy zawierający numer produktu głównego, aktywne wymiary produktu i separatory tekstu wybrane przez użytkownika. Można też ustalić zasady nazewnictwa dla nazw produktów. Można ponadto skonstruować konwencję nazewnictwa do identyfikowania konfiguracji, które są tworzone przez konfigurator produktów oparty na ograniczeniach. Te konwencje nazewnictwa mogą zawierać atrybuty wybrane przez użytkownika."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 0c3c1a3e64b016aa72e933f4d6cba854549ff13a
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a>Nazewnictwo numerów i nazw wariantów produktu

W tym temacie opisano sposób ustawiania nazewnictwa numerów produktów w celu zastąpienia stałego formatu [numer produktu głównego — konfiguracja — rozmiar — kolor — styl numeracji] format. Nowe nazewnictwo ma format docelowy zawierający numer produktu głównego, aktywne wymiary produktu i separatory tekstu wybrane przez użytkownika. Można też ustalić zasady nazewnictwa dla nazw produktów. Można ponadto skonstruować konwencję nazewnictwa do identyfikowania konfiguracji, które są tworzone przez konfigurator produktów oparty na ograniczeniach. Te konwencje nazewnictwa mogą zawierać atrybuty wybrane przez użytkownika.

Nowe nazewnictwa numerów wariantu produktu i nazw wariantów produktu pozwalają na uwzględnienie segmentów w identyfikatorach wariantów produktu. Segmenty te mogą zawierać numer i nazwę produktu głównego, identyfikator i nazwy wymiarów produktu, sekwencje numerów, stałe tekstowe i atrybuty. Ta funkcja umożliwia szybkie znalezienie konkretnego wariantu produktu podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu. Zarówno nazewnictwo numerów wariantu produktu i jak i nazewnictwo nazw wariantu produktu tworzy się przy użyciu strony **Nazewnictwo produktów**. Aby otworzyć tę stronę, kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia**.

## <a name="nomenclature-of-predefined-product-variants"></a>Nazewnictwo predefiniowanych wariantów produktu
Warianty produktu są generowane dla produktów głównych zgodnie z jedną z trzech technologii konfiguracji:

-   Wstępnie zdefiniowane warianty
-   Oparte na ograniczeniach
-   Oparte na wymiarze

Każdy wariant produktu ma numer i nazwę, a konwencje nazewnictwa identyfikacji wariantów produktu pozwalają wybrać segmenty, które zostaną umieszczone w każdym numerze lub nazwie wariantu produktu. Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:

-   Numer produktu głównego
-   Nazwa produktu głównego
-   Wartość sekwencji numerów
-   Stała tekstowa
-   Wymiary produktu
    -   Nazwa lub identyfikator konfiguracji
    -   Nazwa lub identyfikator koloru
    -   Nazwa lub identyfikator rozmiaru
    -   Nazwa lub identyfikator stylu

Po zdefiniowaniu nazewnictwa identyfikacji wariantu produktu można je skojarzyć z grupą wymiarów produktu. Wszystkim produktom głównym odwołującym się do tej grupy wymiarów produktu zostaną przypisane numery wariantów produktu zgodnie z konwencją nazewnictwa. Jednak nomenklatur nazw wariantów produktów nie można skojarzyć z grupami wymiarów produktów. Można również przypisać nazewnictwo identyfikacji wariantu produktu bezpośrednio do produktu głównego. W takim przypadku wariantom produktu, które należą do produktu głównego, zostaną przypisane numery oraz nazwy wariantów produktu zgodnie z nomenklaturami.

### <a name="example"></a>Przykład

Koszulka (TS1234) jest wytwarzana w 3 rozmiarach (S, M, L), czterech kolorach (czerwony, zielony, niebieski, żółty) i dwóch stylach (polo, w serek). Z tego względu możliwe są 24 (= 3 x 4 x 2) warianty produktu. Można utworzyć nazewnictwo numerów wariantów produktu, która zawiera następujące segmenty:

1.  Numer produktu głównego
2.  Stała tekstowa: „-”
3.  Kolor
4.  Stała tekstowa: „-”
5.  Rozmiar
6.  Stała tekstowa: „-”
7.  Styl

W tym przypadku numer wariantu produktu czerwonej, małej koszulki polo będzie następujący: TS1234-czerwony-mały-polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Nazewnictwo konfiguracji opartych na ograniczeniach
W konfiguracjach opartych na ograniczeniach można utworzyć dedykowaną konwencję nazewnictwa dla wymiaru konfiguracji produktu. Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:

-   Wartość sekwencji numerów
-   Stała tekstowa
-   Wartość atrybutu

Każdy składnik w modelu konfiguracji produktu może mieć własne nazewnictwo konfiguracji. Mogą być stosowane tylko atrybuty należące do składnika. Atrybuty ze składników podrzędnych i wymagań użytkownika nie mogą być stosowane.

### <a name="example"></a>Przykład

Model konfiguracji produktu ma składnik główny posiadający dwa atrybuty:

-   Materiał (plastik, drewno, stal)
-   Długość (10...100)

Można utworzyć nazewnictwo konfiguracji, która zawiera następujące segmenty:

1.  Wartość atrybutu: Materiał
2.  Stała tekstowa: „AAA”
3.  Wartość atrybutu: Długość

W tym przypadku identyfikator konfiguracji dla materiału „drewno” o długości 78 będzie DrewnoAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nazewnictwo konfiguracji opartych na wymiarach
W konfiguracjach opartych na wymiarach można utworzyć dedykowaną konwencję nazewnictwa dla wymiaru konfiguracji produktu. Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**:

-   Wartość sekwencji numerów
-   Stała tekstowa
-   Element grupy konfiguracji

Nazewnictwo konfiguracji można zdefiniować dla listy składowej (BOM).

### <a name="example"></a>Przykład

Lista BOM ma cztery wiersze BOM, które są podzielone na dwie grupy konfiguracji:

-   Wiersz BOM: M0007, Standardowa szafa
    -   Grupa konfiguracji: Szafa
-   Wiersz BOM: M0008, Szafa o wysokiej jakości
    -   Grupa konfiguracji: Szafa
-   Wiersz BOM: M0021, Przednia kratka z tkaniny
    -   Grupa konfiguracji: Przednia kratka
-   Wiersz BOM: M0022, Przednia kratka z metalu
    -   Grupa konfiguracji: Przednia kratka

Można utworzyć nazewnictwo konfiguracji, która zawiera następujące segmenty:

1.  Grupa konfiguracji: Szafa
2.  Stała tekstowa: „&”
3.  Grupa konfiguracji: Przednia kratka

W tym przypadku identyfikator konfiguracji standardowej szafy z przednią kratką z tkaniny będzie miał wartość M0007&M0021.

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>Nazewnictwo kombinacji wariantów produktu i konfiguracji
Jeśli do konfigurowania wariantów produktu głównego jest używana technologia konfiguracji opartej na ograniczeniach lub na wymiarach, warianty produktu mogą otrzymywać numery wariantów produktu zawierające nazewnictwo z wymiaru konfiguracji. Aby skonfigurować warianty, wykonaj następujące kroki.

1.  Na stronie **Nazewnictwo produktów** zdefiniuj nazewnictwo numerów wariantów produktu zawierające wymiar konfiguracji.
2.  Przypisz tę konwencję nazewnictwa do grupy wymiarów produktu zawierającej wymiar konfiguracji.
3.  Zdefiniuj nazewnictwo konfiguracji dla składników lub list BOM, które będą używane do konfigurowania wariantów produktu.

Można też ustalić zasady nazewnictwa dla nazw wariantów produktu. Aby uwzględnić nazwę lub identyfikator konfiguracji można skonfigurować nazwy wariantów produktu.

### <a name="example-for-constraint-based-configurations"></a>Przykład konfiguracji opartych na ograniczeniach

W tym przykładzie użyta jest konwencja nazewnictwa numerów wariantów produktu składająca się z następujących segmentów:

1.  Numer produktu głównego
2.  Stała tekstowa „\_”
3.  Konfiguracja

Nazewnictwo konfiguracji zawiera następujące segmenty:

1.  Wartość atrybutu: Materiał
2.  Stała tekstowa: „AAA”
3.  Wartość atrybutu: Długość

Można wprowadzić następujące wartości segmentów:

-   Numer produktu głównego = **M0099**
-   Materiał = **Plastik**
-   Długość = **12**

W tym przypadku numer wariantu produktu będzie miał wartość M0099\_PlastikAAA12.

### <a name="example-for-dimension-based-configurations"></a>Przykład konfiguracji opartych na wymiarach

W tym przykładzie użyta jest konwencja nazewnictwa numerów wariantów produktu składająca się z następujących segmentów:

1.  Numer produktu głównego
2.  Stała tekstowa: „//”
3.  Konfiguracja

Nazewnictwo konfiguracji zawiera następujące segmenty:

1.  Grupa konfiguracji: Szafa
2.  Stała tekstowa: „&”
3.  Grupa konfiguracji: Przednia kratka

Można wprowadzić następujące wartości segmentów:

-   Numer produktu głównego = **D0123**
-   Szafa = **M0008**
-   Przednia kratka = **M0022**

W tym przypadku numer wariantu produktu będzie miał wartość D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Konflikty numeracji
W niektórych przypadkach skonfigurowane nazewnictwo numerów wariantów produktu może nie powodować tworzenia unikatowych numerów wariantów produktu. Na przykład numery wariantów produktu nie będą unikatowe, jeśli jeden aktywny wymiar produktu nie jest uwzględniony w nazewnictwie produktu głównego używającym technologii wstępnie zdefiniowanej konfiguracji wariantów. Konflikty są obsługiwane w różny sposób w zależności od technologii konfiguracji.

### <a name="predefined-variants"></a>Wstępnie zdefiniowane warianty

Błąd pojawi się, jeśli zostanie podjęta próba ręcznego utworzenia lub automatycznego wygenerowania wariantów produktu i więcej niż jeden wariant kończy się tym samym numerem wariantu produktu. Aby uniknąć tego scenariusza, należy użyć wszystkich aktywnych wymiarów produktu w grupie wymiarów produktu. Ewentualnie należy uwzględnić sekwencję numerów w celu zagwarantowania, że numery wariantów produktu są unikatowe.

### <a name="constraint-based-configurations"></a>Konfiguracje oparte na ograniczeniach

W zależności od nazewnictwa system może próbować przypisać nieunikatowy numer wariantu produktu do konfiguracji. W takim przypadku jako numeru wariantu produktu system użyje sekwencji numerów wymiaru konfiguracji. Jeśli tak się stanie, otrzymasz ostrzeżenie. Aby uniknąć tej sytuacji, należy dołączyć wystarczającą liczbę atrybutów do nazewnictwa w celu zagwarantowania unikatowych numerów wariantów produktu. Należy również upewnić się, że opcja **Użyj ponownie** jest włączona dla składnika.

### <a name="dimension-based-configurations"></a>Konfiguracje oparte na wymiarach

Podczas jednego kroku procesu konfiguracji system proponuje wartość konfiguracji zgodną z konwencją nazewnictwa. W tym kroku można ręcznie zmienić wartość konfiguracji. Podczas zapisywania konfiguracji system sprawdza, czy wartość konfiguracji jest unikatowa. Jeśli wprowadzona wartość nie jest unikatowa, pojawi się komunikat o błędzie. Aby zapisać konfigurację, należy wprowadzić niepowtarzalną wartość konfiguracji.

<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-predefined-variants-2016-11)

[Tworzenie konwencji nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-product-variants_2016_11)



---
title: Nomenklatura numer produktu
description: "W tym temacie opisano, jak można skonfigurować numer nomenklaturą produktów do zastąpienia ustalony format [produkt główny - Konfiguracja - rozmiar - Kolor — styl numeracji], z formatu docelowego, który zawiera numer głównego produktu, aktywne wymiary produktu i ograniczniki tekstu wybranych przez użytkownika. Można także skonstruować konwencję nazewnictwa do identyfikowania konfiguracji, które są tworzone przez konfiguratora produktów opartego na ograniczeniach. Te konwencje nazewnictwa mogą zawierać atrybuty wybrane przez użytkownika."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220104
ms.assetid: 31c9efb4-b5f6-4af3-b884-8f1e128469bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 58afcd62e7ef317e624fd26d198c2606bf53e6a5
ms.lasthandoff: 03/31/2017


---

# <a name="product-number-nomenclature"></a>Nomenklatura numer produktu

W tym temacie opisano, jak można skonfigurować numer nomenklaturą produktów do zastąpienia ustalony format [produkt główny - Konfiguracja - rozmiar - Kolor — styl numeracji], z formatu docelowego, który zawiera numer głównego produktu, aktywne wymiary produktu i ograniczniki tekstu wybranych przez użytkownika. Można także skonstruować konwencję nazewnictwa do identyfikowania konfiguracji, które są tworzone przez konfiguratora produktów opartego na ograniczeniach. Te konwencje nazewnictwa mogą zawierać atrybuty wybrane przez użytkownika.

Nowe nazewnictwo numerów wariantów produktu pozwala umieszczać segmenty w identyfikatorach wariantów produktu. Segmenty te mogą zawierać numer produktu głównego, wymiary produktów, numeracje, stałe tekstowe i atrybuty. Ta funkcjonalność umożliwia szybkie znalezienie wariantu produktu podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu.

## <a name="nomenclature-of-predefined-product-variants"></a>Nazewnictwo predefiniowanych wariantów produktu
Warianty produktu są generowane dla produktów głównych zgodnie z jedną z trzech technologii konfiguracji:

-   Wstępnie zdefiniowane warianty
-   Oparte na ograniczeniach
-   Oparte na wymiarze

Każdy wariant produktu ma numer, a konwencja nazewnictwa identyfikacji wariantów produktu pozwala wybrać segmenty, które zostaną umieszczone w każdym numerze wariantu produktu. Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**.

-   Numer produktu głównego
-   Wartość sekwencji numerów
-   Stała tekstowa
-   Wymiary produktu
    -   Konfiguracja
    -   Kolor
    -   Rozmiar
    -   Styl

Po zdefiniowaniu konwencji nazewnictwa identyfikacji wariantów produktu można ją skojarzyć z grupą wymiarów produktu. W związku z tym wszystkim produktom głównym odwołującym się do tej grupy wymiarów produktu zostaną przypisane numery wariantów produkty zgodnie z konwencją nazewnictwa. Istnieje również możliwość przypisania konwencji nazewnictwa identyfikacji wariantu produktu bezpośrednio do produktu głównego. W takim przypadku wariantom produktu należącym do tego produktu głównego zostaną przypisane numery wariantów produktu zgodnie z konwencją nazewnictwa.

### <a name="example"></a>Przykład

Koszulka (TS1234) jest wytwarzana w 3 różnych rozmiarach (S, M, L), 4 różnych kolorach (czerwony, zielony, niebieski, żółty) i 2 stylach (polo, w serek), co daje łącznie 24 możliwe warianty produktu. Jest tworzona konwencja nazewnictwa wariantów produktu z następującymi segmentami:

1.  Numer produktu głównego
2.  Stała tekstowa: „-”
3.  Kolor
4.  Stała tekstowa: „-”
5.  Rozmiar
6.  Stała tekstowa: „-”
7.  Styl

Numer wariantu produktu Czerwony, Mały, Polo będzie następujący: TS1234-czerwony-mały-polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Nomenklatura konfiguracji constraintbased
W przypadku konfiguracji opartych na ograniczeniach dedykowany nomenklatury mogą być wbudowane w konfiguracji wymiaru produkt. Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**.

-   Wartość sekwencji numerów
-   Stała tekstowa
-   Wartość atrybutu 

Każdy składnik w modelu konfiguracji produktu może mieć własne nazewnictwo konfiguracji. Mogą być stosowane tylko atrybuty należące do składnika. Atrybuty ze składników podrzędnych i wymagań użytkownika nie są dostępne.

### <a name="example"></a>Przykład

Model konfiguracji produktu ma składnik główny z dwoma atrybutami.

-   Materiał (plastik, drewno, stal)
-   Długość (10...100)

Konwencję nazewnictwa konfiguracji definiuje się za pomocą następujących segmentów:

1.  Wartość atrybutu: Materiał
2.  Stała tekstowa: „AAA”
3.  Wartość atrybutu: Długość

Identyfikator konfiguracji materiału „drewno” o długości 78 otrzyma następującą wartość: DrewnoAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nomenklatura konfiguracji dimensionbased
W przypadku konfiguracji opartych na wymiarach dedykowany Nomenklatury Scalonej może być budowany dla konfiguracji Wymiar produktu. Można wybrać następujące segmenty na stronie **Nazewnictwo produktów**.

-   Wartość sekwencji numerów
-   Stała tekstowa
-   Element grupy konfiguracji

Nazewnictwo konfiguracji można zdefiniować dla listy składowej (BOM).

### <a name="example"></a>Przykład

Lista składowa ma 4 wiersze BOM podzielone na 2 grupy konfiguracji.

-   Wiersz BOM: M0007, Standardowa szafa
    -   Grupa konfiguracji: Szafa
-   Wiersz BOM: M0008, Szafa o wysokiej jakości
    -   Grupa konfiguracji: Szafa
-   Wiersz BOM: M0021, Przednia kratka z tkaniny
    -   Grupa konfiguracji: Przednia kratka
-   Wiersz BOM: M0022, Przednia kratka z metalu
    -   Grupa konfiguracji: Przednia kratka

Konwencję nazewnictwa konfiguracji definiuje się za pomocą następujących segmentów:

1.  Grupa konfiguracji: Szafa
2.  Stała tekstowa: „&”
3.  Grupa konfiguracji: Przednia kratka

Identyfikator konfiguracji standardowej szafy z przednią kratką z tkaniny będzie miał następującą wartość: M0007&M0021.

## <a name="nomenclature-of-a-combination-of-product-variants-and-configurations"></a>Nazewnictwo kombinacji wariantów produktu i konfiguracji
Jeśli do konfigurowania wariantów produktu głównego jest używana technologia konfiguracji opartej na ograniczeniach lub na wymiarach, warianty produktu mogą otrzymywać numery wariantów produktu zawierające nazewnictwo z wymiaru konfiguracji. Aby skonfigurować warianty, wykonaj następujące kroki:

1.  Na stronie **Nazewnictwo produktów** zdefiniuj konwencję nazewnictwa numerów wariantów produktu zawierającą wymiar konfiguracji.
2.  Przypisz tę konwencję nazewnictwa do grupy wymiarów produktu zawierającej wymiar konfiguracji.
3.  Zdefiniuj konwencję nazewnictwa konfiguracji dla składników lub list składowych, które będą używane do konfigurowania wariantów produktu.

### <a name="example-for-constraint-based-configurations"></a>Przykład konfiguracji opartych na ograniczeniach

W tym przykładzie można użyć konwencji nazewnictwa numerów wariantów produktu składającej się z następujących segmentów:

1.  Numer produktu głównego
2.  Stałą tekstową "\_"
3.  Konfiguracja

Konwencja nazewnictwa konfiguracji może zawierać następujące segmenty:

1.  Wartość atrybutu: Materiał
2.  Stała tekstowa: „AAA”
3.  Wartość atrybutu: Długość

Można wprowadzić następujące wartości segmentów:

-   Numer produktu głównego = M0099
-   Materiał = Plastik
-   Długość = 12

Staną się numer wariantu produktu: M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Przykład konfiguracji opartych na wymiarach

W tym przykładzie można użyć konwencji nazewnictwa numerów wariantów produktu składającej się z następujących segmentów:

1.  Numer produktu głównego
2.  Stała tekstowa: „//”
3.  Konfiguracja

Konwencja nazewnictwa konfiguracji może zawierać następujące segmenty:

1.  Grupa konfiguracji: Szafa
2.  Stała tekstowa: „&”
3.  Grupa konfiguracji: Przednia kratka

Można wprowadzić następujące wartości segmentów:

-   Numer produktu głównego = D0123
-   Szafa = M0008
-   Przednia kratka = M0022

Numer wariantu produktu będzie miał wartość: D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Konflikty numeracji
Istnieje możliwość skonfigurowania konwencji nazewnictwa numerów wariantów produktu, która nie powoduje tworzenia unikatowych numerów wariantów produktu. Na przykład może się to zdarzyć, jeśli jeden aktywny wymiar produktu nie jest uwzględniony w konwencji nazewnictwa produktu głównego używającej technologii wstępnie zdefiniowanej konfiguracji wariantów. Konflikty są obsługiwane w różny sposób dla różnych technologii konfiguracji.

### <a name="predefined-variants"></a>Wstępnie zdefiniowane warianty

Wystąpi błąd, jeśli zostanie podjęta próba ręcznego lub automatycznego generowania wariantów produktu, gdzie jeden lub więcej wariantów miałby otrzymać ten sam numer wariantu produktu. Aby tego uniknąć, należy użyć wszystkich aktywnych wymiarów produktu istniejących w grupie wymiarów produktu albo dodać numerację, co zapewni, że numery wariantów produktu są unikatowe.

### <a name="constraint-based-configurations"></a>Konfiguracje oparte na ograniczeniach

W zależności od konwencji nazewnictwa system może próbować przypisać nieunikatowy numer wariantu produktu do konfiguracji. W takim przypadku system użyje sekwencji numerów dla wymiaru konfiguracji jako numer wariantu produktu w zamian. W takim przypadku pojawi się ostrzeżenie. Aby tego uniknąć, należy w konwencji nazewnictwa uwzględnić tyle atrybutów, ile pozwoli zagwarantować unikatowość, oraz włączyć dla składnika opcję **Użyj ponownie**.

### <a name="dimension-based-configurations"></a>Konfiguracje oparte na wymiarach

Proces konfigurowania zawiera etap, w którym system zaproponuje wartość konfiguracji zgodną z konwencją nazewnictwa. W tym kroku można ręcznie zmienić wartość konfiguracji. Podczas zapisywania konfiguracji system sprawdzi, czy wartość konfiguracji jest unikatowa. Jeżeli nie, zostanie wyświetlony komunikat o błędzie. Aby zapisać konfigurację, należy wprowadzić niepowtarzalną wartość konfiguracji.



<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie nomenklatury numer produktu dla wariantów produktu wstępnie zdefiniowane (Przewodnik zadania)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-predefined-product-variants/)

[Tworzenie nomenklatury numer produktu dla wariantów produktu skonfigurowanych (Przewodnik zadania)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-configured-product-variants/)



---
title: "Konfigurowanie układów ekranu dla punktu sprzedaży"
description: "Ten temat zawiera informacje dotyczące układów ekranu dla usługi Microsoft Dynamics 365 dla operacji - punkt sprzedaży detalicznej sprzedaży (POS) doświadczeń."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d49c5c9773047940e524c71e59a674ebe8460ad7
ms.lasthandoff: 03/31/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Konfigurowanie układów ekranu dla punktu sprzedaży

Ten temat zawiera informacje dotyczące układów ekranu dla usługi Microsoft Dynamics 365 dla operacji - punkt sprzedaży detalicznej sprzedaży (POS) doświadczeń.

Usługi Microsoft Dynamics 365 dla operacji - punkt sprzedaży detalicznej sprzedaży (POS) interfejsu użytkownika można skonfigurować przy użyciu kombinacji Profile graficzne i układy ekranu, przypisane do sklepów, rejestrów i/lub użytkowników.

## <a name="visual-profile"></a>Profil graficzny
Profile graficzne są przypisane do rejestrów i są używane do określania elementów wizualnych, które są specyficzne dla rejestru i udostępnione przez użytkowników. Każdy użytkownik, który loguje się do kasy będzie mieć motyw, kolory i obrazy. **Profil numer** -numer profilu jest identyfikator unikatowy dla profilu graficznego. **Opis** -opis pozwala określić znaczącą nazwę, która pomoże zidentyfikować odpowiedni profil dla danej sytuacji. **Motyw** -użytkownicy mogą wybrać między tematy aplikacji jasny lub ciemny. Te ustawienia wpływ na kolory czcionki i tła całej aplikacji. **Kolorem akcentu** -kolor akcentu jest używana przez cały POS odróżnienia lub wyróżnienia pewnych elementów wizualnych, takich jak płytki, polecenia, przyciski lub hiperłącza. Elementy te są zazwyczaj zaskarżeniu. **Kolor nagłówka** -kolor nagłówka pozwala użytkownikowi na skonfigurowanie kolor nagłówka strony do potrzeb znakowania sprzedawcy detalicznego. Ta funkcja jest dostępna tylko w usłudze Dynamics 365 dla wersji operacji 1611. **Tło logowania** -użytkownicy mogą określić obraz jako tło dla ekranu logowania. Rozmiar plików obrazów tła powinna być utrzymywana tak małe jak to możliwe, jak przechowywanie i ładowanie dużych plików może mieć wpływ na wydajność i zachowania aplikacji. **Tło aplikacji** -Retail POS można również użyć obrazu jako tła w całej aplikacji zamiast koloru motywu stałych. Podobnie jak w przypadku tła logowania, zaleca się zachować jak najmniejszy rozmiar pliku.

## <a name="screen-layouts"></a>Układy ekranu
Konfiguracja układu ekranu Określa akcje, zawartości i położenie formantów interfejsu użytkownika w ekran powitalny POS i ekranu transakcji. ** Startowa **-w większości przypadków, ekran powitalny to strony, które użytkownicy będą widzieć po pierwszym zalogowaniu do punktu sprzedaży. Ekran powitalny może składać się z obrazu znakowania i siatek przycisków, które zapewniają dostęp do operacji punktu sprzedaży. Zwykle operacje, które nie są specyficzne dla bieżącej transakcji są umieszczane w tym miejscu. **Ekran transakcji** -ekran Transaction jest w głównym ekranie programu Retail POS do przetwarzania transakcji sprzedaży i zamówień. Na ekranie transakcji można skonfigurować przy użyciu Projektant układu ekranu. **Ekran startowy domyślne** -Niektórzy sprzedawcy detaliczni wolą kasjer nawigować po zalogowaniu bezpośrednio na ekranie transakcji. Domyślne ustawienie ekranu start umożliwia użytkownikom ustawianie to dla każdego układu ekranu.

### <a name="assignment"></a>Przypisanie

Układy ekranu można przypisać na poziomie sklepu, kasy lub użytkownika. Przypisywanie użytkownika zastępuje rejestr i przechowywać przypisania i przesłonięcia przydziału rejestru przypisania sklepu. W prosty scenariusz, gdzie wszyscy użytkownicy użycia tego samego układu, niezależnie od tego, czy rejestracja lub roli układ ekranu można ustawić tylko w sklepie. W przypadkach gdy niektóre rejestry lub użytkownicy wymagają wyspecjalizowane układy mogą mieć przypisanych odpowiednio.

### <a name="layout-sizes"></a>Rozmiary układów

Ta funkcja dotyczy tylko Dynamics 365 dla wersji operacji 1611. Ponieważ w wielu przypadkach układy ekranu mogą być używane w wielu rozmiaru ekranu i rozdzielczości, użytkownicy mogą konfigurować ich układ i zawartość dla każdego. W momencie uruchamiania aplikacji Retail POS automatycznie wybrać najbliższy rozmiar układu dla urządzenia. Układ ekranu może również zawierać konfiguracje dla zarówno pełny, jak i kompaktowe urządzenia. Ta konfiguracja umożliwia użytkownikowi można przypisać do układu jednym ekranie, który będzie działał w różnych rozmiarach i obudów znajdujące się w magazynie. **Pełna nowoczesnych POS -** -pełne układy są zazwyczaj najlepiej nadaje się do większych rozmiarach, takich jak monitory PC lub tabletek. Użytkownicy mogą wybierać elementy interfejsu użytkownika, które obejmują, określić ich rozmiar i położenie i konfigurowania ich właściwości szczegółowe. Układy pełnego obsługują konfiguracje poziomym i pionowym. **Kompaktowanie nowoczesnych POS -** -Compact układy są zazwyczaj najlepiej nadaje się do lub małych tabletów. Możliwości projektowania są ograniczone do kompaktowe urządzenia. Użytkownicy mogą konfigurować kolumny i pola do okienka paragonu i sum.

### <a name="screen-layout-designer"></a>Projektant układu ekranu

Każdy układ rozmiar w ramach układu ekranu musi być skonfigurowany przy użyciu Projektant układu ekranu. Projektant umożliwia użytkownikom należy przypisać i skonfigurować elementy interfejsu użytkownika ekranu transakcji. Projektant układu ekranu używa ClickOnce, aby pobrać, zainstalować i uruchomić najnowszą wersję aplikacji za każdym razem, użytkownik uzyskuje dostęp do niego. Należy sprawdzić wymagania dotyczące przeglądarki za pomocą opcji ClickOnce — niektóre przeglądarki, takie jak chrom, wymagają rozszerzeń. **Klawiatura numeryczna** -numerycznej jest głównym użytkownikiem na ekranie POS transakcji. Może być skonfigurowany do Pokaż cały na ekranie konsoli, który jest idealnym rozwiązaniem dla ekranów dotykowych, lub tylko pola wejściowego, który może być używany z klawiaturą. Numer ustawień w konsoli są dostępne w pełny układ. W usłudze Dynamics 365 dla wersji operacji 1611 układy kompaktowe zawsze mają pełną klawiaturę numeryczną dostępne na ekranie transakcji. **Panel sumy** - panel sum można skonfigurować w jednej lub dwóch kolumn, aby wyświetlić pola takie jak linia count, kwotę rabatu, opłat, Suma częściowa i podatku. W usłudze Dynamics 365 dla wersji operacji 1611 compact układy obsługują tylko pojedynczy sumy kolumny. **Przyjęcie** -** ** panel odbioru zawiera wiersze zamówienia sprzedaży, wiersze płatności i informacje o dostawie produktów i usług przetwarzane w punkcie sprzedaży. Użytkownicy mogą określać kolumny, szerokość i położenie. W układach compact w usłudze Dynamics 365 dla wersji operacji 1611 można również skonfigurować dodatkowe informacje, które pojawi się w wierszu poniżej linii głównej. **Kartoteka nabywcy** - klienta karta pokazuje informacje odnoszące się do aktualnie skojarzonych z transakcją odbiorcy. Kartoteka nabywcy można skonfigurować tak, aby ukryć lub pokazać dodatkowe informacje. **Karta sterowania** - formantu karty mogą być umieszczane na układ ekranu i inne formanty, takie jak numerycznej, kartoteki nabywcy lub siatki przycisków można umieścić wewnątrz karcie. Formant karty jest kontenerem, który ułatwia użytkownikom fit więcej zawartości na ekranie. Formant karty jest dostępna tylko dla pełnego układów. ** Image **-formant obrazu może służyć do wyświetlania logo Sklepu lub inny obraz marki na ekranie transakcji. Formant obrazu jest dostępna tylko dla pełnego układów. **Polecane produkty** - Jeśli skonfigurowany dla środowiska naturalnego, zalecane środki kontroli będzie wyświetlać podpowiedzi produktu oparte na nauce maszyny. Zalecane środki kontroli jest dostępna tylko dla pełnego układów w usłudze Dynamics 365 dla wersji operacji 1611. ** Niestandardowego formantu **-formant niestandardowy działa jako symbol zastępczy w układzie ekranu, aby pozwala użytkownikom zarezerwować miejsce dla zawartości niestandardowej. Formant niestandardowy jest dostępna tylko dla pełnego układów.

<a name="see-also"></a>Informacje dodatkowe
--------

[Install the Retail POS Layout designer](install-pos-layout-designer.md)



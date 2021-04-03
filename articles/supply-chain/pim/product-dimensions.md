---
title: Wymiary produktu
description: Istnieje pięć wymiarów produktu - kolor, konfiguracja, rozmiar, styl i wersja. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.
author: t-benebo
manager: tfehr
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ca0a7233004522de2af7281416169f0393feeb11
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260654"
---
# <a name="product-dimensions"></a>Wymiary produktu

[!include [banner](../includes/banner.md)]

Istnieje pięć wymiarów produktu: kolor, konfiguracja, rozmiar, styl i wersja. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.

Wymiary produktu to cechy, które służą do określenia wariantu produktu. Kombinacje wymiarów produktu służą do definiowania wariantów produktu. Należy zdefiniować co najmniej jeden wymiar produktu dla produktu głównego w celu utworzenia wariantu produktu.

## <a name="product-variants"></a>Warianty produktu

Warianty produktu są również określane jako elementy. Towar to produkt materialny, który nie jest usługą. Istnieje również możliwość zdefiniowania produktu głównego typu usługa. Za pomocą typu usługa można określić warianty produktu, które zawierają usługi. Na przykład można określić produkt główny dla pracy w zakresie doradztwa i warianty produktu dla pracy wykonywanej przez starszych konsultantów i młodszych konsultantów.

## <a name="product-dimensions"></a>Wymiary produktu

Wariant produktu może być generowany na podstawie wartości w wymiarach produktu.

Wartości wymiaru produktu dla wymiarów rozmiaru, koloru i stylu można utworzyć w następujących lokalizacjach:

- Strona **Rozmiar** (**Zarządzanie informacjami o produktach \> Konfiguracja \> Grupy wymiarów i wariantów \> Rozmiary**)
- Strona **Kolor** (**Zarządzanie informacjami o produktach \> Konfiguracja \> Grupy wymiarów i wariantów \> Kolory**)
- Strona **Styl** (**Zarządzanie informacjami o produktach \> Konfiguracja \> Grupy wymiarów i wariantów \> Style**)

Wartości wymiaru produktu dla wymiaru konfiguracji są zwykle tworzone za pomocą konfiguratora produktów lub konfiguratora opartego na wymiarach. 

Wersje produktów są zwykle tworzone dla określonych wersji w miarę rozwoju produktu podczas jego cyklu życia. Wersje produktów opisano szczegółowo w dalszej części tego tematu.

Wymiary produktu mogą być również tworzone i obsługiwane na stronie **Wymiary produktu**, która jest dostępna z następujących miejsc:

- Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Produkty \> Produkty główne**. W okienku akcji wybierz pozycję **Wymiary produktu**.
- Kliknij kolejno opcje **Zarządzanie informacjami o produktach \> Produkty \> Wszystkie produkty i produkty główne**. Wybierz produkt główny. W okienku akcji wybierz pozycję **Wymiary produktu**.
- Kliknij kolejno opcje **Zarządzanie informacjami o produktach \> Zwolnione produkty**. Wybierz produkt główny. Następnie w okienku akcji na karcie **Produkt** w grupie **Produkt główny** wybierz opcję **Wymiary produktu**.

Liczba wariantów, które można utworzyć dla towaru jest ograniczona przez liczbę kombinacji wymiarów produktu.

> [!TIP]
> Jeśli produkt jest używany, na przykład, w wierszu zamówienia, należy wybrać wymiary produktu do zdefiniowania wariantu produktu, który ma być używany.

## <a name="example"></a>Przykład

Firma sprzedaje jeansy. Dla towaru — *jeansów* — istnieją wymiary kolor i rozmiar. Jeansy są sprzedawane w trzech różnych kolorach i sześciu rozmiarach. Kolory to niebieskie, czarny i brązowy. Rozmiary to: XS, S, M, L, XL i XXL. Nie wszystkie rozmiary są dostępne w trzech kolorach. Jeżeli wszystkie kombinacje byłyby dostępne, istniałoby 18 różnych typów jeansów. Jednak w tym przykładzie utworzono tylko dziewięć następujących kombinacji wariantu produktu.

| Kolor | Rozmiar |
|-------|------|
| Niebieski  | XS   |
| Niebieski  | N    |
| Niebieski  | P    |
| Czarny | P    |
| Czarny | L    |
| Czarny | XL   |
| Brązowy | L    |
| Brązowy | XL   |
| Brązowy | XXL  |

## <a name="the-version-product-dimension"></a>Wersja wymiaru produktu

Wersja to wymiar produktu, który ma pomóc w zachowaniu i śledzeniu wielu wersji produktu w łańcuchu dostaw. Śledzenie wersji ma zasadnicze znaczenie dla sukcesu producentów, którzy działają w świecie stale kurczących się cykli życia produktów, zwiększonych wymagań dotyczących jakości i niezawodności oraz większego nacisku na bezpieczeństwo produktów.

Jako standardowy wymiar produktu, wersja będzie działać podobnie jak istniejące wymiary produktu (rozmiar, styl, kolor i konfiguracja). Z tego względu można go stosować do innych celów oprócz śledzenia wersji produktów.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>Włącz wymiar wersji

#### <a name="before-you-turn-on-the-version-dimension"></a>Przed włączeniem wymiaru wersji

Po włączeniu wymiaru wersji niektóre funkcje mogą zostać przerwane lub przestanie działać zgodnie z oczekiwaniami, jeśli zainstalowano inne rozwiązania, które dodają dostosowania do wymiarów magazynowych. Aby wymiar wersji był w pełni funkcjonalny, może być konieczne zaktualizowanie tych rozwiązań, tak aby obejmowały one wymiar wersji w odniesieniu do wymiarów magazynowych.

Podczas testowania rozwiązań w celu zapewnienia zgodności z wymiarem wersji należy szukać następujących elementów:

1. **Funkcje:** Co najważniejsze, wszelkie dostosowania, które obejmują wymiary magazynowe, muszą zostać ocenione, aby upewnić się, że mogą działać w połączeniu z wymiarem wersji.
1. **Odwołania do wymiarów magazynowych:** Poszukaj odniesień do wymiarów magazynowych (to znaczy miejsc, w których wymiary są wyraźnie wymienione). Odwołania do `InventDimId` powinny zostać wykonane z pola, ale nie są poszukiwane odwołania do stylu lub koloru. Na przykład należy sprawdzić następujące elementy:

    - Wywołania interfejsu API w klasach rozszerzonych
    - Wszystkie odwołania do konkretnych wymiarów magazynowych w kodzie rozszerzenia (kod ten musi przepływać na wymiar wersji wraz z stylem, kolorem i wymiarami rozmiaru).

1. **Odwołania do przestarzałych wywołań interfejsu API:** Wprowadzając wymiar wersji, Microsoft starał się uczynić jak najmniejszą liczbę interfejsów API przestarzałymi. Niektóre z przestarzałych interfejsów API spowodują wyświetlenie ostrzeżenia po włączeniu klucza konfiguracji **Wymiar produktu - wersja**. Przed włączeniem wymiaru wersja w systemie produkcji wywołania tych interfejsów API muszą zostać naprawione w rozwiązaniach rozszerzonych. Oto przestarzałe interfejsy API dotyczące wersji:

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **Mapy:** Jeśli w każdej mapie są używane wymiary magazynowe, odpowiednie mapowanie relacji do tych map musi zostać zaktualizowane, tak aby obejmowało ono wymiar wersji. W rozszerzonych rozszerzeniach modelu lub tabeli odszukaj tabele, których pola zawierają wymiary magazynowe.
1. **Funkcje rozwiązania Microsoft Dynamics 365 Commerce:** Po włączeniu wymiar wersji pojawi się w całym kodzie specyficznym dla Commerce w Dynamics 365 Supply Chain Management. Jednak wymiar wersji nie jest jeszcze obsługiwany przez bazę danych kanału Commerce ani w aplikacjach w punkcie sprzedaży (POS) lub aplikacjach handlu elektronicznego. Te aplikacje handlowe nie obsługują użytkowników sprzedających/wysyłających lub zwracających/otrzymujących zapasy według wymiaru wersji. Funkcje wyszukiwania dostępności zapasów nie rozróżniają zapasów według wymiaru wersji w aplikacjach Commerce. To zachowanie przypomina bieżące zachowanie wymiaru konfiguracji w całym module Commerce.

#### <a name="turn-on-the-version-dimension"></a>Włącz wymiar wersji

Aby móc używać wymiaru wersji, należy ją włączyć w systemie. To zadanie wymaga uprawnień administratora.

1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
1. Włącz funkcję o nazwie *Wersja wymiarowa produktu*. (Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Przełącz system do [trybu konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
1. Na karcie **Klucze konfiguracji** rozwiń pozycję **Handel**, a następnie zaznacz pole wyboru dla **Wymiar produktu - wersja**.
1. Wyłącz [tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="areas-where-the-version-dimension-isnt-supported"></a>Obszary, w których wymiar wersji nie jest obsługiwany

W poniższych obszarach nie jest obsługiwany wymiar wersji (nadal możesz używać tych obszarów, ale nie będziesz mieć możliwości dodawania produktów z wersji (produktów, w których jest używany wymiar wersji) do tych obszarów). Na przykład nie można dodać towaru z wersją do katalogu dostawcy. Jest tak dlatego, że dodawanie produktów z wymiarem wersji do tych obszarów może spowodować zmiany powodujące niezgodność.

- Miesięczne zestawienie kosztów
- Pamięć podręczna zestawienia obiektów kosztów
- MCR statystyk sprzedaży dla pozycji
- Katalogi dostawców
- EcoResProductDimensionGroupEntity

Ponadto funkcje tworzenia i przetwarzania zamówień w aplikacji Commerce (na przykład w przypadku zamówień w punktach sprzedaży, centrum obsługi telefonicznej i e-commerce) nie obsługują wymiaru wersji. Nie ma potwierdzonego harmonogramu, kiedy zamówienia Commerce zostaną ulepszone, aby je obsługiwać.

### <a name="functional-characteristics-of-the-version-dimension"></a>Charakterystyka funkcjonalna wymiaru wersji

Wymiar wersji działa podobnie do innych wymiarów produktu. Jednak ze względu na swoją specyfikę i ponieważ jest przeznaczony do utrzymywania i śledzenia wielu wersji produktu, zachowuje się nieco inaczej. Poniżej przedstawiono niektóre różnice i podobieństwa:

- **Brak grupy wersji.**

    Chociaż istnieje koncepcja grup dla rozmiaru, koloru i stylu (grupa kolorów, grupa rozmiarów i grupa stylów), nie istnieje koncepcja grupy wersji. Grupy pozwalają wstępnie zdefiniować odpowiednie wartości, aby na przykład przypisać do produktu grupę kolorów, produkt mógł używać wszystkich kolorów z tej grupy kolorów. To pojęcie nie ma zastosowania w odniesieniu do wymiaru wersji, ponieważ wersje, które produkt przyjmuje, nie są wstępnie zdefiniowane podczas tworzenia produktu. W takim przypadku wersje są tworzone w trakcie cyklu życia produktu, ponieważ są one wymagane. Zazwyczaj, jeśli formularz, dopasowanie i funkcja produktu pozostają takie same, zamiast nowego produktu zostanie utworzona nowa wersja.

- **Propozycje wariantów produktów działają tak, jak obecnie.**

    Sugestie wariantów produktu będą tworzyć sugestie dla wszystkich wartości wymiarów wersji, podobnie jak w przypadku innych wymiarów. Proces tworzenia i zwalniania wersjonowanych produktów jest taki sam, jak w przypadku produktów używających innych wymiarów. Podczas tworzenia wersjonowanego produktu pierwsza wersja (V1) zostanie utworzona jako wymiar produktu, a warianty zostaną zwolnione. Gdy produkt się zmieni i potrzebna jest nowa wersja, zostanie dodana wartość nowej wersji (V2), a wymagane warianty zostaną wydane. Nie oczekuje się, że wszystkie wersje (V1, V2 i V3) zostaną utworzone z wyprzedzeniem dla produktu.

> [!IMPORTANT]
> Jeśli włączysz wymiar wersji i użyjesz go, niektóre rozwiązania odwołujące się do wymiarów magazynowych mogą przestać działać zgodnie z oczekiwaniami. Aby potwierdzić i rozwiązać te problemy, skontaktuj się z niezależnym dostawcą oprogramowania (ISV), aby uzyskać rozwiązania, których dotyczy problem. Aby uzyskać więcej informacji, skorzystaj z opcji [Włącz wymiar wersji](#enable-version-dim).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
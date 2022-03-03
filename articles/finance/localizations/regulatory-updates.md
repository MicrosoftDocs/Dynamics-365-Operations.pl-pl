---
title: Aktualizacje wymagane przepisami prawa
description: Ten temat zawiera listę planowanych i udostępnionych aktualizacji wymaganych przepisami prawa dla Microsoft Dynamics 365 Finance.
author: VStamberg
ms.date: 01/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: vastrup
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 663b7d3162af6d385bc9c445b1e98cf5f74a1471
ms.sourcegitcommit: f2a78e0d7d461ca843ac2f9abff7690275db9196
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8105571"
---
# <a name="regulatory-updates"></a>Aktualizacje wymagane przepisami prawa

[!include [banner](../includes/banner.md)]

W tym temacie opisano aktualizacji wymaganych przepisami prawa dla wersji w lokalizacjach obsługiwanych i wypuszczonych przez program Dynamics 365 Finance. Harmonogram dostarczania może się zmienić i planowane funkcje mogą być inne lub mogą nie zostać udostępnione. Aby uzyskać więcej informacji, zobacz [zasady Microsoft](https://go.microsoft.com/fwlink/p/?linkid=2007332). 

Aktualizacje wymagane przepisami prawa to funkcje implementowane w celu zachowania zgodności z nowymi lub zmienionymi przepisami w danym kraju. Aby dowiedzieć się o innych planowanych lub udostępnionych funkcjach specyficznych dla kraju, należy zapoznać się z [plany wydawcze Dynamics 365 i Power Platform](/business-applications-release-notes/index).

Firma Microsoft dokłada starań w celu wprowadzenia w życie nowych wymagań prawnych możliwie jak najszybciej. Rzeczywista data dostarczenia zależy od daty zawiadomienia o zmianie przepisów, dostępności szczegółów nowych wymagań, dostępności narzędzi do walidacji i rozmiaru oraz stopnia skomplikowania zmiany w prawie.

Planujemy dostarczać aktualizacje wymagane przepisami prawa w jednej wersji aktualizacji usług udostępnionej w czasie pozwalającym klientom na uaktualnienie ich narzędzi, tak aby wszystko było gotowe w dniu wejścia w życie nowego przepisu (w przypadku zmian przepisów dot. transakcji) lub w terminie składania obowiązkowych raportów (w przypadku zmian prawa dotyczącego sprawozdawczości). Klienci i partnerzy mogą przeglądać nowe aktualizacje przepisów w programie Preview Early Adoption Program (PEAP).

W przypadku późnego ogłoszenia zmian, późnej dostępności szczegółów wymagań lub narzędzi do walidacji, albo w przypadku wyjątkowo obszernych i skomplikowanych zmian może nie być możliwe udostępnienie aktualizacji wymaganej przepisami prawa do dnia udostępnienia ogólnej comiesięcznej aktualizacji. W takich przypadkach aktualizacja wymagana przepisami prawa będzie rozsyłana jako poprawki dla odpowiednich dostępnych comiesięcznych aktualizacji.

Aktualizacje dotyczące środków ustawowych, które zostały wydane w ramach comiesięcznych aktualizacji, są oznaczone wyłącznie jako wersja wydania. Aktualizacje dotyczące aktualizacji, które są dostarczane jako poprawki na gorąco lub w ramach wersji Preview, mogą być identyfikowane odpowiednio przez skróty HF i PEAP. 

Aby uzyskać informacje o najnowszych planach w zakresie aktualizacji wymaganych przepisami prawa, zapoznaj się z poniższą tabelą.   

|Kraj|Data zwolnienia|Wersja wydania|Aktualizacje wymagane przepisami prawa|
|--------------------|---------------|-------|-------| 
|      Austria         |   Sierpień 2021      | 10.0.22      |   Deklaracja VAT w XML i podgląd w Excelu   |
|      Austria         |   2021 września      | 10.0.22HF      |   Format Intrastat jest aktualizowany od 2022 roku — kraj pochodzenia i identyfikator VAT partnera stają się obowiązkowe w wysyłkach   |
|      Belgia        |   2021 października      | 10.0.22HF     |   Kody transakcji Intrastat zmienią się na 2 cyfry począwszy od 2022 roku  |
|      Brazylia         |   Sierpień 2021      | 10.0.22      |   NF-e NT2020.006 — Identyfikacja pośrednika platformy cyfrowej (aktualizacje układu i zasad walidacji)   |
|      Brazylia         |   2021 grudnia         | 10.0.22, 10.0.23, 10.0.24         |    Funkcja fiskalna SPED układ 2022  |
|      Republika Czeska         |   2021 października         | 10.0.23HF         |     Format Intrastat jest aktualizowany od 2022 roku — kraj pochodzenia i identyfikator VAT partnera stają się obowiązkowe w wysyłkach  |
|      Dania         |   2021 grudnia         | 10.0.22HF         |    Format Intrastat zaktualizowany począwszy od 2022  |
|      Estonia         |   2021 grudnia      | 10.0.22HF      |   Format Intrastat jest aktualizowany od 2022 roku — kraj pochodzenia i identyfikator VAT partnera stają się obowiązkowe w wysyłkach  |
|      Finlandia         |   Listopad 2021         | 10.0.22HF         |    Format Intrastat zaktualizowany począwszy od 2022.  |
|      Niemcy        |   Sierpień 2021       | 10.0.22HF      |   Format Intrastat zaktualizowany INSTAT XML począwszy od 2022. Format Intrastat TXT nie obowiązuje od 01.07.2021  |
|      Niemcy        |   2021 października       | 10.0.23      |   Deklaracja VAT w XML i podgląd w Excelu (nowy projekt z kwotami w walucie kodu podatku, działający po wyjęciu z pudełka z funkcją odwrotnego obciążenia, może być wykonywany w podmiotach prawnych spoza DE i może pobierać transakcje podatkowe od kilku podmiotów prawnych)  |
|      Włochy         |   Listopad 2021         | 10.0.22HF, 10.0.23HF, 10.0.24         |    Fakturowanie elektroniczne dla transakcji transgranicznych  |
|      Meksyk         |   Listopad 2021      | 10.0.22      |   Dopełnienie pozycji Carta de Porte w dokumentach CFDI   |
|      Meksyk         |   2021 grudnia      | 10.0.24      |   Carta de Porte uzupełnia wersję 2.0  |
|      Holandia        |   2021 października      | 10.0.22HF      |   2-cyfrowy kod transakcji w formacie pliku Intrastat z 2022 roku  |
|      Nowa Zelandia         |   Sierpień 2021      | 10.0.22    |   Formularz deklaracji GST GST101A  |
|      Norwegia        |   Listopad 2021      | 10.0.24      |   Format deklaracji VAT 2022 z przesłaniem bezpośrednim — Dynamics 365 Finance |
|      Oman         |   Sierpień 2021      | 10.0.22      |   Deklaracja VAT - Wersja 1 |
|      Polska          |   2021 października     | 10.0.23, 10.0.24     |   JPK_V7M — nowa wersja schematu od stycznia 2022 roku |
|      Polska          |   Listopad 2021     | 10,0,24HF     |   Raport roczny o terminach płatności w transakcjach handlowych |
|      Polska          |   2021 października     | 10.0.24     |   Elektroniczny format listy sprzedaży do UE (VAT-UE) |
|      Rosja          |   2021 października     | 10.0.22HF, 10.0.23, 10.0.24    |   Zmiany w sprzedaży, zakupach ksiąg i dziennikach faktograficznych|
|      Rosja          |   2021 października     | 10,0,24HF    |   Zmiana w formatach deklaracji VAT z załącznikami|
|      Rosja          |   Listopad 2021     | 10.0.24    |   Federalne Standardy Rachunkowości 6/2020 (Środki trwałe)|
|      Arabia Saudyjska          |   Listopad 2021     | 10.0.22HF, 10.0.23    |   Generowanie fakturowania elektronicznego w Arabii Saudyjskiej — faza 1|
|      Arabia Saudyjska          |   Listopad 2021     | 10.0.22HF, 10.0.23HF, 10.0.24    |   Handel detaliczny - fakturowanie elektroniczne w Arabii Saudyjskiej — faza 1|
|      Hiszpania          |   2021 października     | 10.0.23    |    Model deklaracji VAT 303 w txt i podgląd w Excelu|
|      Hiszpania          |   2021 września     | 10.0.22    |    Format Intrastat zostanie zaktualizowany do raportowania w 2022 r. - identyfikator VAT partnera i kraj pochodzenia będą obowiązkowe w przypadku wysyłek|
|      Szwecja          |   2021 października     | 10.0.22HF    |    Format Intrastat jest aktualizowany od 2022 roku — kraj pochodzenia i identyfikator VAT partnera stają się obowiązkowe w wysyłkach. Używane będą kody transakcji dwucyfrowych.|
|      Zjednoczone Królestwo          |   Sierpień 2021     | 10.0.22    |    Wielka Brytania — zapobieganie oszustw MTD 2021)|



## <a name="additional-resources"></a>Dodatkowe zasoby
- Aby uzyskać więcej informacji o wszystkich planowanych i zwolnionych aktualizacjach przepisów specyficznych dla kraju, zobacz temat [Wyszukiwanie aktualizacji przepisów specyficznych dla kraju](search-for-regulatory-updates.md). (Wymagane jest logowanie).
- Aby uzyskać listę lokalizacji obsługiwanych, zobacz [Przewodnik dostępności w różnych krajach](https://aka.ms/dynamics_365_international_availability_deck).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

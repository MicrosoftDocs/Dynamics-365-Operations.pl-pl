---
title: Dzielenie wygenerowanych plików XML na podstawie rozmiaru pliku i ilości treści
description: Ten temat zawiera informacje dotyczące dzielenia plików generowanych na podstawie rozmiaru pliku i ilości elementu zawartości.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: cde95430022d94c42bdd985b5e4a8f9f5147d000
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181365"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Dzielenie wygenerowanych plików XML na podstawie rozmiaru pliku i ilości treści

[!include[banner](../includes/banner.md)]

Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby generowały wychodzące dokumenty w formacie XML. Czasami te dokumenty mogą być akceptowane tylko wtedy, gdy spełniają określone kryteria, np. maksymalnego rozmiaru pliku lub maksymalnej liczby niektórych węzłów XML. Można zaprojektować formaty ER w taki sposób, aby generowały dokumenty elektroniczne zgodnie z wymogami wyznaczonymi przez ich odbiorców.

- Dla elementu formatu FILE można zdefiniować limit rozmiaru pliku jako wyrażenie ER. Jeśli zdefiniowany limit zostanie przekroczony podczas generowania raportu modułu ER, moduł ER zakończy tworzenie bieżącego pliku, a następnie przejdzie do tworzenia następnego pliku.
- Dla każdego elementu formatu XML ELEMENT można zdefiniować limit liczby elementów jako wyrażenie ER. Jeśli liczba węzłów XML w wygenerowanym pliku przekracza zdefiniowany limit podczas tworzenia raportu modułu ER, moduł ER zakończy tworzenie bieżącego pliku, a następnie przejdzie do tworzenia następnego pliku.
- Dla każdego elementu formatu XML SEQUENCE można zdefiniować limit liczby elementów podrzędnych jako wyrażenie ER. Jeśli liczba zagnieżdżonych węzłów XML elementu formatu w wygenerowanym pliku przekracza zdefiniowany limit podczas tworzenia raportu modułu ER, moduł ER zakończy tworzenie bieżącego pliku, a następnie przejdzie do tworzenia następnego pliku.
- Można zaznaczyć dowolny element formatu XML ELEMENT jako nieprzenoszony. W ten sposób można zachować zagnieżdżone obiekty węzłów XML, które zostały wygenerowane pod elementem formatu, w jednym pliku.

Poza używaniem elementów formatu XML ELEMENT i XML SEQUENCE w celu dodania węzłów kodu źródłowego XML do wygenerowanego pliku można również używać elementu formatu XML RAW. Jednak węzły dodawane przy użyciu elementu formatu XML RAW nie są brane pod uwagę podczas obliczania liczby węzłów w celu oceny przestrzegania ograniczenia liczby elementów.

Jeśli skonfigurowano plikowe miejsca docelowe dla elementu formatu FILE, w którym ustawiono dzielenie wygenerowanych danych wyjściowych po każdym przekroczeniu określonego limitu, każda część wygenerowanych danych wyjściowych jest wysyłana do skonfigurowanego plikowego miejsca docelowego jako osobny plik. Aby nadać niepowtarzalne nazwy plików, które są tworzone przez podział danych wyjściowych, należy skonfigurować wyrażenie RE dla elementu formatu pliku. Po dołączeniu źródła danych raportowania elektronicznego o typie NUMERACJA numer będzie zwiększany dla każdego kolejnego fragmentu podzielonych danych wyjściowych.

Aby dowiedzieć się więcej o tej funkcji, należy odtworzyć przewodnik po zadaniach **pliki XML podziału ER na podstawie rozmiaru pliku lub ilość zawartości pozycji**, wchodzący w skład procesu biznesowego **7.5.4.3 Pobierania/opracowywanie składników usług/rozwiązań informatycznych (10677)** i można go pobrać z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Ten przewodnik zadania przeprowadzi Cię przez proces konfigurowania formatu ER w celu podzielenia wygenerowanych plików na podstawie ograniczeń rozmiaru pliku i ilości pozycji zawartości. Aby ukończyć przewodnik po zadaniach, należy pobrać następujące pliki:

- [Konfiguracja modelu ER — XmlFilesSplittingModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Konfiguracja formatu ER — XmlFilesSplittingFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a>Dodatkowe zasoby
[Aplikacje docelowe Raportowania elektronicznego](electronic-reporting-destinations.md)

[Projektant formuł w Raportowaniu elektronicznym](general-electronic-reporting-formula-designer.md)

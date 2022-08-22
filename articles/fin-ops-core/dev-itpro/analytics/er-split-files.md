---
title: Dzielenie wygenerowanych plików XML na podstawie rozmiaru pliku i ilości zawartości
description: Ten artykuł zawiera informacje dotyczące dzielenia plików generowanych na podstawie rozmiaru pliku i ilości elementu zawartości.
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 5347d4e85198893dd94f14508176db93ccd47c22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280104"
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

- [Konfiguracja modelu ER — XmlFilesSplittingModel.xml](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [Konfiguracja formatu ER — XmlFilesSplittingFormat.xml](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a>Dodatkowe zasoby
[Lokalizacje docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)

[Projektant formuł w module Raportowanie elektroniczne (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

---
title: Aparaty do zarządzania transportem
description: Aparaty zarządzania transportem definiują logikę, która służy do tworzenia i przetwarzania stawek transportowych w module Zarządzanie transportem.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dff811723e25952b4c5af20262010ff4b910be7f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "361137"
---
# <a name="transportation-management-engines"></a>Aparaty do zarządzania transportem

[!include [banner](../includes/banner.md)]

Aparaty zarządzania transportem definiują logikę, która służy do tworzenia i przetwarzania stawek transportowych w module Zarządzanie transportem. 

Aparat zarządzania transportem oblicza zadania, takie jak stawki przewoźnika za transport. System umożliwia zmianę strategii obliczeń w czasie wykonywania na podstawie danych w programie Microsoft Dynamics 365 for Finance and Operations. Aparatu zarządzania transportem jest podobny do dodatku, który jest powiązany z umową przewoźnika.

## <a name="what-engines-are-available"></a>Jakie aparaty są dostępne?
Poniższa tabela zawiera aparaty zarządzania transportem dostępne w programie Microsoft Dynamics 365 for Finance and Operations.

| Aparat zarządzania transportem | opis                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Aparat wyznaczania stawki**                  | Oblicza stawki.                                                                                                                                                                                                                                                                                                           |
| **Ogólny aparat**               | Proste aparaty pomocnicze, używane przez inne aparaty, które nie wymagają danych z programu Microsoft Dynamics 365 for Finance and Operations, na przykład aparat przydziału. Aparaty przydziału służą do zmniejszania końcowych kosztów transportu do określonych zamówień i wierszy zgodnie z wymiarami takimi jak objętość i waga. |
| **Aparat przebiegu**               | Oblicza odległość pokonywaną podczas transportu.                                                                                                                                                                                                                                                                                     |
| **Aparat czasu tranzytu**          | Oblicza czas potrzebny na podróże od rozpoczęcia do zakończenia w miejscu docelowym.                                                                                                                                                                                                                                       |
| **Aparat strefy**                  | Oblicza strefę na podstawie bieżącego adresu strefy i oblicza liczbę stref, które muszą zostać skreślone w celu podróży z adresu A do adresu B.                                                                                                                                                                    |
| **Typ opłaty frachtowej**            | Standaryzuje faktury za fracht i wiersze BOM frachtu i jest używane do automatycznego uzgadniania rachunków za transport.                                                                                                                                                                                                                |


<a name="what-engines-must-be-configured-to-rate-a-shipment"></a>Jakie aparaty muszą być skonfigurowane do ustalenia stawki za przesyłkę?
---------------------------------------------------

Aby ustalić stawkę za przesyłkę dla określonego przewoźnika, należy skonfigurować wiele aparatów zarządzania transportem. **Aparat stawki** jest wymagany, ale do obsługi  mogą być konieczne również inne aparaty do **zarządzania transportem**. Na przykład **aparat stawki** może być używany do pobierania danych z **aparatu przebiegu** w celu obliczenia stawki w oparciu o przebieg między lokalizacją źródłową a miejscem docelowym.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>Co jest wymagane do zainicjowania aparatu zarządzania transportem?
Aparat zarządzania transportem wymaga ustawienia inicjowania danych do działania w określony sposób. Konfiguracja może obejmować następujące typy danych:
-   Odwołania do innych aparatów zarządzania transportem. Aby uzyskać szczegółowe informacje, zobacz przykład konfiguracji w tej sekcji.
-   Odwołania do typów .NET, które są używane przez aparat zarządzania transportem.
-   Prosta konfiguracja danych.

W większości przypadków można kliknąć przycisk **Parametry** w formularzach konfiguracji aparatu zarządzania transportem w celu skonfigurowania danych inicjujących. **Przykład konfiguracji z aparatem stawki, który odwołuje się do aparatu przebiegu** Poniższy przykład pokazuje ustawienia wymagane dla aparatu stawki, który jest oparty na typie aparatu .NET Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEngine i odwołuje się do aparatu przebiegu.

|          Parametr           |                                                                                  Opis                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <em>RateBaseAssigner</em>   | Typ .NET interpretowania danych przypisania podstawy stawki dla określonego schematu. Składnia wartości parametru składa się z dwóch segmentów oddzielonych pionową kreską ( |
|  <em>MileageEngineCode</em>  |                       Kod aparat przebiegu identyfikujący rekord aparatu przebiegu w bazie danych programu Microsoft Dynamics 365 for Finance and Operations.                        |
| <em>ApportionmentEngine</em> |                        Kod aparatu ogólnego identyfikujący rekord aparatu przydziału w bazie danych programu Microsoft Dynamics 365 for Finance and Operations.                        |

<a name="how-is-metadata-used-in-transportation-management-engines"></a>Jak używane są metadane w aparatach zarządzania transportem?
----------------------------------------------------------

Aparaty zarządzania transportem, które opierają się na danych zdefiniowanych w programie Dynamics 365 for Finance and Operations, mogą używać różnych schematów danych. System zarządzania transportem umożliwia różnych aparatom zarządzania transportem korzystanie z tych samych ogólnych tabel fizycznej bazy danych. Aby się upewnić, że interpretacja wykonania tego aparatu dane jest poprawna, można zdefiniować metadane dla tabel baz danych. Zmniejsza to koszty budowania nowych aparatów zarządzania transportem, ponieważ nie są wymagane dodatkowe struktury tabeli i formularza w programie Operations.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>Co może być używane jako dane wyszukiwania w obliczeniach stawki?
Dane, które są używane podczas obliczania stawek w programie Microsoft Dynamics 365 for Finance and Operations, są zależne od konfiguracji metadanych. Na przykład, aby wyszukać kursy w oparciu o kody pocztowe, trzeba skonfigurować metadane na podstawie typu wyszukiwania kodu pocztowego.

## <a name="do-all-engine-configurations-require-metadata"></a>Czy wszystkie konfiguracje aparatu wymagają metadanych?
Nie, nie potrzebują ich aparaty zarządzania transportem, które są używane do pobierania danych potrzebnych przy obliczaniu stawki z systemów zewnętrznych. Można pobrać dane stawki dla tych aparatów z systemów przewoźnika transportu zewnętrznego, zazwyczaj za pośrednictwem usługi sieci web. Na przykład można użyć aparatu przebiegu, który pobiera dane bezpośrednio z map Bing, dzięki czemu aparat ten nie potrzebuje metadanych.

| **Uwaga**                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aparaty zarządzania transportem, które zostały dostarczone z programem Finance and Operations, opierają się na danych, które są pobierane z aplikacji. Aparaty połączone z systemami zewnętrznymi nie są częścią programu Operations. Jednak model rozszerzania oparty na aparacie umożliwia rozszerzenia kompilacji przy użyciu pakietu Visual Studio Tools dla programu Microsoft Dynamics 365 for Finance and Operations. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>W jaki sposób skonfigurować metadane dla aparatu zarządzania transportem?
Metadane dla aparatów zarządzania transportem są skonfigurowane inaczej dla różnych typów aparatów.

| Aparat zarządzania transportem               | Konfiguracja metadanych                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Aparat wyznaczania stawki**                                | Wymaga **typu opartego na stawce**. Typ stawki bazowej zawiera metadane dla danych podstawowych stawki i przypisanie podstawowej stawki danych. Struktura metadanych podstawowej stawki zależy od typu aparatu stawki. Struktura metadanych przypisywania podstawy stawki zależy od typu użytkownika przypisującego podstawową stawkę, skojarzonego z tym aparatem stawki. Można ustawić typ podstawowej stawki aparatu stawki na stronie **Aparat stawki** i na stronie **Główna stawka**. |
| **Aparat strefy**                                | Wymaga metadanych do skonfigurowania bezpośrednio w głównej strefie.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Aparat czasu tranzytu** i **aparat przebiegu** | Pobiera metadane bezpośrednio z aparatu przebiegu konfiguracji ustawień formularza.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Przykład metadanych dla aparatu stawki** Aparatu zarządzania transportem wymaga identyfikacji adresu pochodzenia, stanu docelowego i kraju/regionu, i rozpoczęcia i punktu końcowego wysyłki. Dzięki spełnieniu tych wymagań metadane będą wyglądać jak w tabeli poniżej. Tabela ta zawiera także informacje o tym, jaki typ danych wejściowych jest wymagany.
-   Określ te informacje w obszarze **Zarządzanie transportem** &gt; **Ustawienia** na stronie **Typ stawki bazowej**.

| Kolejność | Nazwisko                          | Typ pola | Typ danych | Typ wyszukiwania    | Obowiązkowe |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa        | Miejsce początkowe — kod pocztowy            | Przypisanie | Ciąg    | Kod pocztowy    | Wybrano  |
| 2        | Miejsce docelowe             | Przypisanie | Ciąg    | Stanowy          |           |
| 3        | Miejsce początkowe — kod pocztowy | Przypisanie | Ciąg    | Kod pocztowy    | Wybrano  |
| 4        | Miejsce docelowe — kod pocztowy   | Przypisanie | Ciąg    | Kod pocztowy    | Wybrano  |
| 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych        | Kraj przeznaczenia           | Przypisanie | Ciąg    | Kraj/region |           |






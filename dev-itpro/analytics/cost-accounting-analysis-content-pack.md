---
title: "Rachunek kosztów analizy zawartości BI zasilania"
description: "W tym temacie opisano, co jest zawarte w rachunku kosztów analizy zawartości Power BI. Wyjaśnia, jak uzyskać dostęp do raportów BI zasilania i zawiera informacje o modelu danych i podmiotów, które były używane do tworzenia treści."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 50e7bd92ee693f59fd013226aee22bd1a54c81e2
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-analysis-power-bi-content"></a>Rachunek kosztów analizy zawartości BI zasilania

W tym temacie opisano, co jest zawarte w rachunku kosztów analizy zawartości Power BI. Wyjaśnia, jak uzyskać dostęp do raportów BI zasilania i zawiera informacje o modelu danych i podmiotów, które były używane do tworzenia treści.

<a name="overview"></a>Przegląd
--------

**Analizy rachunku kosztów** Microsoft Power BI zawartość jest przeznaczona dla kontrolerów kosztów lub każdego, kto jest odpowiedzialny za wykonywanie kontroli kosztów organizacji. Obejmuje on kluczowych wskaźników, takich jak koszt, wielkości i stawki kosztów rzeczywistych kosztów, koszt budżetowy, a koszty budżetu elastycznego. Wykorzystuje dane transakcji z rachunku kosztów w usłudze Microsoft Dynamics 365 dla operacji i zapewnia zagregowany widok kosztów dla całej organizacji w jednej walucie dla raportowania. Menedżerowie można filtrować dane przez obiekty koszt przeprowadzić kontrolę kosztów ich jednostek organizacyjnych, nawet jeśli organizacja może mieć kilka podmiotów prawnych. Ponieważ **analizy rachunku kosztów** Power BI zawartości wyróżnia różnic pomiędzy rzeczywistymi kosztami a kosztami budżetowymi, menedżerowie mogą być informowany o pozytywnych i negatywnych tendencji dla swoich jednostek operacyjnych. Menedżerowie mogą drążenie do hierarchii element kosztów lub kosztów poszczególnych elementów, aby uzyskać szczegółowe informacje dotyczące sposobu odchyleń kosztowych miały miejsce oraz następnie podjęcia skutecznych działań. **Analizy rachunku kosztów** Power BI zawartości Przeanalizujmy kosztów księgowych na jak koszt przepływa przez obiekty koszt całej organizacji. Aby dowiedzieć się więcej na temat rachunku kosztów, zobacz [strona główna rachunku kosztów](/dynamics365/operations/financials/cost-accounting/cost-accounting-home-page.md). Zdefiniowanie zabezpieczeń poziom dostępu w rachunku kosztów i łącząc go z zabezpieczeniami na poziomie wiersza w BI zasilania, można udzielić wszystkich właścicieli obiektów koszt dostępu do **analizy rachunku kosztów** Power BI zawartości. Wszystkie dane w wizualizacji będzie następnie być filtrowane według poziomu dostępu, który jest kontrolowany w rachunku kosztów. Aby dowiedzieć się więcej na temat poziomu dostępu zabezpieczeń i zabezpieczenia na poziomie wiersza, zobacz [Konfigurowanie zabezpieczeń dla zawartości rachunku kosztów dla Power BI](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Dostęp do zawartości BI zasilania
Można znaleźć **analizy rachunku kosztów** Power BI zawartości w bibliotece zasobów współużytkowanych w Microsoft Dynamics cyklu życia usługi (LCS). Aby uzyskać więcej informacji na temat sposobu pobierania zawartości i podłącz go do sieci 365 Dynamics dla danych operacji, zobacz [Power BI zawartości w LCS firmy Microsoft i jej partnerzy](power-bi-content-microsoft-partners.md). **Uwaga:** KB4011327 ** ** stanowi warunek wstępny dla **analizy rachunku kosztów** Power BI zawartości.  Po zalogowaniu się do cyklu życia usług można uzyskać dostęp KB tutaj: <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki, które są zawarte w treści BI zasilania
Zawartość zawiera zestaw stron raportu. Każda strona zawiera zestaw miar, które są przedstawiane jako wykresy, tabliczki i tabelami. Poniższa tabela zawiera omówienie wizualizacje w **analizy rachunku kosztów** Power BI zawartości.

| Strony raportu                      | Wykres                                                                                                                         | Kafelek                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Kontrola kosztów według okresu obrachunkowego    | Koszt rzeczywisty i koszt budżetowy wg poziomu hierarchii element kosztów                                                                   | Koszt budżetowy koszt rzeczywisty vs                    |
|                                  | Różnica budżetowa wg poziomu hierarchii element kosztów                                                                               | Stawka kosztu rzeczywistego w porównaniu z budżetu stawka kosztów          |
|                                  | 10 najlepszych odchylenie budżetu w procentach element kosztów                                                                          | Wielkość budżetu vs rzeczywistej wielkości          |
| Kontrola kosztów za rok poprzedzający datę     | Koszt rzeczywisty i koszt budżetowy wg okresu roku kalendarzowego                                                                           | Koszt budżetowy koszt rzeczywisty vs                    |
|                                  | Odchylenie budżetu według okresu roku kalendarzowego                                                                                       | Stawka kosztu rzeczywistego w porównaniu z budżetu stawka kosztów          |
|                                  | 10 najlepszych odchylenie budżetu w procentach element kosztów                                                                          | Wielkość budżetu vs rzeczywistej wielkości          |
| Stawka kosztu według roku obrachunkowego         | Stawka kosztu rzeczywistego, przez zachowanie kosztów                                                                                             | Stawka kosztu rzeczywistego w porównaniu z budżetu stawka kosztów          |
|                                  | Stawka kosztu rzeczywistego, wariancji stawki koszt budżetowy, koszt budżetowy stawkę procentową i stawki kosztu budżetu wg poziomu hierarchii element kosztów | Wielkość budżetu vs rzeczywistej wielkości          |
|                                  | Różnica budżetowa wg poziomu hierarchii element kosztów                                                                               |                                               |
|                                  | 10 najlepszych odchylenie budżetu w procentach element kosztów                                                                          |                                               |
| Budżet elastyczny według okresu obrachunkowego | Koszt rzeczywisty, koszt budżetowy i budżet elastyczny kosztów wg poziomu hierarchii element kosztów                                             | Wielkość budżetu vs rzeczywistej wielkości          |
|                                  | Odchylenie budżetu i odchylenie budżetu elastycznego wg poziomu hierarchii element kosztów                                                  | Rzeczywisty koszt w porównaniu z budżetu elastycznego kosztów           |
|                                  | Koszt rzeczywisty, koszt budżetowy i elastyczne kosztów według kosztu zachowanie i kosztów poziom hierarchii element                                  | Stawka kosztu budżetu elastycznego vs stawka kosztu rzeczywistego |
| Zestawienie kosztów według okresu obrachunkowego  | Koszt rzeczywisty poziom hierarchii element kosztów i nazwa elementu członkowskiego wymiaru obiektu kosztów                                             |                                               |
|                                  | Koszt rzeczywisty nazwa elementu członkowskiego wymiaru obiektu kosztów i nazwa elementu członkowskiego wymiaru elementu kosztów                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dynamics 365 dla danych operacji jest używany do wypełniania strony raportu **analizy rachunku kosztów** Power BI zawartości. Te dane jest reprezentowany jako zagregowanych wskaźników, które są umieszczane w magazynie podmiot, który jest bazy danych Microsoft SQL, który jest zoptymalizowany pod kątem analytics. Aby uzyskać więcej informacji, zobacz [omówienie Power BI Integracja z magazynu jednostki](power-bi-integration-entity-store.md). Następujące kluczowe pomiary agregacji są wykorzystywane jako podstawa zawartości.

| Jednostka                  | Klucz zagregowanego wskaźnika | Źródło danych dla usługi Dynamics 365 dla operacji | Pole     | opis                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| Zapisy wyceny kosztów | SUM(Amount)               | CAMDATAAggregatedCostEntry                  | Ilość    | Kwota w walucie księgi rachunku kosztów |
| Wpisy statystyczne     | SUM(MAGNITUDE)            | CAMDATAAggregatedStatisctialEntry           | Wartość |                                               |

W poniższej tabeli przedstawiono, jak klucza zagregowanych wskaźników są używane do tworzenia kilku miary obliczeniowe w zestawie danych zawartości.

| Pomiar                                       | Sposób obliczania środka                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Koszt rzeczywisty                                   | OBLICZ ("rachunek kosztów wpisy"\[środka\], "Wersje transakcji"\[ISSOURCEVERSIONBUDGET\_wartość\] = 0)            |
| Koszt budżetowy                                   | OBLICZ ("rachunek kosztów wpisy"\[środka\], "Wersje transakcji"\[ISSOURCEVERSIONBUDGET\_wartość\] = 1)            |
| Odchylenie koszt w budżecie                          | \[Budżet kosztów\] - \[koszt rzeczywisty\]                                                                                      |
| Procentowe odchylenie budżetu                    | IF (\[koszt budżetowy\] = 0, blank(), \[odchylenie budżetu\] / \[koszt budżetowy\])                                                |
| Rzeczywista wielkość                              | OBLICZ ("Wpisy statystycznych"\[FullMagnitude\], "Wersje transakcji"\[ISSOURCEVERSIONBUDGET\_wartość\] = 0)          |
| Wielkość budżetu                              | OBLICZ (\[FullMagnitude\], "Wersje transakcji"\[ISSOURCEVERSIONBUDGET\_wartość\] = 1)                               |
| Odchylenie statystyczne budżetu                   | \[Wielkość budżetu\] - \[rzeczywista wielkość\]                                                                            |
| Procentowe odchylenie statystyczne budżetu        | IF (\[wielkości budżetu\] = 0, blank(), \[Odchylenie statystyczne budżetu\] / \[wielkości budżetu\])                          |
| Stawka kosztu rzeczywistego                              | IF (\[rzeczywista wielkość\] = 0, BLANK(), \[rzeczywisty koszt\] / \[rzeczywista wielkość\])                                          |
| Stawka kosztu budżetowego                              | IF (\[wielkości budżetu\] = 0, BLANK(), \[koszt budżetowy\] / \[wielkości budżetu\])                                          |
| Odchylenie kurs budżetowy koszt                     | \[Stawka kosztu budżetu\] - \[stawki kosztów rzeczywistych\]                                                                            |
| Wartość procentowa odchylenia kurs budżetowy koszt          | IF (\[koszt budżetowy\] = 0, blank(), \[stawka odchylenie kosztowe budżetu\] / \[stawka kosztu budżetu\])                                 |
| Kosztu ustalonego budżetu                             | OBLICZ (\[koszt budżetowy\], zapisów koszt\[COSTBEHAVIOR\] = 1)                                              |
| Koszt budżetowy zmiennej                          | OBLICZ (\[koszt budżetowy\], zapisów koszt\[COSTBEHAVIOR\] = 2)                                              |
| Kosztu ustalonego budżetu elastycznego                    | \[Kosztu ustalonego budżetu\]                                                                                                  |
| Kosztów zmiennych budżetu elastycznego                 | IF (\[wielkości budżetu\] = 0, BLANK(), (\[koszt budżetowy zmiennej\] / \[wielkości budżetu\]) \*\[rzeczywista wielkość\])       |
| Koszt budżetu elastycznego                          | \[Budżet elastyczny koszt stały\] + \[kosztów zmiennych budżetu elastycznego\]                                                     |
| Odchylenie budżetu elastycznego                      | \[Koszt budżetowy elastyczne\] - \[koszt rzeczywisty\]                                                                             |
| Procentowe odchylenie budżetu elastycznego           | IF (\[budżetu elastycznego koszt\] = 0, BLANK(), \[odchylenie budżetu elastycznego\] / \[budżetu elastycznego koszt\])                     |
| Stawka kosztu budżetu elastycznego                     | IF (\[rzeczywista wielkość\] = 0, BLANK(), \[budżetu elastycznego koszt\] / \[rzeczywista wielkość\])                                 |
| Odchylenie stawki kosztów budżetu elastycznego            | \[Stawka kosztu budżetu elastycznego\] - \[stawki kosztów rzeczywistych\]                                                                   |
| Procentowe odchylenie stawki kosztów dla budżetu elastycznego | IF (\[stawka kosztu budżetu elastycznego\] = 0, BLANK(), \[stawka odchylenie kosztowe budżet elastyczny\] / \[stawka kosztu budżetu elastycznego\]) |

Następujące wymiary kluczy są używane jako filtry do plasterka łącznej wartości, tak aby osiągnąć większą ziarnistość i zapewniają lepszy wgląd analityczne.

| Jednostka                             | Przykłady atrybutów                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Księgi rachunku kosztów            | Księga rachunku kosztów                                                                                               |
| Jednostki kontroli kosztów                 | Nazwa jednostki kontroli kosztów                                                                                               |
| Wymiary składników kosztów            | Koszt elementów wymiaru nazwa, nazwa elementu członkowskiego wymiaru element kosztów, opis składnika kosztów element wymiaru          |
| Wymiary obiektów kosztów             | Nazwa wymiaru obiekt kosztów, nazwa elementu członkowskiego wymiaru obiektu kosztów, opis składnika kosztów obiekt wymiaru              |
| Wymiary statystyczne             | Nazwa wymiaru statystycznych, nazwa elementu członkowskiego wymiaru statystycznych, opis składnika statystycznych wymiaru              |
| Hierarchie wymiarów obiekt kosztów  | Nazwa hierarchii wymiaru obiektu kosztów, kosztu poziom hierarchii wymiaru obiektu, drzewa hierarchii wymiaru obiektu koszt    |
| Hierarchie wymiarów elementów kosztów | Nazwa hierarchii wymiaru element kosztów, kosztu poziom hierarchii wymiaru elementu, drzewa hierarchii wymiaru elementów kosztów |
| Hierarchie wymiarów statystycznych  | Nazwa hierarchii wymiaru statystycznych, poziom hierarchii wymiaru statystycznych, wymiar statystycznych drzewie hierarchii    |
| Wersje transakcji               | Nazwa wersji                                                                                                         |
| Kalendarze obrachunkowe                   | Kalendarz, opis kalendarza                                                                                       |
| Lata obrachunkowe                       | Rok kalendarzowy                                                                                                        |
| Okresy obrachunkowe                     | Okres roku kalendarzowego                                                                                                 |

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](..\data-entities\data-entities.md)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](configure-power-bi-integration.md)
-   [Konfigurowanie zabezpieczeń dla zawartości rachunku kosztów BI zasilania](setup-security-cost-accounting-content-pack.md)



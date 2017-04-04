---
title: "Zarządzanie cyklem życia konfiguracji raportowania elektronicznego"
description: "W tym temacie opisano sposób zarządzania cyklem życia Electronic raportowania (ER) konfiguracje dla usługi Microsoft Dynamics 365 dla operacji rozwiązania."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: f4d8994f6548119789715a4879b6bc02d25598e9
ms.lasthandoff: 03/31/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Zarządzanie cyklem życia konfiguracji raportowania elektronicznego

W tym temacie opisano sposób zarządzania cyklem życia Electronic raportowania (ER) konfiguracje dla usługi Microsoft Dynamics 365 dla operacji rozwiązania.

<a name="overview"></a>Przegląd
--------

Raportowanie elektroniczne (ER) jest aparatem, który obsługuje dokumenty elektroniczne wymagane ustawowo i specyficzne dla danego kraju w programie Microsoft Dynamics 365 for Operations. Zasadniczo moduł ER umożliwia wykonywanie następujących zadań dla pojedynczego dokumentu elektronicznego. Aby uzyskać więcej szczegółowych informacji, zobacz [Omówienie raportowania elektronicznego](general-electronic-reporting.md).

-   Projektowanie szablonu dokumentu elektronicznego:
    -   identyfikacja wymaganych źródeł danych, które mogą być prezentowane w dokumencie:
        -   Leżących u podstaw systemu Dynamics 365 dla danych operacji, takich jak tabele danych, obiektów danych i klas.
        -   Właściwości specyficzne dla procesu, takie jak Data wykonania i czas i strefę czasową.
        -   Użytkownik parametrów wejściowych, określonym przez użytkownika w czasie wykonywania.
    -   Definiowanie wymaganych elementów dokumentu oraz ich topologii w celu określenia formatu finalnego dokumentu.
    -   Konfigurowanie żądanego przepływu danych z wybranych źródeł danych do zdefiniowanych elementów dokumentu (za pomocą powiązań źródeł danych ze składnikami formatu dokumentu) i określanie logiki kontroli procesu.
-   Udostępnianie szablonu pozwalające używać go w innych wystąpieniach programu Dynamics 365 for Operations:
    -   Przekształcanie szablonu dokumentu utworzonego w programie Dynamics 365 for Operations na konfigurację raportowania elektronicznego, a następnie eksportowanie konfiguracji z bieżącego wystąpienia programu Dynamics 365 for Operations jako pakietu XML, który może być przechowywany lokalnie lub w usłudze LCS.
    -   Przekształcanie konfiguracji ER na szablon dokumentu programu Dynamics 365 for Operations.
    -   Import pakietu XML przechowywanego lokalnie lub w usłudze LCS do bieżącego wystąpienia programu Dynamics 365 for Operations.
-   Dostosowywanie szablonu dokumentu elektronicznego:
    -   Pobieranie szablonu z usługi LCS do bieżącego wystąpienia programu Dynamics 365 for Operations jako konfiguracji ER.
    -   Projektowanie niestandardowej wersji konfiguracji ER z zachowaniem odniesienia do wersji bazowej.
-   Integracja szablonu z określonym procesem biznesowym w celu udostępnienia go w programie Dynamics 365 for Operations:
    -   Konfigurowanie ustawień programu Dynamics 365 for Operations, tak aby zaczął używać konfiguracji ER, poprzez utworzenie odwołania do tej konfiguracji w parametrze związanym z procesem. Na przykład odwołać się do konfiguracji ER w określonej metody płatności rozrachunków z dostawcami kont do generowania wiadomości płatności elektronicznych do przetwarzania faktur.
-   Używanie szablonu w określonym procesie biznesowym:
    -   Konfiguracja ER uruchamiania w procesie konkretnej firmy. Na przykład aby generować komunikat płatności elektronicznych do przetwarzania faktur podczas płatności, która odwołuje się do konfiguracji ER jest zaznaczone.

## <a name="concepts"></a>Koncepcje
Następujące role i powiązanych z nimi działań są związane z cyklem życia konfiguracji encja-Relacja.

| Rola                                       | Działania                                                      | opis                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konsultant funkcjonalny raportowania elektronicznego | Tworzenie i zarządzanie składnikami ER (modelami i formatami).           | Osoby firmy, która projektuje ER modeli danych specyficznych dla domeny, projektuje szablony wymagane dla dokumentów elektronicznych i wiąże je odpowiednio.                                                                           |
| Deweloper raportowania elektronicznego             | Tworzenie i zarządzanie mapowaniami modelu danych.                          | Usługa Dynamics 365 dla operacji specjalista, który wybiera wymagane 365 Dynamics dla źródeł danych operacji i powiązanie ich z modeli danych specyficznych dla domeny encja-Relacja.                                                                 |
| Kierownik ds. księgowania                      | Konfigurowanie ustawień procesów odwołujących się do artefaktów ER. | Na przykład **kierownik** rolę, która umożliwia ustawień konfiguracji ER używane w konkretnej metody płatności rozrachunków z dostawcami kont do generowania wiadomości płatności elektronicznych do przetwarzania faktur. |
| Pracownik ds. płatności rozrachunków z dostawcami            | Używanie artefaktów ER w określonym procesie biznesowym.                | Na przykład **Pracownik ds** rolę, która umożliwia płatności elektronicznych wiadomości ma być generowana dla przetwarzania faktur oparty na formacie ER, który jest skonfigurowany dla konkretnych sposobów płatności.           |

## <a name="er-configuration-development-lifecycle"></a>Cykl życia tworzenia konfiguracji ER
Zalecamy projektować konfiguracje raportowania elektronicznego w środowisku programistycznym jako odrębnym wystąpieniu programu Dynamics 365 for Operations z następujących przyczyn:

-   Użytkownicy posiadający rolę **Deweloper raportowania elektronicznego** lub **Konsultant funkcjonalny raportowania elektronicznego** mogą edytować konfiguracje i uruchamiać je do celów testowych. Ten scenariusz może powodować wywoływanie metod klas i tabel mogących uszkadzać dane firmy i spowalniać działanie wystąpienia programu Dynamics 365 for Operations.
-   Wywołania metod klas i tabel jako źródeł danych ER konfiguracji ER nie są ograniczone przez punkty wejścia do programu Dynamics 365 for Operations ani logowanie do zasobów firmy. Dlatego poufne dane firmy mogą być dostępne dla użytkowników posiadających rolę **Deweloper raportowania elektronicznego** lub **Konsultant funkcjonalny raportowania elektronicznego**.

Konfiguracje ER, zaprojektowanych w środowisku programowania można przekazać do środowiska testowego do oceny konfiguracji (prawidłowego procesu integracji, poprawność wyników i wydajności) i zapewnienia jakości, takie jak prawidłowość praw dostępu oparty na rolach i podział obowiązków. Funkcje, które umożliwiają wymianę konfiguracji ER może służyć do tego celu. Wreszcie sprawdzone konfiguracje ER można przekazać LCS, gdzie mogą być współużytkowane z subskrybentów usługi, albo do środowiska produkcyjnego do użytku wewnętrznego, takich jak pokazano na poniższej ilustracji. ![ER konfiguracji cyklu](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Informacje dodatkowe
--------

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)



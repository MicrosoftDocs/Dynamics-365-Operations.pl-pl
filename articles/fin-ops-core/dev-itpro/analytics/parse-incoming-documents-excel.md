---
title: Analizowanie dokumentów przychodzących w formacie programu Excel
description: Ten temat zawiera informacje na temat projektowania formatów raportowania elektronicznego (RE), aby przeanalizować zawartość znajdującą się w przychodzących plikach programu Microsoft Excel.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: d4ebad1b800abe77871bfa3e550a95f1fe2bfcc4692301cf79fb8b98a0b3f233
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772920"
---
# <a name="parse-incoming-documents-in-excel-format"></a>Analizowanie dokumentów przychodzących w formacie programu Excel

[!include[banner](../includes/banner.md)]

Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby analizowały przychodzące pliki programu Microsoft Excel reprezentujące dane skoroszytów programu Microsoft Excel (pliki w formacie XLSX). Następnie można użyć zawartości tych plików do aktualizacji danych aplikacji. Jest to użyteczne w następujących przypadkach:

- Projektujesz nowy model i format i chcesz je przetestować w czasie wykonywania. W tym wypadku program Excel będzie symulował rzeczywiste dane aplikacji.
- Zarządzasz danymi poza aplikacją w programie Excel i chcesz zaimportować te dane, aby przesłać określony raport.

Aby dowiedzieć się więcej o tej funkcji, odtwórz przewodników po zadaniach **ER importowanie danych z pliku programu Microsoft Excel (część 1: format projektu)** i **ER importowanie danych z pliku programu Microsoft Excel (część 2: importowanie danych)** (części procesu biznesowego 7.5.4.3 Pobierania/opracowywanie składników usług/rozwiązań informatycznych (10677)). Te wskazówki zadania pokażą Ci, jak można przeanalizować przychodzący plik Excel przy użyciu formatu ER, aby zaimportować informacje z dokumentów przychodzących i zaktualizować dane aplikacji. Możesz pobrać pliki przewodnika zadań z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).

Aby ukończyć przewodnik po zadaniach wymienione powyżej, należy pobrać następujące pliki:

| Opis zawartości                         | Plik                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| Przychodzący plik w formacie .XLSX — szablon    | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266) |
| Przychodzący plik w formacie .XLSX — przykładowe dane | [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Jeśli jeszcze nie odtwarzano przewodnika po zadaniu [ER Tworzenie wymaganych konfiguracji do importowania danych z pliku zewnętrznego](./tasks/er-required-configurations-import-data.md) w bieżącej aplikacji Finance and Operations, pobierz następujący plik.

| Opis zawartości    | Plik                                                            |
|------------------------|-----------------------------------------------------------------|
| Konfiguracja modelu ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
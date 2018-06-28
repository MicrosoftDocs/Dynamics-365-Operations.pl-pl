---
title: "Analizowanie dokumentów przychodzących w programie Microsoft Excel"
description: "Ten temat zawiera informacje na temat projektowania formatów raportowania elektronicznego (RE), aby przeanalizować zawartość znajdującą się w przychodzących plikach programu Microsoft Excel."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 001e287590b9f43ed38de803bcace3a25a6f6637
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2018

---

# <a name="parse-incoming-microsoft-excel-files"></a>Analizowanie przychodzących plików programu Microsoft Excel

[!include[banner](../includes/banner.md)]

Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby analizowały przychodzące pliki programu Microsoft Excel reprezentujące dane skoroszytów programu Microsoft Excel (pliki w formacie XLSX). Następnie można użyć zawartości tych plików do aktualizacji danych aplikacji. Jest to użyteczne w następujących przypadkach:

-   Projektujesz nowy model i format i chcesz je przetestować w czasie wykonywania. W tym wypadku program Excel będzie symulował rzeczywiste dane aplikacji.
-   Zarządzasz danymi poza aplikacją w programie Excel i chcesz zaimportować te dane, aby przesłać określony raport.

Aby dowiedzieć się więcej o tej funkcji, odtwórz przewodników po zadaniach **ER importowanie danych z pliku programu Microsoft Excel (część 1: format projektu)** i **ER importowanie danych z pliku programu Microsoft Excel (część 2: importowanie danych)** (części procesu biznesowego 7.5.4.3 Pobierania/opracowywanie składników usług/rozwiązań informatycznych (10677)). Te wskazówki zadania pokażą Ci, jak można przeanalizować przychodzący plik Excel przy użyciu formatu ER, aby zaimportować informacje z dokumentów przychodzących i zaktualizować dane aplikacji. Możesz pobrać pliki przewodnika zadań z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).

Aby ukończyć przewodnik po zadaniach wymienione powyżej, należy pobrać następujące pliki:

| Opis zawartości                        | Plik                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| Przychodzący plik w formacie .XLSX — szablon   | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)  |
| Przychodzący plik w formacie .XLSX — przykładowe dane| [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Jeśli jeszcze nie odtwarzano przewodnika po zadaniu [ER Tworzenie wymaganych konfiguracji do importowania danych z pliku zewnętrznego](./tasks/er-required-configurations-import-data.md) w bieżącej aplikacji Dynamics 365 for Finance and Operation, pobierz następujący plik:

| Opis zawartości                        | Plik                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| Konfiguracja modelu ER                     | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266)            |



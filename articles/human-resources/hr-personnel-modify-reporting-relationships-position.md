---
title: Modyfikowanie relacji zależności służbowych
description: W tej procedurze pokazano sposób zmiany relacji zależności służbowej dla pracownika.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db15394bf4bcd1b56781d269ad81aa1ad20b5e69
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728816"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modyfikowanie relacji zależności służbowych

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tej procedurze pokazano sposób zmiany relacji zależności służbowej dla pracownika. Relacja zależności służbowej może służyć do kierowania dokumentów przez przepływ pracy. W procedurze również pokazano sposób przypisywania pracownika do dodatkowych hierarchii. Na przykład pracownik może być częścią zespołu projektu z nieformalną relacją podlegania kierownikowi projektu. Na stanowisku można zdefiniować dodatkowe relacje służbowe, aby uwzględnić różne scenariusze projektowe lub macierzowe. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje **Zasoby ludzkie** \> **Stanowiska** \> **Stanowiska**.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według wartości **000091** pola **Stanowisko**.
3. Na liście wybierz łącze w wybranym wierszu.
4. Rozwiń sekcję **Stanowisko zwierzchnie**.
5. Wybierz przycisk **Nowy do**, aby otworzyć rozwijane okno dialogowe.
6. W polu **Przełożony** wprowadź lub wybierz wartość.
7. Wybierz opcję **Utwórz**.
8. Rozwiń sekcję **Relacje**.
9. Wybierz opcję **Dodaj**.
10. Zaznacz pole wyboru z lewej strony siatki.
11. W polu **Nazwa hierarchii** wprowadź lub wybierz wartość (np. **Projekt**).
12. W polu **Stanowisko zwierzchnie** wprowadź lub wybierz wartość (np. **000437**).
13. Wybierz opcję **Zapisz**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]

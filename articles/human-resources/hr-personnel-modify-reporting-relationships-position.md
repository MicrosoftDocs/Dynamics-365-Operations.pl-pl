---
title: Modyfikowanie relacji zależności służbowych
description: W tej procedurze pokazano sposób zmiany relacji zależności służbowej dla pracownika.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd884362393674a4f55ea0410548edbb72786fff
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465397"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modyfikowanie relacji zależności służbowych

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tej procedurze pokazano sposób zmiany relacji zależności służbowej dla pracownika. Relacja zależności służbowej może służyć do kierowania dokumentów przez przepływ pracy. W procedurze również pokazano sposób przypisywania pracownika do dodatkowych hierarchii. Na przykład pracownik może być częścią zespołu projektu z nieformalną relacją podlegania kierownikowi projektu. Na stanowisku można zdefiniować dodatkowe relacje służbowe, aby uwzględnić różne scenariusze projektowe lub macierzowe. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje Zasoby ludzkie > Stanowiska > Stanowiska.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Stanowiska z wartością „000091”.
3. Na liście kliknij łącze w wybranym wierszu.
4. Rozwiń sekcję Stanowisko zwierzchnie.
5. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
6. W polu Przełożony wprowadź lub wybierz wartość.
7. Kliknij przycisk Utwórz.
8. Rozwiń sekcję Relacje.
9. Kliknij przycisk Dodaj.
10. Zaznacz pole wyboru z lewej strony siatki.
11. W polu Nazwa hierarchii wprowadź lub wybierz wartość.
    * Przykład: Projekt  
12. W polu Stanowisko zwierzchnie wprowadź lub wybierz wartość.  Przykład: 000437.
13. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
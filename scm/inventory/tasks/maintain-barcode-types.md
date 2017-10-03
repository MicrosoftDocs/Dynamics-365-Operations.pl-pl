---
title: "Obsługa typów kodów kreskowych"
description: "W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 57ad3f2cb4f4a246af4d58001c6ef56c440b5431
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="maintain-bar-code-types"></a>Obsługa typów kodów kreskowych

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości. Te zadania zazwyczaj wykonuje kierownik magazynu.

1. Przejdź do okna Kody kreskowe.
2. Kliknij przycisk Nowy.
3. W polu Konfiguracja kodów kreskowych wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ kodu kreskowego wybierz opcję.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać opcję „Kod 39”.  
6. W polu Rozmiar wpisz liczbę.
7. W polu Długość maksymalna wpisz liczbę.
8. Kliknij przycisk Zapisz.
9. Zamknij stronę.
10. Przejdź do okna Parametry modułu Zarządzanie zapasami i magazynem.
11. W polu Konfiguracja kodów kreskowych wprowadź lub wybierz wartość.
    * Wybierz utworzoną wcześniej konfigurację kodu kreskowego, ale pamiętaj, że format kodu kreskowego musi być zgodny z formatem unikatowego identyfikatora typu rekordu używanego w procesie. Na przykład dla marszrut pobrania format kodu kreskowego musi być zgodny z formatem odwołania do marszruty pobrania, który jest zazwyczaj sekwencją numeracji.  
12. Kliknij przycisk Zapisz.
13. Zamknij stronę.


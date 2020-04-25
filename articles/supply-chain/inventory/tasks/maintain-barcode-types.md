---
title: Obsługa typów kodów kreskowych
description: W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 979726a1d094146b546bbc6d31963367de2c59f5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204086"
---
# <a name="maintain-barcode-types"></a>Obsługa typów kodów kreskowych

[!include [banner](../../includes/banner.md)]

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

